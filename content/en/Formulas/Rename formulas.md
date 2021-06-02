---
title: Rename formulas
weight: 45
description: In this section you will find information about how to rename a formula in Ritchie.
---

---

## How to rename?

### Premisses

{{% alert color="warning" %}}
Only local formulas can be renamed.
{{% /alert %}}

## Renaming your formula

You can use the core command **`rit rename formula`** to rename a local formula. The required input parameters are:

1. The name of the old formula;
2. The new formula name.

Example: `rit group old` > `rit group new`

![](/docs-ritchie/shared/rit-rename-formula.gif)

{{% alert color="info" %}}

- Ritchie will automatically identify the workspace to which the formula belongs.
  - If you identify more than one workspace with the entered formula, an extra necessary step will be to choose in which workspace the formula should have its name changed.
- This formula includes entry via _flag_, check out more on [**Formula commands**](/docs-ritchie/standard-inputs/formulas-commands/) page.
  {{% /alert %}}

## Effects

1. All files that identify the formula will be changed to the new formula name

   _these changes reflect both in Ritchie's internal control folders and in the workspace folder (whether it is the default or custom)_

2. Ritchie's autocompleted will only identify the new formula name.

## Next steps

In this section, you saw how to rename a formula on Ritchie. To keep configuring the formula:

👉 Check out [**how to share formulas**](/docs-ritchie/formulas/share-formulas/).
