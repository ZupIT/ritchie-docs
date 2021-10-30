---
title: Share formulas
weight: 47
description: 'In this section, you will find how to share formulas on Ritchie.'
---

---

## **How to share?** 

Once a formula repository has been published, other users can add it locally from its **URL** to access its formulas.

Example: [**`https://github.com/ZupIT/ritchie-formulas`**](https://github.com/ZupIT/ritchie-formulas)

To add a new repository on Ritchie, it is necessary to run the command:

```text
rit add repo
```

Once the repository has been added, Ritchie will use the selected release on the repository to access the available formulas.

![](/shared/rit-share-formula.gif)

{{% alert color="warning" %}}

If the formula repository is **private**, the user will have to inform his Github/Gitlab token.

{{% /alert %}}

## **How to see the repo latest version?**

{{% alert color="info" %}}

This feature is available from Ritchie 2.2 version.

{{% /alert %}}

On Ritchie, you can check out new formula commands and if there is a new version of some repository you added locally.
Follow these steps:

**Step 1.** Run the help command **`rit --help`**. The system will return a list with the group of available repositories.

```text
(new version 2.12.1) commons repo commands:
  beagle      Beagle commands
  bitbucket   Manage bitbucket objects
  clean-swift Manage clean-swift objects
  docker      Manipulate Docker objects
  git         Manipulate Git objects
  github      Manipulate GitHub objects
  gitlab      Manipulate GitLab objects
  istio       Istio Service Mesh commands
  jupyter     Manage jupyter objects
  kafka       Kafka commands
  kubernetes  Manipulate kubernetes objects
  publish     Publish command
  scaffold    Manipulate scaffold objects
  xcode       Manage xcode objects
```

**Step 2.** If you prefer, run the **`rit list repo`** command, that returns informations about the imported repositories, like the current version and the last available version.

### **How to see the repo formulas?**

{{% alert color="info" %}}

This feature is available from Ritchie 2.11 version.

{{% /alert %}}

When you work with various formula groups, it may be hard to remember all the available commands.

If you want to list formulas from a specific repository, follow the steps below:

1. Run the list command **` rit list formula`**. The system will return a list with the available groups of repositories and the  '**ALL**' option.

```text
? Repository:
  ALL
> repo-name-1
  repo-name-2
  ```

2. Select the repository you want (or ALL), the system will return a list with the commands and a description defined on the **`help.json`** of each formula.

```text
? Repository: repo-name-1
COMMAND                                 DESCRIPTION
rit aws add terraform-eks               Generate terraform AWS eks
rit aws add terraform-vpc               Generate terraform AWS vpc
rit aws apply terraform                 Apply terraform on AWS
rit aws clean bucket                    Clean bucket AWS
rit aws create bucket                   Create bucket AWS
rit aws delete bucket                   Delete AWS objects

There are 6 formulas
```

### **How can I update?**

To update the version of any repository, you have to run the command below informing the repository and the version you wish to be updated:

```text
rit update repo
```

## **Next steps**
Keep configuring your formula:

👉 Check out how to [**use credentials**]({{< ref path="Credentials/Use credentials as formula inputs" >}}) with your formulas.

👉 Check out our [**list of commands**]({{< ref path="Reference/List of commands and flags" >}}) to see the available automations on our community repo.
