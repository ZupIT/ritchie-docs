---
title: Extract input variables in a formula
weight: 37
description: 'In this section, you will find information about a formula main class file'
---

---

## **What is the main file?**

{{% alert color="info" %}}

The main file is used to extract the **inputs** asked in the config.json file, saved as **local variables.**

- Inputs are extracted by the field **name** informed on the config.json file **UPPERCASE**.

{{% /alert %}}

This file is also where the formula functions, manipulating the input parameters, are called to perform the operation and/or automation of the formula.

### Main file examples

Check out the examples below, there is always an existing **`formula`** class with a **`Run()`** function:

{{< tabs id="T1" >}}
{{% tab name="main.go" %}}
```text
func main() {
	input1 := os.Getenv("INPUT_TEXT")
	input2 := os.Getenv("INPUT_LIST")
	input3, _ := strconv.ParseBool(os.Getenv("INPUT_BOOLEAN"))
	input4 := os.Getenv("INPUT_PASSWORD")

	formula.Formula{
		Text:     input1,
		List:     input2,
		Boolean:  input3,
		Password: input4,
	}.Run(os.Stdout)
}
```
{{% /tab %}}

{{% tab name="Main.java" %}}
```text
public class Main {

  public static void main(String[] args) {

    String inputText = System.getenv("INPUT_TEXT");
    boolean inputBoolean = Boolean.parseBoolean(System.getenv("INPUT_BOOLEAN"));
    String inputList = System.getenv("INPUT_LIST");
    String inputPassword = System.getenv("INPUT_PASSWORD");

    Formula formula = new Formula(
      inputText, 
      inputBoolean, 
      inputList, 
      inputPassword
    );
    
    formula.Run();
  }
}
```
{{% /tab %}}

{{% tab name="index.js" %}}
```text
const INPUT1 = process.env.INPUT_TEXT
const INPUT2 = process.env.INPUT_BOOLEAN
const INPUT3 = process.env.INPUT_LIST
const INPUT4 = process.env.INPUT_PASSWORD

run(INPUT1, INPUT2, INPUT3, INPUT4)
```
{{% /tab %}}

{{% tab name="main.py" %}}
```text
input1 = os.environ.get("INPUT_TEXT")
input2 = os.environ.get("INPUT_BOOLEAN")
input3 = os.environ.get("INPUT_LIST")
input4 = os.environ.get("INPUT_PASSWORD")

formula.Run(input1, input2, input3, input4)
```
{{% /tab %}}

{{% tab name="main.sh" %}}
```text
//Inputs are not even necessary here, as Shellscript get values from local variables directly.

runFormula '$SAMPLE_TEXT' $SAMPLE_LIST '$SAMPLE_BOOL''$SAMPLE_PASSWORD'
```
{{% /tab %}}
{{< /tabs >}}
