---
title: How to use GitHub credentials
weight: 86
description: 'In this section, you will find a tutorial on how to use credentials on Ritchie.'
---

In this tutorial you will learn how to create a formula on Ritchie that will return a JSON with Github credentials.

The tutorial configures the inputs inside the **config.json** file, but run the formula without informing them as `prompt` or `stdin` (they will be extracted automatically). You'll find more information in the [**input configuration**]({{< ref path="Formulas/Configure inputs" >}}) section.

{{% alert color="info" %}}

Command suggestion: **`rit github get user`**.

{{% /alert %}}

## **Inputs**

This formula must have (at least) three input parameters. See below:

1. Username (`RIT_GITHUB_USER`).
2. Token (`RIT_GITHUB_TOKEN`).
3. Email (`RIT_GITHUB_EMAIL`).

## How can you do that? 

{{% alert color="info" %}}

This is the same for all programming languages.

{{% /alert %}}

Search for the `config.json` file of your formula and replace it the **`inputs`** field for the block below: 

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
## **Step by step** 

Follow the steps below to create your formula:

### **Step 1: Extract all inputs parameters**
Search for the **`main`** file of tour formula and extract all the inputs before using them to call your formula's method. See some code example below:

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

This file follows the **`main.*`** nomenclature for most languages, except Node that it calls **`index.js`**.
{{% /alert %}}

### **Step 2: Implement the formula's operation**

Search for the **`formula`** file of your formula and implement the method performing the operation of your automation. See some code examples: 

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

Depending on the language, it can be necessary add some dependencies in the related files (`pom.xml` for **Java**, `requirements.txt` for **Python**, `package.json` for **Node**, `go.mod` for **Golang**, etc).

{{% /alert %}}

### **Step 3: Test the formula on your terminal**

- **Test without configured credentials**
```
~ rit github get user
? Provider key not found, please provide a value for github username:  ******
? Provider key not found, please provide a value for github token:  ******
? Provider key not found, please provide a value for github email:  ******
{"username": "Dennis", "token": "123456", "email": "dennis.ritchie@zup.com.br"}
```

- **Test with configured credentials**
```
~ rit github get user 
{"username": "Dennis", "token": "123456", "email": "dennis.ritchie@zup.com.br"}
```

{{% alert color="info" %}}

If you want to test your formula more, see some suggestions below:
* Develop some Github operation by manipulating these credentials.
* Code a formula which will allow the user to create a repository on Github. 
* Code a formula which will allow the user to **add**, **commit** and **push** using only one command. 
* Code a formula which will allow the user to generate a **release** of the informed Github repository.

{{% /alert %}}


## **Next steps** 

👉 If you've completed the second tutorial, go to the third [**How to use conditional inputs**]({{< ref path="Tutorials/conditional inputs" >}}).