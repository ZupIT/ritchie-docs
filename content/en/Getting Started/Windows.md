---
title: CLI installation for Windows
weight: 12
description: 'In this section, you will find how to install Ritchie for Windows.'
---

---

To install **the latest version of Ritchie** on Windows, you have to download Ritchie's installer and run it on your terminal.

## Step 1: Download the installer

You can download the Ritchie latest version using this link: [latest version](https://commons-repo.ritchiecli.io/latest/ritchiecli.msi)

Or download any version by pasting this URL on your navigator substituting the `{VERSION}` field according to [the project repository tags](https://github.com/ZupIT/ritchie-cli/tags):

```url
https://commons-repo.ritchiecli.io/{VERSION}/installer/ritchiecli.msi
```

Once you made it, follow the instructions on your terminal after running the `rit` command.

{{% alert color="info" %}}
If you prefer, you also can proceed with the[ **manual installation**.](/docs-ritchie/getting-started/manual-installation/)
{{% /alert %}}

## Step 2: Verify installation

You can confirm if your installation went well by running this command: 

```text
rit --version
```

If everything's configured, the terminal will return Ritchie's current version.
