---
title: CLI installation for Linux
weight: 8
description: 'In this section, you will find how to install Ritchie for Linux.'
---

---

### **Requirements** (only for versions prior to 2.0.6)
 
* The **make** command. 

## **Step 1: Installing command**

### Latest Version

To install the latest version, run the command below in the terminal:

```text
curl -fsSL https://commons-repo.ritchiecli.io/install.sh | bash
```

{{% alert color="warning" %}}
To install Ritchie on servers or Docker containers (without `sudo` user), use the following command:

```text
curl -fsSL https://commons-repo.ritchiecli.io/install.sh | sed -e 's/sudo//g' | bash
```

{{% /alert %}}

{{% alert color="info" %}}

If you prefer, you also can install using the [ **manual installation**.]({{< ref path="Getting started/Manual installation" >}}).

{{% /alert %}}

### Packages

To download a specific package or version, just paste the URL on your browser replacing the **`{VERSION}`** field according to [**the repository's project tags**](https://github.com/ZupIT/ritchie-cli/tags):

#### Red Hat Package Manager

```url
https://commons-repo.ritchiecli.io/{VERSION}/installer/ritchie.rpm
```

{{% alert color="info" %}}

To download version 2.12.0 use the following URL:

```url
https://commons-repo.ritchiecli.io/2.12.0/installer/ritchie.rpm
```

{{% /alert %}}

#### Debian

```url
https://commons-repo.ritchiecli.io/{VERSION}/installer/ritchie.deb
```
{{% alert color="info" %}}

To download version 2.12.0 use the following URL:

```url
https://commons-repo.ritchiecli.io/2.12.0/installer/ritchie.deb
```

{{% /alert %}}

#### Arch Linux

The `tar.gz` package is available on this [**Arch Linux user repository**](https://aur.archlinux.org/packages/ritchie-cli/) page ([**repository reference**](https://github.com/avelino/ritchie-cli-archpack)).

## **Step 2: Verify installation**

Confirm if your installation went well by running this command:

```text
rit --version
```

If everything's configured, the terminal will return Ritchie's current version.
