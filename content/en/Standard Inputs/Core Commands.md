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

### Repo commands

rit add repo

```text
rit add repo --name=Zup --provider=Github --repoUrl=https://github.com/ZupIT/ritchie-formulas-zup --tag=2.8.9 --token=1324efg
```

{{% alert color="info" %}}

When the version flag is not passed, ritchie automatically searches for the latest version

{{% /alert %}}

### Formula commands

rit rename formula

```text
rit rename formula --oldName='rit group old' --newName='rit group new'
```

{{% alert color="info" %}}

When more than one workspace has the old formula, an extra interaction via prompt for choosing the workspace is running by Ritchie

{{% /alert %}}
