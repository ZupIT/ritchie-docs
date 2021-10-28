---
title: Group formulas
weight: 51
description: 'In this section, you will understand how to group formulas on Ritchie.'
---

---

## **What is an aggregation?**

On Ritchie, it is possible to **run formulas inside formulas.** This process is called **Formula aggregation**‌.

This functionality allows you, for example, to make operations in which you need to run consecutive formulas.

Check out on the following topics to understand how works this aggregation.

## **How to group?**

### **1. Premisse**

To group formulas, it is necessary to use **Standard Inputs**. For more information, check out the [**Standard Inputs section**]({{< ref path="Standard inputs" >}}).

### **2. Execution**

When [**implementing a formula**]({{< ref path="Formulas/Configure inputs" >}}), the file where the operation is coded needs to execute a command line associated to a formula.‌

The grouped formula command line needs to be executed using **Standard Inputs**, which means informing the inputs parameters directly on the code.‌

### **3. Example**

The **`rit publish repo`** formula has been implemented using formula aggregation, that you can find its [**formula implementation**](https://github.com/ZupIT/ritchie-formulas/tree/master/publish/repo).

On the example below, you'll find below how this aggregation works on the code part, using **`Input flags`**.

{{% alert color="warning" %}}

- This formula has been implemented using **`Shell`** and the reasoning would be the same for any other programming language.

{{% /alert %}}

```text
runFormula() {
  if [ "Github" == $PROVIDER ]
  then
    echo "🐙 Github provider selected"
    rit github publish repo --privacy=$PRIVACY --project_name=$PROJECT_NAME --workspace_path=$WORKSPACE_PATH --version=$VERSION
  elif [ "Gitlab" == $PROVIDER ]
  then
    echo "🦊 Gitlab provider selected"
    rit gitlab publish repo --privacy=$PRIVACY --project_name=$PROJECT_NAME --workspace_path=$WORKSPACE_PATH --version=$VERSION
  else
    echo "🤖 Unexpected Provider informed. Check it please and try again."
  fi
}
```

Here, according to the input informed by the user, two different formulas can be executed:‌

* **`rit github publish repo`**
* **`rit gitlab publish repo`**

To do so, the grouped formulas inputs parameters are informed dynamically according to the inputs parameters of the main formula (**`rit publish repo`**).

Depending on the operation, the **`input flags`** used for the command could be generated according to other operations performed through the formula execution before executing the grouped formula command line.‌

### **Learn More**

- Check out the [**tutorials**]({{< ref path="Tutorials" >}}) page to apply all Ritchie's concepts you have learned.‌

- Check out our [**list of commands**]({{< ref path="Reference/List of commands and flags" >}}) to see the available automations on our community repository.
