---
title: Hello World formula
weight: 25
description: >-
  In this section, you will find how to run a "hello-world" formula.
---

---

## **Hello World**

{{% alert color="warning" %}}

Premisse: After you finished installing and initializing Ritchie - now you can  access the hello-world formula to test. You will need to add the [**ritchie-formulas-demo**](https://github.com/ZupIT/ritchie-formulas-demo) repository locally.

{{% /alert %}}

To add the [**ritchie-formulas-demo**](https://github.com/ZupIT/ritchie-formulas-demo) repository locally, you can use the **`rit add repo`** command, or run the command line below:

```text
rit add repo --provider="Github" --name="demo" --repoUrl="https://github.com/ZupIT/ritchie-formulas-demo" --priority=1
```

{{% alert color="info" %}}

  You can also check which repositories you're using with the **`rit list repo`** command.

{{% /alert %}}

Now, check the details of the formula, you can execute this tutorial commands.

## **Premisse: Check the formula's details**

To get details about a formula, you can execute the command using with the **`--help`** flag:.

```text
rit demo hello-world --help
```
It will return all the flags available for the command execution.

## **Scenarios**  
On Ritchie, you have 6 possibilities to run a formula through these flags:

1. Via Prompt
2. Via Prompt e Docker
3. Via Input Flags
4. Via Input Flags e Docker
5. Via Stdin
6. Via Stdin e Docker

You can see them below, choose a case and type the following commands lines.

### **Option 1: With Prompt**

{{% alert color="warning" %}}

  As this formula has been coded using Golang, it is necessary to have Golang installed on your computer to run it locally.

{{% /alert %}}

```text
rit demo hello-world
```
Select an option for each input parameter and see how the magic works:

![](/shared/rit-helloworld-prompt.gif)

This is the default command line execution, that runs the formula locally using **prompt** to inform the input parameters.

### **Option 2: With Prompt and Docker**

You can run the same command using the **--docker** flag pto execute it remotely (on a container), but still using **prompt** to inform the inputs parameters:

```text
rit demo hello-world --docker
```

{{% alert color="warning" %}}

  Docker needs to be installed and running on your computer for this flag to work.
  In that case, you won't need to have Golang installed.

{{% /alert %}}

### **Option 3: With Input Flags**

You can also run the command informing the inputs through flags (you can know which flags are available using the **`--help`** flag when executing a command). This way, inputs parameters are informed directly with the command line.

```text
rit demo hello-world --rit_input_text="Dennis" --rit_input_boolean=true --rit_input_list="everything" --rit_input_password="Ritchie"
```

### **Option 4: With Input flags and Docker**

When you combine both **`input flags`** and the **`--docker`** flag, it is possible to run a command remotely (on a container) with the input parameters directly informed on the command line:

```text
rit demo hello-world --rit_input_text="Dennis" --rit_input_boolean=true --rit_input_list="everything" --rit_input_password="Ritchie" --docker
```

### **Option 5: With Stdin**

You can also run the command with the **`--stdin`** (Standard input) flag. This way, inputs parameters are also informed directly with the command line.

```text
echo '{"rit_input_text":"Dennis", "rit_input_boolean":"true", "rit_input_list":"everything", "rit_input_password":"Ritchie"}' | rit demo hello-world --stdin
```
{{% alert color="warning" %}}

  Ritchie uses the **JSON** format to execute STDIN commands

{{% /alert %}}

### **Option 6: With Stdin and Docker** 

When you combine both **--stdin** and **--docker** flags, it is also possible to run a command remotely (on a container) with the input parameters directly informed on the command line:

```text
echo '{"rit_input_text":"Dennis", "rit_input_boolean":"true", "rit_input_list":"everything", "rit_input_password":"Ritchie"}' | rit demo hello-world --stdin --docker
```
{{% alert color="info" %}}

  Take a look at the formulas repositories [**(ex: ritchie-formulas)**](https://github.com/ZupIT/ritchie-formulas).
  Most of the community formulas are composed of a [**README**](https://github.com/ZupIT/ritchie-formulas#readme) explaining what the command does and how to run it.

{{% /alert %}}

## **Next steps**
- Check out how to [**create a formula** ]({{< ref path="Formulas/Create formulas" >}}).
