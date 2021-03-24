---
title: Overview
weight: 66
description: In this section, you will find more about stdin flag. 

---

{{% alert color="danger" %}}
The STDIN flag will be deprecated in early 2021, as substituted by [input flags](/docs-ritchie/standard-inputs/input-flag/).
{{% /alert %}}

{{% alert color="info" %}}
The **`--stdin`** flag on Ritchie has been developed to inform input parameters directly on the command lines.  
  
In that case, the input parameters need to be informed in a **JSON format**:

**`echo`**`'{"key":"value"}'`**`|`**`RIT (GROUP) VERB NOUN` **`--stdin`**
{{% /alert %}}

You can use this stdin flag rules on:

👉 [**Core Commands**](/docs-ritchie/stdin-flag/stdinflag-core-commands/)

👉 [**Formulas Commands**](/docs-ritchie/standard-inputs/formulas-commands/)