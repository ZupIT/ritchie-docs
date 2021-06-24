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

### Comando de inicialização do Ritchie

rit init

```text
rit init --sendMetrics="yes" --addCommons="yes" --runType="local"
```

### Comando para criar fórmula

rit create formula

```text
rit create formula --name="rit group verb noun" --language="go" --workspace="Default"
```

### Comandos de Credenciais

rit set credential

```text
rit set credential --provider=github --fields=username,token --values=Dennis,123456
```

rit delete credential

```text
rit delete credential --provider=github
```

### Comandos de Ambiente

rit set env

```text
rit set env --env=prod
```

rit delete env

```text
rit delete env --env=prod
```

### Comandos de Fórmulas

rit list formula

```text
rit list formula --name=repo_name
```

{{% alert color="info" %}}

Se você precisar listar as fórmulas de todos os repositórios adicionados, use a flag '**ALL**'.

{{% /alert %}} 

```text
rit list formula --name=ALL
```

rit rename formula

```text
rit rename formula --oldName='rit group old' --newName='rit group new'
```

{{% alert color="info" %}}

Quando mais de um workspace possui o mesmo nome da fórmula antiga, uma interação extra via prompt para escolha do workspace é executada pelo Ritchie

{{% /alert %}}

### Comandos de Repo

rit add repo

```text
rit add repo --name=Zup --provider=Github --repoUrl=https://github.com/ZupIT/ritchie-formulas-zup --tag=2.8.9 --token=1324efg
```

{{% alert color="info" %}}

Quando não é passada a flag de versão, o ritchie busca automaticamente a última versão

{{% /alert %}}

rit delete repo

```text
rit delete repo --name=repo_name
```

rit update repo

```text
rit update repo --name="commons" --version="2.0.0"
```

### Comandos de workspace

rit add workspace

```text
rit add workspace --name=workspace_name --path=path/to/workspace
```

rit delete workspace

```text
rit delete workspace --name=workspace_name
```

rit update workspace

```text
rit update workspace --name=workspace_name
```
