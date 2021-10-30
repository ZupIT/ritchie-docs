---
title: Run Formula
weight: 24
description: 'In this section, you will find a path to how run formulas using Ritchie.'
---

---

## **How to run formulas?**

There are **two ways** to run formulas on Ritchie:
 
1. **Locally**
2. **Using Docker**

The **default formulas execution method** is defined during the initialization step with the **`rit init`** command. You can change this setting by running the following command:

```text
rit set formula-runner
```

![](/shared/rit-run-formula.gif)

### **1. Locally**

To run a formula locally, it is necessary to have installed on your computer the formula programming languages dependencies used to create the formula.

- **Example:** A formula written in **Java** will need **Java installed** on the computer, so it will be able to run locally.

### **2. Through Docker**

All formulas can run regardless the programming language used from the moment you have **`DOCKER`** installed and running.

{{% alert color="info" %}}

For more information about this execution, check out the [**"Hello World" formula section** ]({{< ref path="Formulas/Hello world formula" >}}).

{{% /alert %}}

{{% alert color="warning" %}}

 **Docker user on MacOS:**
To avoid the **'Error: exit status 1'**, you have to **disable** the Cloud Experience, depending on your version.

See how:
Access on Docker:
 - Preferences > Command Line> Enable cloud experience.

 ![](/shared/ios-docker.PNG)

{{% /alert %}}

### **3. Local & Docker Flags**

You can force Ritchie CLI to execute a formula with a specific method using flags.

* The **`--local`** flag will execute a formula with locally (if the default method is Docker).
* The **`--docker`** flag will execute a formula with Docker (if the default method is local).

### 4. Containers with Ritchie

{{% alert color="warning" %}}

All formulas templates contain a **Dockerfile** which creates a container with **Ritchie CLI** installed.

{{% /alert %}}

## **Next steps**

To keep learning about formulas:

👉 Go to [**Hello World formula**]({{< ref path="Formulas/Hello world formula" >}}) to see different ways to run a formula on Ritchie.

👉 Go to the [**create formulas**]({{< ref path="Formulas/Create formulas" >}}) section to understand how to create your first automation with Ritchie.
