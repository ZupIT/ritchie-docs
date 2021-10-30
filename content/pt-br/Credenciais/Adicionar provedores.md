---
title: Adicionar provedores
weight: 59
description: Nesta seção, você vai encontrar como adicionar provedores ao Ritchie.
---

---

É possível configurar o Ritchie para adicionar novos provedores no seu espaço de trabalho.

Para fazer isso:
1. Selecione a opção "**Add a new**" rodando o comando **`rit set credential`**:

```text
? Select your provider Add a new
? Define your provider name: Provider_Name
? Define your field name: (ex.:token, secretAccessKey) token
? Select your field type: secret
? Add more credentials to this provider? no
? token: *
✔ Provider_Name credential saved!
```

As informações que o Ritchie solicita são:

* **Provider name:** Nome do novo provedor. Você pode nomear de acordo com sua preferência.
* **Field name:** Nome da credencial que está nesse provedor.
* **Field type:** Tipo de valor dessa credencial. Ele pode ser: **plain text** ou **secret**. 

Ao terminar essa configuração, você pode configurar as credenciais seguindo as instruções acima. 

{{% alert color="warning" %}}

Esse provedor, assim como as suas informações, serão salvas de forma permanente no Ritchie. No entanto, você pode adicionar quantos provedores quiser. 

{{% /alert %}}
