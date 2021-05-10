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