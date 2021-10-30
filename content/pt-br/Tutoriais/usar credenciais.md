---
title: Como usar credenciais do GitHub
weight: 86
description: 'Nesta seção, você vai encontrar o tutorial para usar credenciais no Ritchie.'
---

Neste tutorial, a ideia é criar uma fórmula que vai retornar um JSON contendo as credenciais do Github.

O tutorial configura os parâmetros de entrada dentro do arquivo **config.json**, mas executar a fórmula sem informá-los usando `prompt` ou `stdin`(serão extraídos automaticamente). Você encontrará todas as informações necessárias na seção de [**configurar inputs**]({{< ref path="Fórmulas/Arquivo config" >}}).

{{% alert color="info" %}}

Sugestão de comando: **`rit github get user`**.

{{% /alert %}}

## **Parâmetros de entrada**

Essa fórmula deverá conter (pelo menos) três parâmetros de entrada. Veja como abaixo:

1. Username (`RIT_GITHUB_USER`). 
2. Token (`RIT_GITHUB_TOKEN`).
3. Email (`RIT_GITHUB_EMAIL`).

## Como fazer isso? 

{{% alert color="info" %}}

Essa parte é comum para todas as linguagens de programação.

{{% /alert %}}

Procure pelo arquivo `config.json` da sua fórmula e substitua o campo **`inputs`** pelo bloco abaixo:

```"inputs": [
    {
        "name": "rit_github_user",
        "type": "CREDENTIAL_GITHUB_USERNAME"
    },
    {
        "name": "rit_github_token",
        "type": "CREDENTIAL_GITHUB_TOKEN"
    },
    {
        "name": "rit_github_email",
        "type": "CREDENTIAL_GITHUB_EMAIL"
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

username = os.environ.get("RIT_GITHUB_USER")
token = os.environ.get("RIT_GITHUB_TOKEN")
email = os.environ.get("RIT_GITHUB_EMAIL")

formula.run(username, token, email)
```
{{% /tab %}}

{{% tab name="Java" %}}
```
package com.ritchie;

import com.ritchie.formula.Formula;

public class Main {

  public static void main(String[] args) {
    String username = System.getenv("RIT_GITHUB_USER");
    String token = System.getenv("RIT_GITHUB_TOKEN");
    String email = System.getenv("RIT_GITHUB_EMAIL");
    Formula formula = new Formula(username, token, email);
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
)

func main() {
	username := os.Getenv("RIT_GITHUB_USER")
	token := os.Getenv("RIT_GITHUB_TOKEN")
  email := os.Getenv("RIT_GITHUB_TOKEN")

	formula.Formula{
		Username: username,
		Token:    token,
		Email:    email,
	}.Run()
}
```
{{% /tab %}}

{{% tab name="Node" %}}
```
const run = require("./formula/formula")

const USERNAME = process.env.RIT_GITHUB_USER
const TOKEN = process.env.RIT_GITHUB_TOKEN
const EMAIL = process.env.RIT_GITHUB_EMAIL

run(USERNAME, TOKEN, EMAIL)
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

import json

class Github:
	username = 'username'
	token = 'token'
	email = 'email'

def run(username, token, email):
    # Create object
    github = Github()
    github.username = username
    github.token = token
    github.email = email

    # Convert to JSON string
    github_json = json.dumps(github.__dict__)

    # Print json string
    print(github_json)
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

{{% tab name="Golang" %}}
```
package formula

import (
	"bytes"
	"encoding/json"
	"log"
)

type Formula struct {
	Username string
	Token    string
	Email    string 
}

func (h Formula) Run() {
	response, err := json.Marshal(h)
	if err != nil {
		log.Printf("Error", h)
	}

	var prettyJSON bytes.Buffer
	error := json.Indent(&prettyJSON, response, "", "\t")
	if error != nil {
		log.Println("JSON parse error:", error)
	}

	log.Println("Github Credentials:", string(prettyJSON.Bytes()))
}
```
{{% /tab %}}

{{% tab name="Node" %}}
```
function Run(username, token, email) {
    console.log("Credential Github")
    console.log("username: " + username)
    console.log("token: " + token)
    console.log("email: " + email)
}

const formula = Run
module.exports = formula
```
{{% /tab %}}
{{< /tabs >}}

{{% alert color="warning" %}}

Dependendo da linguagem, pode ser necessário adicionar algumas dependências nos arquivos relacionados (`pom.xml` para **Java**, `requirements.txt` para **Python**, `package.json` para **Node**, `go.mod` para **Golang**, etc).

{{% /alert %}}

### **Passo 3: Teste a fórmula no terminal**

- **Teste sem credenciais configuradas**
```
~ rit github get user
? Provider key not found, please provide a value for github username:  ******
? Provider key not found, please provide a value for github token:  ******
? Provider key not found, please provide a value for github email:  ******
{"username": "Dennis", "token": "123456", "email": "dennis.ritchie@zup.com.br"}
```

- **Teste com credenciais configuradas**
```
~ rit github get user 
{"username": "Dennis", "token": "123456", "email": "dennis.ritchie@zup.com.br"}
```

{{% alert color="info" %}}

Se você quiser incrementar essa fórmula, veja algumas sugestões abaixo: 
* Desenvolva alguma operação Github manipulando essas credenciais.
* Codifique uma fórmula que permitirá ao usuário criar um repositório no Github.
* Codifique uma fórmula que permitirá ao usuário fazer um **add**, **commit** e **push** usando apenas um comando.
* Codifique uma fórmula que permitirá ao usuário gerar uma **release** do repositório Github informado.

{{% /alert %}}


## **Próximos passos** 

👉 Se você completou o segundo tutorial, vá para o terceiro [**Como usar os inputs condicionais?**]({{< ref path="Tutoriais/usar inputs condicionais" >}}).
