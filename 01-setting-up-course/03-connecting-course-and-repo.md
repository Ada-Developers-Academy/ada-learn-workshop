# Course.yaml

Each course you create is connected with a file called `course.yaml`.  This file lists all the repositories that your course uses.  

## Create a `course.yaml`

Below is an example `course.yaml file.

```yaml
---
:Course:
- :Section: Pre-Ada Units
  :Repos:
  - :Url: https://github.com/gSchool/ada-jumpstart-live-programming-workflow
```








## Multi-repo example

Below is a multi-repo example of a course.yaml file

```yaml
---
:Course:
- :Section: Pre-Ada Units
  :Repos:
  - :Url: https://github.com/gSchool/ada-jumpstart-live-programming-workflow
- :Section: Learn Workshop
  :Repos:
  - :URL: https://github.com/gSchool/ada-learn-workshop
```