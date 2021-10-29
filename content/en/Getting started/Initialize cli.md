---
title: Initialize CLI
weight: 17
description: 'In this section, you will find how to initialize Ritchie CLI.'
---

--- 

See the steps below to initialize the CLI: 

## **Step 1: Initialization**

Run the following command to initialize Ritchie:

```text
rit init
```

This command will ask **three information**:

1. If the user **wants to contribute anonymously** to Ritchie metrics.
2. If the user **wants to add the community** formulas locally.
3. Which **execution method** the user wants to use by **default** (local or docker). [**formula execution method**]({{< ref path="Formulas/Run formula" >}}).

![](/shared/rit-init.gif)

After this, the command will create all the necessary configuration's files.

## **Step 2: Verify Initialization**

### 1. Commons repository

If you added the community formulas repository, verify the import using the following command:

```text
rit list repo
```

This command will return all formulas repositories the user has local access to.

![](/shared/rit-list-repo.gif)

### 2. Ritchie folder

You can check if the **`.rit`** folder has been created on your **`$HOME`** directory.

{{% alert color="info" %}}

All operations done using Ritchie will be saved in this **.rit** folder (credentials, repos, metrics...).

{{% /alert %}}
