# Creating a Custom Snippet

A custom snippet provides a way to run and test any code body in any language you can write a docker container for.  

## How it works

When a student submits code in a custom snippet Learn then:

1.  Creates a container from a designated `Dockerfile` and associated files
2.  Copies the student submission into the container as `submission.txt`
3.  Runs the Bash script `test.sh` on the container
4.  Sends the output from the container back to Learn

## Creating A Custom Snippet

### Step 1:  Create a folder for your docker/testing setup

First create a folder on your repository to create a custom snippet testing.  

I recommend setting up this directory organization:

```txt
├── custom-snippets
│   ├── <snippet-name-1>
│   │   ├── Dockerfile
│   │   ├── test.sh
│   │   ├── Gemfile
│   │   ├── snippet_test.rb
│   │   ├── other files
│   ├── <snippet-name-2>
│   │   ├── Dockerfile
│   │   ├── test.sh
│   │   ├── Gemfile
│   │   ├── snippet_test.rb
│   │   ├── other files
...
```

### Create A Dockerfile

A `Dockerfile` is a file used to build a container used for testing the submission.

Here is a decent sample Dockerfile for testing Ruby code.  It creates a container with Ruby 2.7, and installs needed gems and then creates a folder copies the local files to the container and makes `test.sh` runnable.

```Dockerfile
# Starting from a minimalist image
FROM ruby:2.7

# Optional
# Reference for help contact me
LABEL maintainer="chris@adadev.org"

# Create a directory for the app
RUN mkdir /app

# Set the working directory for RUN, ADD and COPY
WORKDIR /app

# Copy the Gemfile into 
COPY ./Gemfile .
RUN gem install bundler
RUN bundle install

COPY . .

RUN chmod +x test.sh
```

### Create Script to execute tests

You should also create a Bash script file to run the tests.  Below is a sample bash script.

```bash
#!/bin/bash

# rename submission.txt into a ruby file
mv submission.txt submission.rb

# Run the test file
ruby snippet_test.rb
```

### Create Gemfile - Ruby only

You can create a Gemfile for Ruby applications to install needed libraries.

### Create Tests

You can then create a test file.

```ruby
require "minitest/autorun"
require "minitest/reporters"
require "stringio"

Minitest::Reporters.use! Minitest::Reporters::SpecReporter.new

FILENAME_TO_TEST = "./submission.rb"


# Method to test User input
# *inputs: Simulated text inputs (array)
# block: Block of code to execute using that input
def simulate_stdin(*inputs, &block)
  # Switch Standard input to 'inputs'
  io = StringIO.new
  inputs.flatten.each { |str| io.puts(str) }
  io.rewind

  actual_stdin, $stdin = $stdin, io
  # Run the block
  yield
ensure
  # Switch Standard input back
  $stdin = actual_stdin
end


describe "Test Suite" do

  # Run the file as a Ruby file and capture
  #   standard output
  def user_input_helper(given_input, filename)
    output = StringIO.new
    original_stdout = $stdout
    $stdout = output
    simulate_stdin(given_input) do
      eval File.read(filename).force_encoding("utf-8")
    end
    $stdout = original_stdout
    
    output_list = output.string.split(/\s/)
    return output_list
  end
  
  it "will print hello," do
    output_list = user_input_helper('', FILENAME_TO_TEST)
    
    includes_hello = false
    output_list.each do |word|
      if word.match /hello,/i
        includes_hello = true
      end
    end

    expect(includes_hello).must_equal true
  end

  it "will include world!" do
    output_list = user_input_helper('-1', FILENAME_TO_TEST)

    includes_world = false
    output_list.each do |word|
      if word.match /world\!/i
        includes_world = true
      end
    end

    expect(includes_world).must_equal true
  end
end
```
