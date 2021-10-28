---
title: How to use conditional inputs
weight: 88
description: >-
  In this section, you will find a tutorial on how to use condition inputs on Ritchie.
---

Here, the idea is to create a formula on Ritchie that will return the tool selected by the user according to its profile.

> You'll find more information about the **conditional field** on the [**config.json inputs**]({{< ref path="Formulas/Configure inputs" >}}) section.


{{% alert color="info" %}}

Command suggestion: **`rit get tools`**.

{{% /alert %}}

## Inputs

This formula must have (at least) three input parameters. See below:

1. Name (`RIT_NAME`). 
2. Profile (`RIT_PROFILE`).
3. Profile tool (`RIT_TOOL`).

The formula inputs must follow the diagram below:

![](/shared/ritchie-conditional-inputs.png)

## How can you do that? 

{{% alert color="info" %}}

This is the same for all programming languages.

{{% /alert %}}

Search for the `config.json` file of your formula and replace it the **`inputs`** field for the block below: 


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

## **Step by step** 

Follow the steps below to create your formula:

### **Step 1: Extract all inputs parameters**
Search for the **`main`** file of tour formula and extract all the inputs before using them to call your formula's method. See some code example below:

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

This file follows the **`main.*`** nomenclature for most languages, except Node that it calls **`index.js`**.

{{% /alert %}}

### **Step 2: Implement the formula's operation**

Search for the **`formula`** file of your formula and implement the method performing the operation of your automation. See some code examples: 

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

Depending on the language, it can be necessary add some dependencies in the related files (`pom.xml` for **Java**, `requirements.txt` for **Python**, `package.json` for **Node**, `go.mod` for **Golang**, etc).

{{% /alert %}}

### **Step 3: Test the formula on your terminal**

- **Test with prompt**
```
~ rit get tools
? Type the professional name: Dennis
? Select the professional profile: BACK-END
? Which tool this BACK-END professional needs to install: DOCKER
Welcome to Dennis
He is our new BACK-END professional.
Ritchie will install DOCKER for him automatically.
```

- **Test with input flags**
```
~ rit get tools --rit_name="Dennis" --rit_profile="BACK-END" --rit_tool="DOCKER"
Welcome to Dennis
He is our new BACK-END professional.
Ritchie will install DOCKER for him automatically.
```

{{% alert color="info" %}}

If you want to test your formula more, see a suggestion below:
* Install the selected tool according to the computer OS.

{{% /alert %}}


## **Next step** 

👉 If you've completed the second tutorial, go to the fourth [**How to group formulas**]({{< ref path="Tutorials/group a formula" >}}).
