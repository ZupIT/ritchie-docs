---
title: Core Commands
weight: 75
description: >-
  In this section, you will find more details about commands that can be used though input flags.
---

---

## Core Commands with input flags

{{% alert color="info" %}}

This flags are supported since Ritchie's 2.8 release.

{{% /alert %}}

### Available flags

### Init command

rit init

```text
rit init --sendMetrics="yes" --addCommons="yes" --runType="local"
```

### Credentials commands

rit set credential

```text
rit set credential --provider=github --fields=username,token --values=Dennis,123456
```

rit delete credential

```text
rit delete credential --provider=github
```

### Environment commands

rit set env

```text
rit set env --env=prod
```

rit delete env

```text
rit delete env --env=prod
```

### Formula commands

rit list formula

```text
rit list formula --name=repo_name
```

{{% alert color="info" %}}

If you need to list formulas from every repository you have added, use the flag 'ALL'.

{{% /alert %}}

```text
rit list formula --name=ALL
```

rit rename formula

```text
rit rename formula --oldName='rit group old' --newName='rit group new'
```

{{% alert color="info" %}}

When more than one workspace has the old formula, an extra interaction via a prompt for choosing the workspace is executed by Ritchie.

{{% /alert %}} 

### Repo commands

rit add repo

```text
rit add repo --name=Zup --provider=Github --repoUrl=https://github.com/ZupIT/ritchie-formulas-zup --tag=2.8.9 --token=1324efg
```

{{% alert color="info" %}}

When the version flag is not passed, ritchie automatically searches for the latest version

{{% /alert %}}

rit delete repo

```text
rit delete repo --name=repo_name
```

rit update repo

```text
rit update repo --name="commons" --version="2.0.0"
```

### Workspace Commands

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
