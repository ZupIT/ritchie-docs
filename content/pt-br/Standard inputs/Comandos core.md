---
title: Comandos Core
weight: 75
description: >-
  Nesta seção, você vai encontrar mais detalhes sobre comandos core que podem ser usados via input flags.
---

---

## Core Commands com input flags

{{% alert color="info" %}}

Estas flags estão disponíveis a partir da versão 2.8 do Ritchie.

{{% /alert %}}

### Flags disponíveis

### Comandos de credenciais

rit set credential

```text
rit set credential --provider="github" --fields="username,token" --values="Dennis,123456"
```

rit delete credential

```text
rit delete credential --provider="github"
```

### Comandos de Ambiente

rit set env

```text
rit set env --env="prod"
```

rit delete env

```text
rit delete env --env="prod"
```

### Comandos de Fórmulas

rit list formula

```text
rit list formula --name="repo_name"
```

{{% alert color="info" %}}

Se você precisar listar as fórmulas de todos os repositórios adicionados, use a flag '**ALL**'.

{{% /alert %}}

```text
rit list formula --name="ALL"
```

{{% alert color="info" %}}

A flag de workspace será obrigatória quando a fórmula for encontrada em mais de um workspace.

{{% /alert %}}

### Comandos de Repo

rit add repo

```text
rit add repo --name="demo" --provider="Github" --repoUrl="https://github.com/ZupIT/ritchie-formulas-demo" --tag="2.8.9" --token="1324efg"
```

{{% alert color="info" %}}

Quando a flag de versão não é passada, o Ritchie busca automaticamente a última versão.
A flag de token é obrigatória quando o comando é usado para adicionar um repositório privado.

{{% /alert %}}

rit delete repo

```text
rit delete repo --name="repo_name"
```
