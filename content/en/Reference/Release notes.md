---
title: Release Notes
weight: 8
description: >-
  In this section, you will find Ritchie's Release Notes.
---

{{% release/group %}}
{{% release/item type="feature"  date="July 2021" %}}
Add **input flag support** to all core commands.

Add **rit update workspace** core command to enable workspace updates after **git pull** on local repositories.

Add path status to **rit list workspace** core command.

Add the option to create a new workspace with the **rit create formula**  core commands (when informed path doesn't exist).

{{% /release/item %}}
 

{{% release/item type="fix" date="July 2021" %}}
Update formula execution with Docker to avoid creating files with owner root.

Add support for Docker newest and oldest version for MacOS and WSL users
{{% /release/item  %}}


{{% release/item type="chore" date="July 2021" %}}
Add a check to avoid using workspace names with spaces or special characters.

Add functional tests to check core commands behaviour on Ubuntu, Windows and macOS runners.

README and Contributing Guide section improvements.

Add **security** section.
{{% /release/item  %}}

{{% release/item type="docs"  date="June 2021" %}}
Documentation migration from Gitbook to Hugo.
{{% /release/item  %}}
{{% /release/group %}}
 
Check out more on [**Release Notes**](https://github.com/ZupIT/ritchie-cli/releases).
 