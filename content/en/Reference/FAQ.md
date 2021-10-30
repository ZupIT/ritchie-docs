---
title: FAQ
weight: 104
description: In this section, you will find the main questions about Ritchie.
---

---

# **About Ritchie**

### **What is Ritchie?**

Ritchie is an **open source framework** that creates and tweaks a CLI for your team. It allows you to easily create, build and share [**formulas**]({{< ref path="Glossary/#formula" >}}). For more information, check out [**about Ritchie section**]({{< ref path="Reference/About ritchie" >}}).

### **What does Ritchie do?**

Ritchie creates automation commands to improve the operational **developers' experience and brings beneficial such as:**

- Simplify repetitive and easy-to-execute tasks
- Reduce the rework
- Promote more time for the development team to focus on their deliveries.

## **Installation and Use**

### **How to install Ritchie?**

You can follow the installation step by step according do the operational system you're using. For more information, check out the [**installation section**]({{< ref path="Getting started" >}}).

### **How to create a new formula on Ritchie?**

Using the command `rit create formula` , you can create formulas using any programming language. Check out more in [**create a formula section**]({{< ref path="Formulas/Create formulas" >}}).

### **How to create formulas on an existing repository?**

Follow the next steps:

1. Clone the repo;
2. Add the repo with `rit add workspace` command;
3. Add the new formula with `rit create formula` command and implement it.

### **How to run formulas?**

You can execute your formulas locally or through Docker. For more information, check out [**how to run a formula section**]({{< ref path="Formulas/Run formula" >}}).

### **How to build formulas on Ritchie?**

When you run a formula, a build is automatically made, you don't need a command to do that.

### **How to update a formula from a repository?**

Follow the next steps:

1. Locally clone the repo;
2. Add the repo with the `rit add workspace` command;
3. Now, update the workspace.

### **How to execute a formula from a repository?**

Use `rit add repo ` command to add the repository.

### **How to publish formulas on Ritchie?**

You can publish a formula by creating a Github's, Gitlab's or Bitbucket's repository and adding a release version of this formula. For more information, check out how to [**publish a formula section**]({{< ref path="Formulas/Publish formulas" >}}).

# **Community**

### How to submit my formula on community's repo?

You just have to open a pull request on [**ritchie-formula's repository** ](https://github.com/ZupIT/ritchie-formulas) with your formula suggestion.

### **How to contribute?**

You can contribute with improvements, suggestions or reporting bugs on[ **ritchie-cli's repository.** ](https://github.com/ZupIT/ritchie-cli)That's the process you should follow:

1. Fork the repository.
2. Create a branch: `git checkout -b <branch_name>`.
3. Implement your idea.
4. Commit your implementation: `git commit -m '<commit_message>'`.
5. Push your branch: `git push origin <project_name>/<location>`.
6. Open a pull request on the `main` branch for analysis.
