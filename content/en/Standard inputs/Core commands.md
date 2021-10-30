---
title: Core Commands
weight: 75
description: >-
  In this section, you will find more details about commands that can be used through input flags.
---

---

## **Core Commands with input flags**

{{% alert color="info" %}}

This flags are supported since Ritchie's 2.8 release.

{{% /alert %}}

### **Available flags**

### **Init command**

rit init

```text
rit init --sendMetrics="yes" --addCommons="yes" --runType="local"
```

### **Create formula command**

rit create formula

```text
rit create formula --name="rit group verb noun" --language="go" --workspace="Default"
```

### **Credentials command**

rit set credential

```text
rit set credential --provider="github" --fields="username,token" --values="Dennis,123456"
```

rit delete credential

```text
rit delete credential --provider="github"
```

### **Environment commands**

rit set env

```text
rit set env --env="prod"
```

rit delete env

```text
rit delete env --env="prod"
```

### **Formula commands**

rit set formula-runner

```text
rit set formula-runner --runner="local"
```

rit list formula

```text
rit list formula --name="repo_name"
```

{{% alert color="info" %}}

If you need to list formulas from every repository you have added, use the flag '**ALL**'.

{{% /alert %}}

```text
rit list formula --name="ALL"
```

rit rename formula

```text
rit rename formula --oldName="rit group old" --newName="rit group new" --workspace="workspace_name"
```

{{% alert color="info" %}}

The workspace flag is required when the formula is found in more than one workspace.

{{% /alert %}}

rit delete formula

```text
rit delete formula --workspace="workspace_name" --formula="rit group verb noun"
```

### **Repo commands**

rit add repo

```text
rit add repo --name="demo" --provider="Github" --repoUrl="https://github.com/ZupIT/ritchie-formulas-demo" --tag="2.8.9" --token="1324efg"
```

{{% alert color="info" %}}

When the version flag is not passed, Ritchie automatically searches for the latest version.
The token flag is mandatory when the command is used to add a private repository.

{{% /alert %}}

rit delete repo

```text
rit delete repo --name="repo_name"
```

rit update repo

```text
rit update repo --name="commons" --version="2.0.0"
```

### **Tutorial command**

rit tutorial

```text
rit tutorial --enabled=true
```

### **Workspace commands**

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
