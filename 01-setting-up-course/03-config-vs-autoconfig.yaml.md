# Config vs Autoconfig

When you publish content to learn with the Learn Cli tool you need a file to tell Learn the sequence of lessons and units.  If you don't have a `config.yaml` file Learn will generate an `autoconfig.yaml` file listing the units and lessons by lexographic order.  

<!-- available callout types: info, success, warning, danger, secondary  -->
### !callout-danger

## About `autoconfig.yaml`

If you publish and have an existing `autoconfig.yaml`, the command `learn publish` will fail.  To get around this delete the `autoconfig.yaml` file with `git rm autoconfig.yaml` and commit the changes before publishing.  

Later you can fix this by creating a `config.yaml` file and commiting it to git.

### !end-callout

## Creating a `config.yaml` file

If you want a non-alphanumeric sequence of lessons and units, or get tired of deleting `autoconfig.yaml`, you can rename `autoconfig.yaml` file to `config.yaml` and then edit it to include descriptions of the lessons and units.

Sample `config.yaml`

```yaml
---
Standards:
  -
    Title: Pre-Ada 01 Getting Started
    Description: In this lesson we work on learning to setup your environment and basic Ruby types.
    UID: a316578c4adce5d91a5b045726442435
    SuccessCriteria:
      - success criteria
    ContentFiles:
      -
        Type: Lesson
        UID: afef9e07f2b5b2e59ab6d99d5c740c79
        Path: /01-pre-ada01/00-starter/00-starter.md
      -
        Type: Lesson
        UID: 801227701c626242c993bbb484d8979b
        Path: /01-pre-ada01/01-workflow/01-workflow.md
      -
        Type: Lesson
        UID: 72d8f4ac70ecacfdc1fb9a21260499cd
        Path: /01-pre-ada01/02-ruby-style/02-ruby-style.md
      -
        Type: Lesson
        UID: 88548f5a0d532127475b88ad71afaf93
        Path: /01-pre-ada01/03-ruby-types/03-ruby-types.md
      -
        Type: Lesson
        UID: 8eeff16177653f68b02e3759da2a0b8f
        Path: /01-pre-ada01/04-keyboard-input/04-keyboard-input.md
      -
        Type: Lesson
        UID: 3de34358f6004c672b3d429b2d874868
        Path: /01-pre-ada01/05-strings/05-strings.md
      -
        Type: Lesson
        UID: ed4172bd56ca60b10150c992624febe9
        Path: /01-pre-ada01/06-assignment-statements/06-assignment-statements.md
      -
        Type: Checkpoint
        UID: 530b3bda94dd8b9fa331492954ed4687
        Path: /01-pre-ada01/07-practice-checkpoint/07-practice-checkpoint.md
  -
    Title: Pre-Ada 02 Decision Making & Looping
    Description: In this lesson we will look at creating conditionals in Ruby and practice writing programs which do so.
    UID: c4f8b81e9b3040e95d0b5e87f43e6874
    SuccessCriteria:
      - success criteria
    ContentFiles:
      -
        Type: Lesson
        UID: f6d43b161129b793cd7f29890daa2139
        Path: /02-pre-ada02/00-starter/00-starter.md
      -
        Type: Lesson
        UID: f62f1ae67dbd4ec57bd331de0568efa1
        Path: /02-pre-ada02/01-boolean-expressions/01-boolean-expressions.md
      -
        Type: Lesson
        UID: 6e1601dc3331f7f2b37b212f1de4ea4a
        Path: /02-pre-ada02/02-conditionals/02-conditionals.md
      -
        Type: Lesson
        UID: b18e0e43ea90466408ba4dfdbf032edb
        Path: /02-pre-ada02/03-while-loops/03-while-loops.md
      -
        Type: Resource
        UID: 4802e9ad7603ebc4836eeb282641818f
        Path: /02-pre-ada02/03-while-loops/while-solution.resource.md
      -
        Type: Checkpoint
        UID: a494d8583e206c5400bc8c7bd2982df8
        Path: /02-pre-ada02/04-exercises/04-exercises.checkpoint.md
  -
```

## Exercise

Rename your `autoconfig.yaml`, add and commit your material and re-publish the content.
