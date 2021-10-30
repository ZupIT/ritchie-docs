---
title: Como agrupar uma fórmula
weight: 90
description: >-
  Nesta seção, você vai encontrar um tutorial para usar o conceito de encapsulamento de fórmula.
---


Neste tutorial, a ideia é criar uma fórmula que irá agrupar uma outra fórmula dentro dela.

>Para mais informações sobre agrupamento de fórmulas, veja a seção de [**encapsular fórmulas**]({{< ref path="Fórmulas/Encapsular fórmulas" >}}).

Vamos agrupar pelo menos duas fórmulas:

* **`rit math sum numbers`** (Nível 1).
* **`rit math multiply numbers`** (TODO).
 

{{% alert color="info" %}}

Sugestão de comando: **`rit math calculate`**

{{% /alert %}}

## **Parâmetros de entrada**

Essa fórmula deverá conter (pelo menos) três parâmetros de entrada. Veja como abaixo:

1. Number one (`RIT_NUMBER_ONE`). 
2. Number two (`RIT_NUMBER_TWO`).
3. Operation (`RIT_OPERATION`).

## Como fazer isso? 

{{% alert color="info" %}}

Essa parte é comum para todas as linguagens de programação.

{{% /alert %}}

Procure pelo arquivo `config.json` da sua fórmula e substitua o campo **`inputs`** pelo bloco abaixo:

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

Esse arquivo segue a nomenclatura **`main.*`** para a maioria das linguagens, exceto para o Node que chama **`index.js`**.

{{% /alert %}}

### **Passo 2: Implemente a operação da fórmula**

Execute a fórmula rit de acordo com a operação selecionada: 

* **multiply** deve chamar a fórmula `rit math multiply numbers`;
* **sum** deve chamar a fórmula `rit math sum numbers`.

Procure pelo arquivo **`formula`** da sua fórmula e implemente o método realizando a operação da sua automação. Veja alguns exemplos de códigos:

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

Dependendo da linguagem, pode ser necessário adicionar algumas dependências nos arquivos relacionados (`pom.xml` para **Java**, `requirements.txt` para **Python**, `package.json` para **Node**, `go.mod` para **Golang**, etc).

{{% /alert %}}

### **Passo 3: Teste a fórmula no terminal**

- **Teste multiplicando**
```
~ rit math calculate
? Number one : 1
? Number two : 2
? Operation: multiplication
The multiplication is 2
```

- **Teste somando**
```
~ ~ rit math calculate
? Number one : 1
? Number two : 2
? Operation: sum
The sum is 3
```

{{% alert color="info" %}}

Se você quiser testar mais sua fórmula, veja algumas sugestões abaixo: 
* Adicione mais operações.
* Adicione a opção de informar qualquer quantidade de números como entradas.

{{% /alert %}}