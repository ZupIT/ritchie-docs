---
title: Comandos de fórmulas
weight: 77
description: >-
  Nesta seção, você vai encontrar mais detalhes sobre comandos de fórmulas que podem ser usados via input flags.
---

---

As Input flags, com as fórmulas, tem como base os **nomes dos parâmetros de entrada**. Eles são informados no arquivo **config.json** no momento de implementar uma fórmula. 
 
### **Exemplo**

1. Comando de fórmula: **`rit demo formula`**

2. Nomes dos parâmetros de entrada que são perguntados pelo arquivo config.json:

   * **`name`**
   * **`surname`**
   * **`dateOfBirth`**

3. Execução da fórmula com Input flags:

```text
rit demo formula --name="dennis" --surname="ritchie" --dateOfBirth="09/09/1941"
```

{{% alert color="danger" %}}

O comando de fórmula, por meio do input flags, precisa dos parâmetros de entrada colocados no config.json para funcionar corretamente.

{{% /alert %}}
