---
title: Rename formulas
weight: 45
description: In this section, you will find how to rename a formula in Ritchie.
---

---

## **How to rename a formula?**

### **Premisses**

{{% alert color="warning" %}}

Only local formulas can be renamed.

{{% /alert %}}

## **Renaming your formula**

You can use the core command **`rit rename formula`** to rename a local formula. The required input parameters are:

1. The name of the old formula;
2. The new formula name;
3. The workspace name.

- **Example:** `rit group old` > `rit group new` > `Default`

![](/shared/rit-rename-formula.gif)

{{% alert color="info" %}}

- Ritchie will automatically identify the workspace to which the formula belongs to.
- If the CLI identify more than one workspace with the entered formula, an extra step (_when using prompt execution_) will be necessary to identify in which workspace the formula should have its name changed.
- This formula includes entry via _flag_.

For more information, check out the [**Formula commands**]({{< ref path="/Standard Inputs/Formulas commands" >}}) section.

  {{% /alert %}}

## **Effects**

1. All files that identify the formula will be changed to the new formula name. _These changes reflect both in Ritchie's internal control folders and in the workspace folder (whether it is the default or custom)_.

2. Ritchie's autocompleted will only identify the new formula name.

## **Next steps**
Keep configuring your formula:

👉 Check out [**how to share formulas**]({{< ref path="/Formulas/Share formulas.md" >}}).
