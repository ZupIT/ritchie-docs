---
title: CLI installation for Windows
weight: 12
description: 'In this section, you will find how to install Ritchie for Windows.'
---

---

To install **the latest version of Ritchie** on Windows, you have to download Ritchie's installer and run it on your terminal.

## **Step 1: Download the installer**

You can download Ritchie:

- Using this link to the [**latest version**](https://commons-repo.ritchiecli.io/latest/ritchiecli.msi);
- Or any version you want: just paste the URL on your browser replacing the `{VERSION}` field according to [**the repository's project tags**](https://github.com/ZupIT/ritchie-cli/tags):

```url
https://commons-repo.ritchiecli.io/{VERSION}/installer/ritchiecli.msi
```

{{% alert color="info" %}}

To download version 2.12.0 use the following URL:

```url
https://commons-repo.ritchiecli.io/2.10.0/installer/ritchiecli.msi
```

{{% /alert %}}

- Or with `Winget`:

```bash
winget install Ritchie-CLI
```
If you don't have winget installed by default on your pc, go to Microsoft store search for winget and install it or maybe you just need to update it.

When you finish, follow the instructions on your terminal after running the `rit` command.

{{% alert color="info" %}}

If you prefer, you also can proceed with the[ **manual installation**.]({{< ref path="Getting started/Manual installation" >}}).

{{% /alert %}}

## **Step 2: Verify the installation**

Confirm if your installation went well, run the command below:

```text
rit --version
```

If everything's configured, the terminal will return Ritchie's current version.