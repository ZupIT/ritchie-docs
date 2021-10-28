---
title: How to group a formula
weight: 90
description: >-
  In this section, you will find a tutorial on how to use the formula aggregation concept.
---

In this tutorial, the idea is to create a formula to execute another formula inside it. 

> See more information on how to run formula inside other on [**groups formulas**]({{< ref path="Formulas/Group formulas" >}}) section.

Here, we will group at least two formulas:

* **`rit math sum numbers`** (level 1).
* **`rit math multiply numbers`** (TODO).

{{% alert color="info" %}}

Command suggestion: **`rit math calculate`**

{{% /alert %}}

## **Inputs**

This formula must have (at least) three input parameters. See below:

1. Number one (`RIT_NUMBER_ONE`). 
2. Number two (`RIT_NUMBER_TWO`).
3. Operation (`RIT_OPERATION`).

## How can you do that? 

{{% alert color="info" %}}

This is the same for all programming languages.

{{% /alert %}}

Search for the `config.json` file of your formula and replace it the **`inputs`** field for the block below: 

```  "inputs": [
    {
      "label": "Number one : ",
      "name": "rit_number_one",
      "type": "text"
    },
    {
      "label": "Number two : ",
      "name": "rit_number_two",
      "type": "text"
    },
    {
      "label": "Operation : ",
      "name": "rit_operation",
      "type": "text",
      "items": [
        "sum",
        "multiplication"
      ]
    }
  ]
```
## **Step by step** 

Follow the steps below to create your formula:

### **Step 1: Extract all inputs parameters**
Search for the **`main`** file of tour formula and extract all the inputs before using them to call your formula's method. See some code example below:

{{< tabs id="T1" >}}
{{% tab name="Python" %}}
```#!/usr/bin/python3
import os

from formula import formula

number_one = int(os.environ.get("RIT_NUMBER_ONE"))
number_two = int(os.environ.get("RIT_NUMBER_TWO"))
operation = os.environ.get("RIT_OPERATION")

formula.run(number_one, number_two, operation)
```
{{% /tab %}}

{{% tab name="Golang" %}}
```
package main

import (
	"formula/pkg/formula"
	"os"
)

func main() {
	numberOne := os.Getenv("RIT_NUMBER_ONE")
	numberTwo := os.Getenv("RIT_NUMBER_TWO")
	operation := os.Getenv("RIT_OPERATION")

	formula.Formula{
		NumberOne: numberOne,
		NumberTwo: numberTwo,
		Operation: operation,
	}.Run()
}
```
{{% /tab %}}

{{% tab name="Shell" %}}
```
#!/bin/bash

# shellcheck source=/dev/null
. "$(dirname "$0")"/formula/formula.sh --source-only

runFormula
```
{{% /tab %}}
{{< /tabs >}}


{{% alert color="warning" %}}

This file follows the **`main.*`** nomenclature for most languages, except Node that it calls **`index.js`**.

{{% /alert %}}

### **Step 2: Implement the formula's operation**

Run the rit formula according to the selected operation: 

* **multiply** must call the `rit math multiply numbers` formula;
* **sum** must call the `rit math sum numbers` formula.

Search for the **`formula`** file of your formula and implement the method performing the operation of your automation. See some code examples: 

{{< tabs id="T1" >}}
{{% tab name="Python" %}}
```#!/usr/bin/python3
import os
import json

def run(number_one, number_two, operation):
    if operation == "sum":
        input_flag_cmd = f"rit python math sum numbers --rit_number_one={number_one} --rit_number_two={number_two}"

    elif operation == "multiplication":
        input_flag_cmd = f"rit python math multiply numbers --rit_number_one={number_one} --rit_number_two={number_two}"

    else:
        print("Unexpected operation")

    os.system(f'{input_flag_cmd}')
```
{{% /tab %}}

{{% tab name="Golang" %}}
```
package formula

import (
	"fmt"
	"log"
	"os/exec"
)

type Formula struct {
	NumberOne string
	NumberTwo string
	Operation string
}

func (h Formula) Run() {
	cmdLine := exec.Command("", "")

	switch h.Operation {
	case "sum":
		cmdLine = exec.Command(
			"rit",
			"math",
			"sum",
			"numbers",
			fmt.Sprintf("--rit_number_one=%s", h.NumberOne),
			fmt.Sprintf("--rit_number_two=%s", h.NumberTwo),
		)
	case "multiplication":
		cmdLine = exec.Command(
			"rit",
			"math",
			"multiply",
			"numbers",
			fmt.Sprintf("--rit_number_one=%s", h.NumberOne),
			fmt.Sprintf("--rit_number_two=%s", h.NumberTwo),
		)
	default:
		fmt.Print("Unexpected operation type:", h.Operation)
	}

	out, err := cmdLine.CombinedOutput()
	if err != nil {
		log.Fatalf("cmd.Run() failed with %s\n", err)
	}

	fmt.Printf(string(out))

}
```
{{% /tab %}}

{{% tab name="Shell" %}}
```
#!/bin/sh
runFormula() {
  if [ "sum" = "$RIT_OPERATION" ]; then
    rit math sum numbers --rit_number_one=$RIT_NUMBER_ONE --rit_number_two=$RIT_NUMBER_TWO
  elif [ "multiplication" = "$RIT_OPERATION" ]; then
    rit math multiply numbers --rit_number_one=$RIT_NUMBER_ONE --rit_number_two=$RIT_NUMBER_TWO
  else
    echo "Unexpected operation type: $RIT_OPERATION"
  fi
}
```
{{% /tab %}}
{{< /tabs >}}

{{% alert color="warning" %}}

Depending on the language, it can be necessary add some dependencies in the related files (`pom.xml` for **Java**, `requirements.txt` for **Python**, `package.json` for **Node**, `go.mod` for **Golang**, etc).

{{% /alert %}}

### **Step 3: Test the formula on your terminal**

- **Multiply test**
```
~ rit math calculate
? Number one : 1
? Number two : 2
? Operation: multiplication
The multiplication is 2
```

- **Sum test**
```
~ ~ rit math calculate
? Number one : 1
? Number two : 2
? Operation: sum
The sum is 3
```

{{% alert color="info" %}}

If you want to test your formula more, see some suggestions below:
* Add more operations.
* Add the option to inform any quantity of numbers as inputs.

{{% /alert %}}
