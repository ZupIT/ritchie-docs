---
title: Create formulas
weight: 29
description: >-
  In this section, you will find how to create formulas on Ritchie and test them.
---

---

## **How to create?**

### **Step 1: Run the formula creation command**

Run the following command to create a formula:

```text
rit create formula
```

Then, you'll have to inform those inputs before running the formula:

1. The **command** (following the **pattern `rit + group + verb + noun`** to respect the [**tree pattern**]({{< ref path="Reference/Glossary" >}})).
2. The formula's **programming language**.
3. **The path** used to save formula's files.

Example: `rit demo create formula`

![](/shared/rit_create_formula.gif)

### **Step 2: Test your formula**

You can test the formula directly after its creation. That's possible because the **`rit create formula`** command also builds the formula automatically (it generates the formula's executable files and add them on **.rit folder**).

In that case, the formula **"Hello World" template** will be executed as you can see below:

![](/shared/rit_demo_hello-world.gif)

This template is composed of **4 inputs parameters**, that represents the currently available kinds of inputs to use Ritchie:

1. A **`sample text`** variable
2. A **`sample list`** of text variables
3. A **`sample boolean`** variable
4. A **`sample password`** variable

When you finished creating your formula, it will be built and sent to a specific repository according to the name of your workspace with the prefix **"local".**

**Example:** If we have a workspace with `Default` name:

```text
{
    "Default":"/home/user/ritchie-formula-local"
}
```

A repository associated to this workspace will be created on the **`/home/user/.rit/repos`** folder, and added on the **`repositories.json`** file.

```text
[
	{
		"provider": "Local",
		"name": "local-default",
		"version": "0.0.0",
		"url": "local repository",
		"priority": 0,
		"isLocal": true
	}
]
```

## **Next steps**
Keep configuring your formula:
- Go to [**organize the formula folder**]({{< ref path="formulas/Organize the formula folder" >}}) to see how to organize the formulas you create.
