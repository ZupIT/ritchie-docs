---
title: Como usar a flag stdin
weight: 64
---

---

{{% alert color="info" %}}
A flag **`--stdin`** no Ritchie foi desenvolvida para também dar suporte nesse cenário. Nesse caso, os parâmetros de entrada devem ser informados em um **formato JSON**:

**`echo`**`'{"key":"value"}'`**`|`**`RIT (GROUP) VERB NOUN` **`--stdin`**
{{% /alert %}}

Você pode usar essas regras da flag stdin em:
