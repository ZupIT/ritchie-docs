---
title: Como usar a flag stdin
weight: 66
---

---

{{%/* alert color="danger" %}}
A flag **--stdin** será descontinuada no início de 2021, sendo substituída pelos [input flags](../../como-usar-input-flags/).
{{% /alert %}}

{{% alert color="info" %}}
A flag **`--stdin`** no Ritchie foram desenvolvidas para oferecer mais uma opção para quem usa os parâmetros de entrada por meio de linha de comando.   
  
Nesse caso, os parâmetros de entrada devem ser informados em um **formato JSON**:  

{{% alert color="info" %}}
*`echo`**`'{"key":"value"}'`**`|`**`RIT (GROUP) VERB NOUN` **`--stdin`**
{{% /alert %}}

Você pode usar essas regras da flag stdin em:
