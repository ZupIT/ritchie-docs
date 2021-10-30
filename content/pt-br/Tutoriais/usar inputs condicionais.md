---
title: Como usar inputs condicionais
weight: 88
description: >-
  Nesta seção, você vai encontrar o tutorial de como usar inputs condicionais no Ritchie.
---

Neste tutorial, a ideia é criar uma fórmula que vai retornar a ferramenta selecionada pelo usuário de acordo com seu perfil. 

> Veja mais informações na seção [**sobre o arquivo config.json**]({{< ref path="Fórmulas/Arquivo config" >}}).

{{% alert color="info" %}}

Sugestão de comando: **`rit get tools`**.

{{% /alert %}}

## **Parâmetros de entrada**

Essa fórmula deverá conter (pelo menos) três parâmetros de entrada. Veja como abaixo:

1. Name (`RIT_NAME`). 
2. Profile (`RIT_PROFILE`).
3. Profile tool (`RIT_TOOL`).

Os parâmetros de entrada da fórmula precisam seguir o diagrama abaixo:

![](/shared/ritchie-conditional-inputs.png)

## **Como fazer isso?** 

{{% alert color="info" %}}

Essa parte é comum para todas as linguagens de programação.

{{% /alert %}}

Procure pelo arquivo `config.json` da sua fórmula e substitua o campo **`inputs`** pelo bloco abaixo:

```"inputs": [
    {
      "label": "Type the professional name: ",
      "name": "rit_name",
      "type": "text",
      "cache": {
        "active": true,
        "newLabel": "Type other name: ",
        "qty": 3
      }
    },
    {
      "label": "Select the professional profile: ",
      "name": "rit_profile",
      "type": "text",
      "items": [
        "BACK-END",
        "FRONT-END",
        "OPERATION",
        "QA"
      ]
    },
    {
      "condition": {
        "variable":"rit_profile",
        "operator":"==",
        "value":"BACK-END"
      },
      "label": "Which tool this BACK-END professional needs to install: ",
      "name": "rit_tool",
      "type": "text",
      "items": [
        "INTELLIJ",
        "DATAGRIP",
        "DOCKER"
      ]
    },
    {
      "condition": {
        "variable":"rit_profile",
        "operator":"==",
        "value":"FRONT-END"
      },
      "label": "Which tool this FRONT-END professional needs to install: ",
      "name": "rit_tool",
      "type": "text",
      "items": [
        "ATOM",
        "CHROME DEV TOOLS",
        "NPM"
      ]
    },
    {
      "condition": {
        "variable":"rit_profile",
        "operator":"==",
        "value":"OPERATION"
      },
      "label": "Which tool this OPERATION professional needs to install: ",
      "name": "rit_tool",
      "type": "text",
      "items": [
        "JENKINS",
        "CIRCLE-CI",
        "TERRAFORM"
      ]
    },
    {
      "condition": {
        "variable":"rit_profile",
        "operator":"==",
        "value":"QA"
      },
      "label": "Which tool this QA professional needs to install: ",
      "name": "rit_tool",
      "type": "text",
      "items": [
        "SELENIUM",
        "POSTMAN",
        "CUCUMBER"
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

name = os.environ.get("RIT_NAME")
profile = os.environ.get("RIT_PROFILE")
tool = os.environ.get("RIT_TOOL")

formula.run(profile, tool)
```
{{% /tab %}}

{{% tab name="Java" %}}
```
package com.ritchie;

import com.ritchie.formula.Formula;

public class Main {

  public static void main(String[] args) {
    String username = System.getenv("RIT_GIT_USER");
    String token = System.getenv("RIT_GIT_TOKEN");
    String email = System.getenv("RIT_GIT_EMAIL");
    Formula formula = new Formula(username, token, email);
    System.out.println(formula.run());
  }
}
```
{{% /tab %}}
{{< /tabs >}}


{{% alert color="warning" %}}

Esse arquivo segue a nomenclatura **`main.*`** para a maioria das linguagens, exceto para o Node que chama **`index.js`**.

{{% /alert %}}

### **Passo 2: Implemente a operação da fórmula**

Procure pelo arquivo **`formula`** da sua fórmula e implemente o método realizando a operação da sua automação. Veja alguns exemplos de códigos:

{{< tabs id="T1" >}}
{{% tab name="Python" %}}
```#!/usr/bin/python3

def run(name, profile, tool):
    printf("Welcome to {name}")
    printf("He is our new {profile} professional.")
    printf("Ritchie will install {tool} for him automatically.")
```
{{% /tab %}}

{{% tab name="Java" %}}
```
package com.ritchie.formula;

import com.google.gson.*; # Add GSON dependency on POM.XML

public class Formula {

  private String username;
  private String token;
  private String email;

  public String run() {
    Gson gson = new Gson();
    return gson.toJson(this, Formula.class);
  }

  public Formula(String username, String token, String email) {
    this.username = username;
    this.token = token;
    this.email = email;
  }

  public String getUsername() {
    return username;
  }

  public void setUsername(String username) {
    this.username = username;
  }

  public String getToken() {
    return token;
  }

  public void setToken(String token) {
    this.token = token;
  }

  public String getEmail() {
    return email;
  }

  public void setEmail(String email) {
    this.email = email;
  }
}
```
{{% /tab %}}
{{< /tabs >}}

{{% alert color="warning" %}}

Dependendo da linguagem, pode ser necessário adicionar algumas dependências nos arquivos relacionados (`pom.xml` para **Java**, `requirements.txt` para **Python**, `package.json` para **Node**, `go.mod` para **Golang**, etc).

{{% /alert %}}

### **Passo 3: Teste a fórmula no terminal**

- **Teste com prompt**
```
~ rit get tools
? Type the professional name: Dennis
? Select the professional profile: BACK-END
? Which tool this BACK-END professional needs to install: DOCKER
Welcome to Dennis
He is our new BACK-END professional.
Ritchie will install DOCKER for him automatically.
```

- **Teste com input flags**
```
~ rit get tools --rit_name="Dennis" --rit_profile="BACK-END" --rit_tool="DOCKER"
Welcome to Dennis
He is our new BACK-END professional.
Ritchie will install DOCKER for him automatically.
```

{{% alert color="info" %}}

Se você quiser incrementar essa fórmula, veja a sugestão abaixo: 
* Instale a ferramenta selecionada de acordo com o SO do computador.

{{% /alert %}}


## **Próximos passos** 

👉 Se você completou o terceiro tutorial, vamos para o quarto [**Como agrupar uma fórmula?**]({{< ref path="Tutoriais/agrupar uma formula" >}}).
