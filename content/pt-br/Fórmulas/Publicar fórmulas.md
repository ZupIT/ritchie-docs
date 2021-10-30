---
title: Publicar fórmulas
weight: 46
description: Nesta seção, você vai encontrar como publicar uma fórmula no Ritchie.
---

---

## **Como publicar?**

Existe uma fórmula no Ritchie que permite você criar/atualizar o repositório de fórmulas no Github e/ou Gitlab.

### **Premissas**

{{% alert color="warning" %}}

Para publicar um repositório, é necessário configurar as credenciais do Github e/ou Gitlab usando o comando **`rit set credential.`**

{{% /alert %}}

## **Publicando seu repositório**

Você pode usar uma fórmula que foi criada no repositório da comunidade para fazer:

- Inicializar em um repositório local do Git (se necessário).
- Criar repositório no Github e/ou Gitlab.
- Gerar a release de uma nova versão do repositório.
- Adicionar um repositório nos repositórios locais do Ritchie (usando o comando **`rit add repo`**).

{{% alert color="info" %}}

Além disso, se o repositório já existir, a fórmula irá fazer o commit de um novo código e gerar uma nova release informada antes de atualizar os repositórios do Ritchie (usando o comando **`rit update repo`**)

{{% /alert %}}

```text
rit publish repo
```

Você deverá informar 5 tipos diferentes de parâmetros de entrada:

1. O **`provedor`** (Github ou Gitlab).
2. A **`privacidade do repositório`**.
3. O **`nome do repositório`**.
4. O **`caminho local do repositório`** que você quer publicar.
5. A **`versão da release`** para ser gerada.

![](/shared/rit-publish-repo.gif)

{{% alert color="warning" %}}

Você pode checar se a publicação deu certo usando o comando **`rit list repo`** e observando se o repositório publicado aparece.

{{% /alert %}}

## **Publicando manualmente**

Para publicar uma fórmula manualmente, você precisa submetê-la no repositório do **Github e/ou Gitlab** seguindo esses passos:

1. Você precisa de um repositório de fórmulas exclusivo no Github e/ou Gitlab. _Ele pode ser criado a partir de um repositório local ou de um repositório clonado._
2. Adicione sua fórmula ao repositório. _Para isso, use o comando **`rit create formula`** ou copie /cole as pastas._
3. Faça o commit e submeta o novo código ao repositório do Github e/ou Gitlab.
4. Gere uma nova release do repositório de fórmulas.

## **Próximos passos**
Continue configurando a sua fórmula:

👉 Veja a seção [**como compartilhar fórmulas**]({{< ref path="Fórmulas/Compartilhar fórmulas" >}}).
