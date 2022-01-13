---
title: Create and update formulas
weight: 29
description: >-
  In this section, you will find how to create and update formulas on Ritchie and test them.
---

---

## **How to create?**

### **Create your formula**

Run the following command to create a formula:

```text
rit create formula
```

{{% alert color="warning" %}}

To run this command, you need to have, at least, one templates in your Ritchie's repository.

{{% /alert %}}

You'll have to inform those inputs before running the formula:

1. The **command** (following the **pattern `rit + group + verb + noun`** to respect the [**tree pattern**]({{< ref path="Reference/Glossary" >}})).
2. The formula's **programming language**.
3. **The workspace** used to save formula's files.


{{% alert color="info" %}}

When you have finished creating your formula, it will be built according to the template and sent to a specific repository according to the selected **workspace**.

**Example:** If you chose the `Default` workspace:

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

{{% /alert %}}

Example: `rit demo create formula`

![](/shared/rit_create_formula.gif)

### **Update your formula**

You can update the formula by modifying their workspace files.
For more information about which files to modify, go to [**organize the formula folder**]({{< ref path="formulas/Organize the formula folder" >}}).

When you run the formula for the first time after modifying the files in the workspace, Ritchie will apply the modification and rebuild the formula automatically.

{{% alert color="warning" %}}

Don't forget to update the unit tests.

{{% /alert %}}

### **Test your formula**

You can test the formula directly after its creation. That's possible because the **`rit create formula`** command also builds the formula automatically (it generates the formula's executable files and add them on **.rit folder**).

In that case, the formula **"Hello World" template** will be executed as you can see below:

![](/shared/rit_demo_hello-world.gif)

This template has 4 inputs parameters, that represent the currently available kinds of inputs to use Ritchie.

1. A **`sample text`** variable
2. A **`sample list`** of text variables
3. A **`sample boolean`** variable
4. A **`sample password`** variable



## **Next steps**
Keep configuring your formula:
- Go to [**organize the formula folder**]({{< ref path="formulas/Organize the formula folder" >}}) to see how to organize the formulas you create.
