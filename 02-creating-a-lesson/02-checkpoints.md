# Checkpoints

A Checkpoint is a markdown file which is named to end with `checkpoint.md`.  Each Checkpoint file must have at least one question.  Checkpoints are otherwise normal markdown documents.   Checkpoints are essentially tests, you can create auto-graded and 

<!-- >>>>>>>>>>>>>>>>>>>>>> BEGIN CHALLENGE >>>>>>>>>>>>>>>>>>>>>> -->
<!-- Replace everything in square brackets [] and remove brackets  -->

### !challenge

* type: multiple-choice
* id: ef0d1524-c73c-4160-8234-2d1fc3c43c8e
* title: Example MC Question
* points: 1
* topics: Example Question

##### !question

Which file determines which repos are used by a course?

##### !end-question

##### !options

* .gitignore
* autoconfig.yaml
* course.yaml
* config.yaml

##### !end-options

##### !answer

* course.yaml

##### !end-answer

<!-- other optional sections -->
##### !hint

config and autoconfig.yaml determine the sequence of units within a section.

##### !end-hint

##### !explanation 

course.yaml lists the repos used for a course.

##### !end-explanation

### !end-challenge

<!-- ======================= END CHALLENGE ======================= -->

## Exercise

Create a checkpoint lesson with 1 question and then publish the results.