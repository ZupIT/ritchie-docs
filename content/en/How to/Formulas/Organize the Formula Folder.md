---
title: Organize the formula folder
weight: 33
description: 'In this section, you will find how to organize Ritchie's formula folder.'
---

---

## What is the formula folder?

This folder contains the files with the formula's behavior. 

{{% alert color="warning" %}}

The folder structure defines the command tree, so **it's not indicated to update** folders names or include more files and/or folders, **if not** in the **src/\*** folder.

{{% /alert %}}

Each programming language has its own specificities, but the formula's structure is almost always the same, no matter what language is used, and will contain:

| File | Description |
| :--- | :--- |
| `config.json` | file to configure the formula inputs. |
| `main file` | file to extract local variables. |
| `pkg/formula file` | file to implement the formula operation. |
| `Dockerfile` | file to build docker images. |
| `README file` | file to explain what the formula does. |
| `Makefile file` | file to compile the formula's code \(_will be deprecated 03/2021_\). |
| `build.sh file` | file to compile the formula's code in shell. |
| `metadata.json file` | file to tag the formula's information. |
| `set_unmask.sh file` | file used by the Makefile file. |
| `help.json files` | file to configure formula helper messages on the CLI. |

You can find all [**languages templates**](https://github.com/ZupIT/ritchie-formulas/tree/master/templates/create_formula/languages) on the ritchie-formulas repository.



### Formula folder examples

{{< tabs name="T0" >}}
{{% tab name="Golang" %}}
![](/go%20%281%29%20%281%29.png)

To change the formula's behavior for this language, you'll have at least to update the following files:

* **config.json:** Update the inputs configurations.
* **main.go:** Extract the inputs and call the formula's methods \(coded on **formula/\***\).
* **formula/\*:** Code the formula's behavior.
{{% /tab %}}

{{% tab name="Java" %}}
![](/java%20%282%29%20%282%29.png)

To change the formula's behavior for this language, you'll have at least to update the following files:

* **config.json:** Update the inputs configurations.
* **main.java:** Extract the inputs and call the formula's methods \(coded on **formula/\***\).
* **formula/\*:** Code the formula's behavior.
{{% /tab %}}

{{% tab name="Node" %}}
![](/node%20%283%29%20%283%29.png)

To change the formula's behavior for this language, you'll have at least to update the following files:

* **config.json:** Update the inputs configurations.
* **index.js:** Extract the inputs and call the formula's methods \(coded on **formula/\***\).
* **formula/\*:** Code the formula's behavior.
{{% /tab %}}

{{% tab name="Python" %}}
![](/python%20%282%29.png)

To change the formula's behavior for this language, you'll have at least to update the following files:

* **config.json:** Update the inputs configurations.
* **main.py:** Extract the inputs and call the formula's methods \(coded on **formula/\***\).
* **formula/\*:** Code the formula's behavior.
{{% /tab %}}

{{% tab name="Shell" %}}
![](/shell%20%282%29%20%281%29.png)

To change the formula's behavior for this language, you'll have at least to update the following files:

* **config.json:** Update the inputs configurations.
* **main.sh:** Extract the inputs and call the formula's methods \(coded on **formula/\***\).
* **formula/\*:** Code the formula's behavior.
{{% /tab %}}
{{< /tabs >}}

{{% alert color="warning" %}}
The structures defines the command, so **it's not indicated to update** folders names or include more files/folders **if not** in the **src/\*** folder.
{{% /alert %}}
