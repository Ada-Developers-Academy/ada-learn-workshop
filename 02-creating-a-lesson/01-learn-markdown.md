# Learn Markdown

Learn markdown is much like Github Markdown.  However there are some extra markdown items that Learn provides.

You can see a list of special markdown blocks Learn can handle by typing `learn markdown`, in the terminal.

## Callouts

You can generate callouts by using the following code.  You can generate a template for a callout by using the Learn Cli tool and typing 

```txt
<!-- available callout types: info, success, warning, danger, secondary  -->
### !callout-info

## title
body

### !end-callout
```

## Learn Questions

Learn can also make the following questions such as:

* multiplechoice
* checkbox
* shortanswer
* number
* paragraph
* javascript
* java
* python
* sql
* customsnippet
* project
* testableproject

The multiplechoice, checkbox, shortanswer, number and many programming exercises can be automatically graded, while others require an instructor to review them.  Each question requires a unique which the learn markdown can generate.  The Learn VS code extension can also generate an ID, if you need.

An example question is:

```txt
<!-- >>>>>>>>>>>>>>>>>>>>>> BEGIN CHALLENGE >>>>>>>>>>>>>>>>>>>>>> -->
<!-- Replace everything in square brackets [] and remove brackets  -->

### !challenge

* type: multiple-choice
* id: a1df3456-f00d-4a12-bcf8-e77fa9ccc1a3
* title: Hitchhiker's Guide
* points: 1
* topics: questions about life

##### !question

What is the answer to the ultimate question?

##### !end-question

##### !options

* 42
* Pasta
* Pizza

##### !end-options

##### !answer

* 42

##### !end-answer

<!-- other optional sections -->
<!-- !hint - !end-hint (markdown, users can see after a failed attempt) -->
<!-- !rubric - !end-rubric (markdown, instructors can see while scoring a checkpoint) -->
<!-- !explanation - !end-explanation (markdown, students can see after answering correctly) -->

### !end-challenge

<!-- ======================= END CHALLENGE ======================= -->
```

## Exercise

With your partner create a couple of Questions in your markdown documents.  Then publish the material on Learn and view them in the LMS.  
