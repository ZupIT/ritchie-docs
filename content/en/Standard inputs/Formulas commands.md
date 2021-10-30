---
title: Formulas commands
weight: 77
description: >-
  In this section, you will find more details about formula commands that can be used through input flags.
---

---

The Input flags with formulas are based on the **inputs parameters names**. They are informed in the **config.json file** used to implement the formula.

### **Example** 

1. Formula command: **`rit demo formula`**

2. Inputs names asked in the config.json file:

   * **`name`**
   * **`surname`**
   * **`dateOfBirth`**

3. Formula execution with input flags:

```text
rit demo formula --name="dennis" --surname="ritchie" --dateOfBirth="09/09/1941"
```

{{% alert color="danger" %}}

 The formula's command through Input flags needs the input parameters based on the config.json to work properly. 

{{% /alert %}}
