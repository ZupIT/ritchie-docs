---
title: Glossary
weight: 103
description: In this section, you will find more about Ritchie's concepts.
---
 
---

The main concepts on Ritchie are

- CLI
- Command Tree
- Credential
- Environment
- Formula
- JSON
- Repository
- Standard Streams

## **CLI**

It is a command line interface, which is a program that processes commands in a software or any computing program only through text.

## **Command Tree**

{{% alert color="info" %}}

Commands used in Ritchie are grouped according to a **"tree"**.
It is important to know this concept in order to actually understand the structure of the product.

{{% /alert %}}

In the case of Ritchie, the **Cobra** (a Golang library) pattern was followed using the following logic of building core commands:

**`RIT + VERB + NOUN`**

To allow more options and freedom for users, it is also allowed to follow the pattern below in the construction of formula commands:

**`RIT + GROUP + VERB + NOUN`**

The app name is Ritchie, so we use the name **`rit`** to start our command tree.

![](/shared/arvore-rit.png)

{{% alert color="warning" %}}

The **`rit`** command is therefore our parent command, or **root**. It is not executable, but has been configured to return the **helper command**.

It is necessary to use executable sub-commands (which are child commands, or branches, of the rit command) in order to start any process.

{{% /alert %}}

The executable commands in Ritchie are the commands located at the last level of the tree.

For example, in the image above:

- The **`rit set context`** command is executable, as it is at the last level of the tree.
- The **`rit kafka create`** command is not executable as there is an executable **topic** subcommand, at the last level of the tree.

This command tree concept is the **core** of Ritchie's structure.

{{% alert color="info" %}}

All commands and sub-commands are mapped in a tree **dynamically** created according to the repositories the user added locally on his computer by using the **`rit add repo`** command.

{{% /alert %}}

## **Credential**

It is the reusable input parameters you can use in Ritchie (for example: access data for any tool or api).

## **Environment**

On Ritchie, each environment will have its own credentials, it may be necessary to execute specific formulas through the CLI.

_For example: it's possible to create a **professional** and a **personal** environments (or **prod** and **staging**) with different credentials, and switch from an environment to another according to the necessity._

## **Formula**

In Ritchie's context, the **formulas** are **scripts** executed through a **command line**. The user can execute it locally or through Docker with the necessary dependencies.

### **Run formulas**

Depending on the formula, the user might need to inform input parameters.

Those input parameters can be informed in different ways:

- After running the command on the terminal (via **prompt**).
- When typing the command on the terminal (via **stdin** or **input flags**).
- During the execution of the formula (if coded using **prompt**).

![](/shared/start-end-ritchie.jpg)

## **JSON**

JavaScript Object Notation (JSON), it is a standard text based format used to structure data created with JavaScript programming language.

## **Repository**

A storage place you can organize features, commands or any files and/or files necessary to use a tool. On Ritchie, there are three repositories created to manage formulas, the server and contributions we receive.

- [**ritchie-cli**](https://github.com/ZupIT/ritchie-cli).
- [**ritchie-formulas**](https://github.com/ZupIT/ritchie-formulas).

## **Standard Streams**

It is a communication channel that allows input and output interconnection between a computer program and its environment.

On Ritchie, the standard input (stdin) is used to execute commands automatically.
