---
title: How to use the stdin flag
weight: 66
---

---

{{% alert color="danger" %}}
The STDIN flag will be deprecated in early 2021, as substituted by [input flags](../../how-to-use-input-flags/).
{{% /alert %}}

{{% alert color="info" %}}
The **`--stdin`** flag on Ritchie has been developed to inform input parameters directly on the command lines.  
  
In that case, the input parameters need to be informed in a **JSON format**:

**`echo`**`'{"key":"value"}'`**`|`**`RIT (GROUP) VERB NOUN` **`--stdin`**
{{% /alert %}}

You can use this stdin flag rules on**:**
