---
title: Definir credenciais
weight: 55
description: Nesta seção, você vai encontrar como definir credenciais no Ritchie.
---

---

Você pode definir as credenciais do Ritchie para não precisar informar os mesmos dados diversas vezes no terminal. 

Para fazer isso, rode o comando abaixo:

```text
rit set credential
```

O terminal irá retornar essa mensagem:

```text
? Select your provider [Use arrows to move, type to filter]
> kubeconfig
  ansible
  aws
  github
  gitlab
  jenkins
  Add a new
```

Depois que você escolheu um dos provedores disponíveis, o Ritchie irá solicitar que você preencha os seguintes campos:

```text
? Select your provider github
? username: DennisRitchie
? email: dennis.ritchie@zup.com.br
? token: 
✔ Github credential saved!
```

{{% alert color="info" %}}

Para saber mais sobre os arquivos editáveis das fórmulas e como **manipular as credenciais definidas na sessão como parâmetros de input** das fórmulas (no caso, inputs no config.json), veja a seção de [**Fórmulas**]({{< ref path="Fórmulas/Arquivo config" >}}).

{{% /alert %}}
