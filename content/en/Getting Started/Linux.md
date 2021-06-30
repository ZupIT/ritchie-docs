---
title: CLI installation for Linux
weight: 8
description: 'In this section, you will find how to install Ritchie for Linux.'
---

---

### **Requirements**

If you want to efficiently use Ritchie on Linux with version **`2.0.5 and earlier`**, we recommend to install the following element configured:

* The **make** command

Once you have it, just run the command below at your terminal:

## Step 1: Installing command

### Latest Version

To install the latest version, copy and paste the command below and run it on your terminal:

```text
curl -fsSL https://commons-repo.ritchiecli.io/install.sh | bash
```

{{% alert color="info" %}}
Note: To install Ritchie on servers or Docker containers (without `sudo` user), use the following command:

```text
curl -fsSL https://commons-repo.ritchiecli.io/install.sh | sed -e 's/sudo//g' | bash
```

{{% /alert %}}

If you prefer, you also can follow with the[ **manual installation**.](/getting-started/manual-installation/)

### Packages

To download a specific package or version, just paste the URL on your browser replacing the `{VERSION}` field according to [the repository's project tags](https://github.com/ZupIT/ritchie-cli/tags):

#### Red Hat Package Manager

```text
https://commons-repo.ritchiecli.io/{VERSION}/installer/ritchie.rpm
```

#### Debian

```text
https://commons-repo.ritchiecli.io/{VERSION}/installer/ritchie.deb
```

#### Arch Linux

The `tar.gz` package is available on this [Arch Linux user repository](https://aur.archlinux.org/packages/ritchie-cli/) page ([repository reference](https://github.com/avelino/ritchie-cli-archpack)).

{{% alert color="info" %}}
If you prefer, you also can follow with the[ **manual installation**.](/docs-ritchie/getting-started/manual-installation/)
{{% /alert %}}

## Step 2: Verify installation

You can confirm if your installation went well by running this command:

```text
rit --version
```

If everything's configured, the terminal will return Ritchie's current version.
