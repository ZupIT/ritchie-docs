---
title: Build formulas
weight: 42
description: 'In this section, you will find how to build formulas on Ritchie.'
---

---

{{% alert color="danger" %}}

This functionality is no longer available from **Ritchie's 2.5.0 version**. From now on, a formula build is automatically made on your CLI: a local repo file will be created as soon as you implement the formula to host it.

If you're using a previous version just follow the instructions of this section.

{{% /alert %}}

## **How to build?**

After [**creating a formula**]({{< ref path="Formulas/Create formulas" >}}), if you want to edit the code of the formula, it's necessary to **build** these changes to test the command with the new implementation. 

To do so, run the command:

```text
rit build formula
```

You must inform: 

* The **directory's path** where the formula is located.
* The **formula's path** to be builded (the formula's command). 

If you want to update the formula's code in running time, you can use the **flag “--watch”** like in the command below:

```text
rit build formula --watch
```
