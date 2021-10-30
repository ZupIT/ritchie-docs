---
title: How to manipulate inputs
weight: 84
description: >-
  In this section, you will find a tutorial on how to manipulate basic inputs on Ritchie.
---

This tutorials helps you to create a simple formula, in this case, it will sum two positive numbers.

{{% alert color="info" %}}

Command suggestion: **`rit math sum numbers`**.

{{% /alert %}}

## Inputs

This formula must have (at least) two input parameters. See below:

1. Number one (`RIT_NUMBER_ONE`). 
2. Number two (`RIT_NUMBER_TWO`).

## **How can you do that?**

{{% alert color="info" %}}

This is the same for all programming languages.

{{% /alert %}}

Search for the `config.json` file of your formula and replace it the **`inputs`** field for the block below: 

```"inputs": [
    {
      "label": "Number one : ",
      "name": "rit_number_one",
      "type": "text"
    },
    {
      "label": "Number two : ",
      "name": "rit_number_two",
      "type": "text"
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

formula.run(number_one, number_two)
```
{{% /tab %}}

{{% tab name="Java" %}}
```
package com.ritchie;

import com.ritchie.formula.Formula;

public class Main {

  public static void main(String[] args) {
    String numberOne = System.getenv("RIT_NUMBER_ONE");
    String numberTwo = System.getenv("RIT_NUMBER_TWO");
    Formula formula = new Formula(Integer.valueOf(numberOne), Integer.valueOf(numberTwo));
    System.out.println(formula.run());
  }
}
```
{{% /tab %}}

{{% tab name="Golang" %}}
```
package main

import (
	"formula/pkg/formula"
	"os"
	"strconv"
)

func main() {
	numberOne, _ := strconv.Atoi(os.Getenv("RIT_NUMBER_ONE"))
	numberTwo, _ := strconv.Atoi(os.Getenv("RIT_NUMBER_TWO"))

	formula.Formula{
		NumberOne: numberOne,
		NumberTwo: numberTwo,
	}.Run()
}
```
{{% /tab %}}

{{% tab name="Node" %}}
```
const run = require("./formula/formula")

const NUMBER_ONE = parseInt(process.env.RIT_NUMBER_ONE)
const NUMBER_TWO = parseInt(process.env.RIT_NUMBER_TWO)

run(NUMBER_ONE, NUMBER_TWO) 
```
{{% /tab %}}
{{< /tabs >}}

_Warning: Here is where the conversion from STRING to INT happens, because there is no native **INT** type in the **`config.json`** file._

{{% alert color="warning" %}}

This file follows the **`main.*`** nomenclature for most languages, except Node that it calls **`index.js`**.

{{% /alert %}}

### **Step 2: Implement the formula's operation**

Search for the **`formula`** file of your formula and implement the method performing the operation of your automation. See some code examples: 

{{< tabs id="T1" >}}
{{% tab name="Python" %}}
```#!/usr/bin/python3

def run(number_one, number_two):
    sum = number_one + number_two
    print("The sum is", sum)
```
{{% /tab %}}

{{% tab name="Java" %}}
```
package com.ritchie.formula;

public class Formula {

  private Integer numberOne;
  private Integer numberTwo;

  public String run() {
    Integer sum = numberOne + numberTwo;
    return String.format("The sum is %s", sum);
  }

  public Formula(Integer numberOne, Integer numberTwo) {
    this.numberOne = numberOne;
    this.numberTwo = numberTwo;
  }

  public Integer getNumberOne() {
    return numberOne;
  }

  public void setNumberOne(Integer numberOne) {
    this.numberOne = numberOne;
  }

  public Integer getNumberTwo() {
    return numberTwo;
  }

  public void setNumberTwo(Integer numberTwo) {
    this.numberTwo = numberTwo;
  }
}
```
{{% /tab %}}

{{% tab name="Golang" %}}
```
package formula

import (
	"fmt"
)

type Formula struct {
	NumberOne int
	NumberTwo int
}

func (f Formula) Run() {
	sum := f.NumberOne + f.NumberTwo
	fmt.Println("The sum is", sum)
}
```
{{% /tab %}}

{{% tab name="Node" %}}
```
function Run(numberOne, numberTwo) {
    var sum = numberOne + numberTwo
    console.log("The sum is " + sum)
}

const formula = Run
module.exports = formula
```
{{% /tab %}}
{{< /tabs >}}


### **Step 3: Test the formula on your terminal**

- **Test with prompt**
```
~ rit math sum numbers
? Number one : 1
? Number two : 2
The sum is 3
```

- **Test with input flags**
```
~ rit math sum numbers --rit_number_one="1" --rit_number_two="2" 
The sum is 3
```

{{% alert color="info" %}}

If you want to test your formula more, see some suggestions below:
* Add a validation of the input parameters to return an error to the user if the parameter is not an integer. 
* Allow the user to sum negative numbers with positive ones. 
* Allow the user to digit decimals in addition to integers. 

{{% /alert %}}

## **Next steps** 

👉 If you've completed this first tutorial, let's go to the second one [**How to use GitHub crendentials**]({{< ref path="Tutorials/use github credentials" >}}).
