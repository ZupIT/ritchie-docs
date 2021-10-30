---
title: Organize the formula folder
weight: 33
description: In this section, you will find how to organize Ritchie's formula folder.
---

---

## **What is the formula folder?**

This folder contains the files with the formula's behavior.

{{% alert color="warning" %}}

The folder structure defines the command tree, so **it's not indicated to update** folders names or include more files and/or folders, **if not** in the **src/*.** folder.

{{% /alert %}}

Each programming language has its own specificities, but the formula's structure is almost always the same, no matter what language is used, and will contain:

| File | Description |
| :--- | :--- |
| `config.json` | File to configure the formula inputs. |
| `main file` | File to extract local variables. |
| `pkg/formula file` | File to implement the formula operation. |
| `Dockerfile` | File to build docker images. |
| `README file` | File to explain what the formula does. |
| `Makefile file` | File to compile the formula's code (_will be deprecated 03/2021_). |
| `build.sh file` | File to compile the formula's code in shell. |
| `metadata.json file` | File to tag the formula's information. |
| `set_unmask.sh file` | File used by the Makefile file. |
| `help.json files` | File to configure formula helper messages on the CLI. |

- You can find all [**languages templates**](https://github.com/ZupIT/ritchie-formulas/tree/master/templates/create_formula/languages) on the [**ritchie-formulas**](https://github.com/ZupIT/ritchie-formulas) repository.

### **Formula folder examples**

{{< tabs name="T0" >}}
{{% tab name="Golang" %}}
![](/shared/go.png)

To change the formula's behavior for this language, you'll have at least to update the following files:

* **config.json:** Update the _**inputs**_ configurations.
* **main.go:** Extract the inputs and call the formula's methods (coded on **formula/\***).
* **formula/*:** Code the formula's behavior.
* **help.json:** Change command description message.
{{% /tab %}}

{{% tab name="Java" %}} 
![](/shared/java.png)

To change the formula's behavior for this language, you'll have at least to update the following files:

* **config.json:** Update the _**inputs**_ configurations.
* **main.java:** Extract the inputs and call the formula's methods (coded on **formula/\***).
* **formula/*:** Code the formula's behavior.
* **help.json:** Change command description message.
{{% /tab %}}

{{% tab name="Node" %}}
![](/shared/node.png)

To change the formula's behavior for this language, you'll have at least to update the following files:

* **config.json:** Update the _**inputs**_ configurations.
* **index.js:** Extract the inputs and call the formula's methods (coded on **formula/\***).
* **formula/*:** Code the formula's behavior.
* **help.json:** Change command description message.
{{% /tab %}}

{{% tab name="Python" %}}
![](/shared/python.png)

To change the formula's behavior for this language, you'll have at least to update the following files:

* **config.json:** Update the _**inputs**_ configurations.
* **main.py:** Extract the inputs and call the formula's methods (coded on **formula/\***).
* **formula/*:** Code the formula's behavior.
* **help.json:** Change command description message.
{{% /tab %}}

{{% tab name="Shell" %}}
![](/shared/shell.png)

To change the formula's behavior for this language, you'll have at least to update the following files:

* **config.json:** Update the _**inputs**_ configurations.
* **main.sh:** Extract the inputs and call the formula's methods (coded on **formula/\***).
* **formula/*:** Code the formula's behavior.
* **help.json:** Change command description message.
{{% /tab %}}
{{< /tabs >}}
