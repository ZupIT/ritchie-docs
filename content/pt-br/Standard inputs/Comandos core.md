---
title: Comandos Core
weight: 75
description: >-
  Nesta seção, você vai encontrar mais detalhes sobre comandos core que podem ser usados via input flags.
---

---

## **Core Commands com input flags**
 
{{% alert color="info" %}}

Estas flags estão disponíveis a partir da versão 2.8 do Ritchie.

{{% /alert %}}

### **Flags disponíveis**

### **Comando de inicialização do Ritchie**

rit init

```text
rit init --sendMetrics="yes" --addCommons="yes" --runType="local"
```

### **Comando para criar fórmula**

rit create formula

```text
rit create formula --name="rit group verb noun" --language="go" --workspace="Default"
```

### **Comandos de credenciais**

rit set credential

```text
rit set credential --provider="github" --fields="username,token" --values="Dennis,123456"
```

rit delete credential

```text
rit delete credential --provider="github"
```

### **Comandos de Ambiente**

rit set env

```text
rit set env --env="prod"
```

rit delete env

```text
rit delete env --env="prod"
```

### **Comandos de Fórmulas**

rit set formula-runner

```text
rit set formula-runner --runner="local"
```

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

rit rename formula

```text
rit rename formula --oldName="rit group old" --newName="rit group new" --workspace="workspace_name"
```


{{% alert color="info" %}}

A flag de workspace é obrigatória quando a fórmula é encontrada em mais de um workspace.

{{% /alert %}}

rit delete formula

```text
rit delete formula --workspace="workspace_name" --formula="rit group verb noun"
```

### **Comandos de Repo**

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

rit update repo

```text
rit update repo --name="commons" --version="2.0.0"
```

### **Comando de Tutorial**

rit tutorial

```text
rit tutorial --enabled=true
```

### **Comandos de workspace**

rit add workspace

```text
rit add workspace --name="workspace_name" --path="path/to/workspace"
```

rit delete workspace

```text
rit delete workspace --name="workspace_name"
```

rit update workspace

```text
rit update workspace --name="workspace_name"
```
