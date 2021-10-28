---
title: Test formulas 
weight: 51
description: 'In this section, you will find how to test formulas on Ritchie.'
---

---

## **Unit Tests** 

In Ritchie CLI context, Unit tests are the way of testing a part of your formula implementation.

Some of the formula templates - Java and Golang - currently have a Test class to write and run the formula unit tests.

You can also configure your CI/CD and release processes to run those tests after each formula update or addition. 

## **Functional Tests**

### **Using Github Actions**
Ritchie’s team recently developed a Github action to test CLI commands outputs. Check the Github repository [**test-cli-commands-action**](https://github.com/GuillaumeFalourd/test-cli-commands-action).

Ritchie CLI uses this action to make sure the CLI core commands behave as expected after updating the files related to them.

### **How does this action work?**

![](/shared/githubactions.PNG)

When you use this action, you can check different implementation scenarios through the formulas outputs, according to the formulas inputs. You can run the tests only when you update a file from the formula directory.

For more information about actions, check out the [**Github Marketplace page**](https://github.com/marketplace/actions/test-cli-commands-action) or the [**How to test formulas**]({{< ref path="Tutorials/how to test formulas.md" >}}) tutorial.
