# Getting Started With Learn

In this lesson we just get setup to write Learn Content.

## Log into Learn

Go to [Learn](https://learn-2.galvanize.com/api_token) and log in with your Github account.  Learn has 2 sections **Learn** and **Auth**.

* Learn is the LMS tool which handles content management and grading. 
* Auth handles Authentication, enrolling students in courses and I _think_ connecting Learn to things like SalesForce.

## Learn Cli Tool

If you haven't already done so please install the Learn Cli tool with:

```bash
brew tap gSchool/learn

brew install learn

learn set --api_token=YOUR_LEARN_API_TOKEN
```

You can find your [API token](https://learn-2.galvanize.com/api_token) on Learn. 

## Resources

- [Learn Cli Docs](https://github.com/gSchool/glearn-cli)
