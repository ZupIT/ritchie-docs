---
title: CLI installation for Macos
weight: 10
description: 'In this section, you will find how to install Ritchie for MacOs.'
---

---

### **Requirements** (only for versions prior to 2.0.6)

* The **make** command ([**Using "make" on macOS**](https://stackoverflow.com/questions/1469994/using-make-on-os-x)).
* **md5sum** tools.

{{% alert color="warning" %}}

To install **md5sum** with _**Homebrew**_ , use: `brew install md5sha1sum`

To install **md5sum** with _**MacPorts**_ , use: `sudo port install md5sha1sum`

{{% /alert %}}

## **Step 1: Installing command**

### First option

To install the latest version, run the command below in the terminal:

```text
curl -fsSL https://commons-repo.ritchiecli.io/install.sh | bash
```

{{% alert color="info" %}}

Note: To install Ritchie on servers or Docker containers (without `sudo` user), use the following command:

```text
curl -fsSL https://commons-repo.ritchiecli.io/install.sh | sed -e 's/sudo//g' | bash
```

{{% /alert %}}

{{% alert color="info" %}}

If you prefer, you also can follow with the[ **manual installation**.]({{< ref path="Getting started/Manual installation" >}}).

{{% /alert %}}

### Second option

You can also **download the Ritchie CLI package** through the command line below, to **install it manually.**

```text
curl --output ~/Desktop/Ritchie-CLI-macos-installer-x64.pkg --location https://commons-repo.ritchiecli.io/latest/Ritchie-CLI-macos-installer-x64.pkg
```

## **Step 2: Verify the installation**

Confirm if your installation worked, run the command below:

```text
rit --version
```

If everything's configured, the terminal will return Ritchie's current version.
