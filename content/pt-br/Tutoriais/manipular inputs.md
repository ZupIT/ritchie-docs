---
title: Como manipular inputs
weight: 84
description: >-
  Nesta seção, você vai encontrar o tutorial para manipular inputs básicos no Ritchie.
---


Neste tutorial, a ideia é ensinar você a criar uma fórmula simples que, neste caso, irá **somar 2 números positivos**.

{{% alert color="info" %}}

Sugestão de comando: **`rit math sum numbers`**.

{{% /alert %}}

## **Parâmetros de entrada**

Essa fórmula deverá conter (pelo menos) os dois parâmetros de entrada. Veja como abaixo:

1. Number one (`RIT_NUMBER_ONE`). 
2. Number two (`RIT_NUMBER_TWO`).

## Como fazer isso? 
{{% alert color="info" %}}

Essa parte é comum para todas as linguagens de programação.

{{% /alert %}}

Procure pelo arquivo `config.json` da sua fórmula e substitua o campo **`inputs`** pelo bloco abaixo:

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
## **Passo a Passo** 

Siga os passos abaixo para criar a sua fórmula:

### **Passo 1: Extrair os parâmetros de entrada**

Procure pelo arquivo **`main`** da sua fórmula e extraia os parâmetros de entrada antes de usá-los para chamar o método da fórmula. Veja abaixo alguns exemplos de códigos:

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

_Observação: Aqui que é realizado a conversão de STRING para INT pois não existe o tipo **INT** nativo no arquivo **`config.json`** ._

{{% alert color="warning" %}}

Esse arquivo segue a nomenclatura **`main.*`** para a maioria das linguagens, exceto para o Node que chama **`index.js`**.

{{% /alert %}}

### **Passo 2: Implemente a operação da fórmula**

Procure pelo arquivo **`formula`** da sua fórmula e implemente o método realizando a operação da sua automação. Veja alguns exemplos de códigos:

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


### **Passo 3: Teste a fórmula no terminal**

- **Teste com prompt**
```
~ rit math sum numbers
? Number one : 1
? Number two : 2
The sum is 3
```

- **Teste com input flags**
```
~ rit math sum numbers --rit_number_one="1" --rit_number_two="2" 
The sum is 3
```

{{% alert color="info" %}}

Se você quiser incrementar essa fórmula, veja algumas sugestões abaixo: 
* Adicione uma validação dos parâmetros de entrada para retornar um erro ao usuário se o parâmetro não for um inteiro.
* Permita que usuário some números negativos com positivos.
* Permita que o usuário digite números decimais. 

{{% /alert %}}


## **Próximos passos** 

👉 Se você completou o primeiro tutorial, vá para o segundo [**Como usar credenciais do GitHub?**]({{< ref path="Tutoriais/usar credenciais" >}}).
