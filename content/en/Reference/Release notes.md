---
title: Release Notes
weight: 8
description: >-
  In this section, you will find Ritchie's Release Notes.
---

{{% release/group %}}
{{% release/item type="feature"  date="May 2021" %}}

Add command **'rit list formulas'**.

Add a force-update option to execute the last formula version when enabled. 

Add lib to support Ritchie-CLI internationalization. 

Add the first part of the formula output feature.

Detect new repo version using cache.

Create configuration to force formula's execution in the latest version.

Add configuration to mount volumes via **config.json**.

Create a formula and check **config.json** file to see the release tag.

{{% /release/item %}}
 

{{% release/item type="fix" date="May 2021" %}}
Fix files created by the formula belonging to the root user.

Change the invocation command from **'docker'** to **'com.docker.cli'** when the runtime env is Windows or MacOS. 

Fix formula's outputs.

{{% /release/item  %}}


{{% release/item type="chore" date="May 2021" %}}
Add tests and support flags for **rit delete repo**.

Save and reuse repo credentials for private repositories.

Add a friendlier error message on update repository.

Test refactor of flag package.

Add tests with testify for delete repository.

Remove stale bot.

Improve metrics extracted by input flags.

Test refactor of a flag package.
{{% /release/item  %}}

{{% release/item type="docs"  date="May 2021" %}}
Documentation migration from Gitbook to Hugo.
{{% /release/item  %}}
{{% /release/group %}}
 
Check out Ritchie's [**Release Notes**](https://github.com/ZupIT/ritchie-cli/releases).
 