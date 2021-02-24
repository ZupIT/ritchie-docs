---
title: Introduction
weight: 24
description: 'In this section, you will find a path to how run formulas using Ritchie.'
---

## How to run formulas?

There are two ways to run formulas on Ritchie :

1. Locally
2. Using Docker

It's good to reinforce that the **default formulas execution method** is defined during the initialization step with the **`rit init`** command. You can change this setting by running the following command:

```text
rit set formula-runner
```

![](/docs/large-gif-1374x404-.gif)

### 1. Locally

To run a formula locally, it is necessary to have installed on your computer the formula programming languages dependencies used to create the formula.

Example: a formula written in **Node** will need **Node installed** on the computer, so it will be able to run locally.   


### 2. Through Docker

All formulas can run regardless the programming language used from the moment you have **`DOCKER`** installed and running.

{{%/* alert color="info" %}}
Check out on the following example [**how to run a "Hello World" formula** ](hello-world-formula)
{{% /alert */%}}

###  3. Local & Docker Flags

You can force Ritchie CLI to execute a formula with a specific method using flags.

* The **`--local`** flag will execute a formula with locally \(if the default method is Docker\). 
* The **`--docker`** flag will execute a formula with Docker \(if the default method is local\). 

### 4. Containers with Ritchie

{{%/* alert color="warning" %}}
All formulas templates contain a **Dockerfile** which creates a container with **Ritchie CLI** installed.
{{% /alert */%}}

## Next steps 

On this section, you saw how to run a formula on Ritchie. To keep learning:

👉 Go to [**Hello World formula**](hello-world-formula) to see different ways to run a formula on Ritchie. 

👉 Go to the [**create formulas**](/docs-ritchie/tutorials/formulas/how-to-create-formulas/) section to understand how to create your first automation with Ritchie.