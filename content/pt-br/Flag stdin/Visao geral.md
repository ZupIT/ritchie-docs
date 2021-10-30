---
title: Visão Geral
weight: 66
description: Nesta seção, você vai encontrar mais detalhes sobre a flag stdin.
---

---

{{% alert color="danger" %}}

A flag **--stdin** será descontinuada no início de 2021, sendo substituída pelos [**input flags**]({{< ref path="Standard inputs" >}}).

{{% /alert %}}

A flag **`--stdin`** no Ritchie foram desenvolvidas para oferecer mais uma opção para quem usa os parâmetros de entrada por meio de linha de comando.

Nesse caso, os parâmetros de entrada devem ser informados em um **formato JSON**:

**`echo`**`'{"key":"value"}'`**`|`**`RIT (GROUP) VERB NOUN` **`--stdin`**

Você pode usar essas regras da flag stdin em:

👉 [**Comandos Core**]({{< ref path="Flag stdin/Comandos core" >}}).

👉 [**Comandos de fórmulas**]({{< ref path="Flag stdin/Comandos de fórmulas" >}}).
