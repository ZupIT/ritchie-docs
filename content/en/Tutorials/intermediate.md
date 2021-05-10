---
title: Intermediate
weight: 88
description: >-
  In this section, you will find a step by step to use condition inputs on
  Ritchie.
---

# Intermediate: Conditional Inputs

## Objective

Create a formula on Ritchie that will **return the tool selected by the user according to its profile**.

> You'll find all the information you need about the **conditional field** on the [**config.json inputs**](/docs-ritchie/formulas/configure-inputs/).

{{% alert color="info" %}}
Command suggestion: **`rit get tools`**
{{% /alert %}}

## Inputs

This formula needs to contain \(at least\) those two inputs parameters:

* Profile \(`RIT_PROFILE`\).
* Profile tool \(`RIT_TOOL`\).

The formula inputs will have to respect the diagram below:

![](/shared/ritchie-conditional-inputs.png)

## Step by step

The formula needs to follow the next steps:

1. Extract all inputs parameters.
2. Return the selected profile on the terminal.
3. Return the selected tool on the terminal.

## Improvement suggestions

 If you want to play a little more, here are some suggestions:

* Install the selected tool according to the computer OS.

## Next steps

👉 If you've completed the third tutorial, let's go to the [**advanced task**](/docs-ritchie/tutorials/advanced/)!
