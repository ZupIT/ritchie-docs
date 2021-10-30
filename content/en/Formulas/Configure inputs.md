---
title: Configure Inputs
weight: 35
description: "In this section, you will find information about a formula config.json file"
---

---

## **What is the config.json file?**

The **config.json** file contains the formula's input parameters. It allows the CLI to know what data to ask the user when he runs the command in the terminal to process the formula correctly.

These input parameters are made up of the following fields:

- **dockerImageBuilder**: A docker image builder (according to the programming language chose at the formula creation).
- **dockerVolumes**: List of local volumes you want to mount in the docker run container.
- **inputs**: The formula inputs parameters list.
- **requireLatestVersion**: A boolean, indicating the need (or not) of the formula to run in the last available version of a repository.

```text
{
  "dockerImageBuilder": "dockerImage",
  "dockerVolumes": [],
  "inputs": [],
  "requireLatestVersion": false,
}
```

## **Docker volume mapping configuration**

For each volume that will be mapped, you must inform its origin and destination, using a colon **":"** as a separator.

#### **Example:**
The source directory being **`/home/user-name/folder`** and the destination directory **`/mount/folder`**
```text
{
    "dockerVolumes": [
        "/home/user-name/folder:/mount/folder"
    ],
}
```

## **Input parameter configuration**

Each input parameter is composed of the following fields:

### **Mandatory fields**

- `name`: variable name to extract.

{{% alert color="warning" %}}

Once an input value is informed on Ritchie CLI, it is saved as a **local variable** during the formula execution.

The variable **name** will be convert **uppercase** as the **local variable name**.

{{% /alert %}}

> A good practice is to add a **_`RIT_`** suffix to each **`input name`** to avoid having conflicts with local variables.
>
> **Example: `rit_file_name` --&gt; `RIT_FILE_NAME`**

- `type`:
  - **text** _(string)_.
  - **bool** _(boolean)_.
  - **password** _(hidden string on CLI)_.
  - **multiselect** list predefined values, it is possible to select multiple values _(string)_.
  - **credentials** _(specific type, check out more on [**use crendential as formula inputs**]({{< ref path="Credentials/Use credentials as formula inputs" >}}))_.
  - **dynamic** _(associated with the optional `request_info` field below)_.
  - **path:** enables the autocomplete to inform a path to a folder or a file _(string)_.
- `label`: text appearing on the CLI, asking for the input.

#### **Input example with mandatory fields:**

```text
{
      "label": "Type your name:",
      "name": "rit_name",
      "type": "text",
}
```

#### **Input example with the multiselect type:**

```text
{
      "label": "Choose one or more days: ",
      "name": "rit_days",
      "type": "multiselect",
      "required": true,
      "items": [
           "Monday",
           "Tuesday",
           "Wednesday",
           "Thursday",
           "Friday",
           "Saturday",
           "Friday"
      ]
}
```

### **Some observations regarding the **`multiselect`** type**

1. To select one of the options with the `multiselect` type, 
- Press the `space` key (the `enter` key will move to the next input, if any).

2. The options selected in the `multiselect` type field will return a string with:
- The options separated by pipe (`|`) and without space example: `Monday | Wednesday | Friday`

3. Use the `required` field as `true`, otherwise, if no option is selected, the local variable will be saved as `undefined`.

#### **Parameter example using the autocomplete type:**

```text
{
      "label": "Type the path to the folder with your file:",
      "name": "rit_path",
      "type": "path"
}
```

### **Optional fields**

- `default`: default input value (if value is **null**).

```text
{
      "label": "Type your name:",
      "name": "rit_name",
      "type": "text",
      "default": "Dennis"
}
```

{{% alert color="info" %}}

You also can make this default configuration with the default flag, which allows you to attribute default values configured on the formula.

In case of fields without a default value, the flag will keep asking for this inputs that must be configured on your config.json file.

{{% /alert %}}

- `required`: Boolean that indicates if the input value is required or optional.

```text
{
      "label": "Type your name:",
      "name": "rit_name",
      "type": "text",
      "required": true
}
```

- `tutorial`: Input helper message _[? for help]_

```text
{
      "label": "Type your name:",
      "name": "rit_name",
      "type": "text",
      "tutorial": "We are expecting you to write your name (ex: John)"
}
```

- `items`: List of input variable options.

```text
{
      "label": "Type your name:",
      "name": "rit_name",
      "type": "text",
      "items": [
            "Dennis",
            "John",
            "Bill"
      ]
}
```

- `cache`: Saves former input values.
  - `active`: If the cache is enabled or not.
  - `qty`: Amount of values to store.
  - `newLabel`: Text appearing on the CLI asking for new input.

```text
{
      "label": "Type your name:",
      "name": "rit_name",
      "type": "text",
      "cache": {
            "active": true,
            "qty": 5,
            "newLabel": "Type another name:"
      }
}

```

- `condition`: It shows an input if the given condition succeeds.
  - `variable`: The variable name used on a previous input for comparison.
  - `operator`: A logical operator to compare. Supports **`==`**, **`!=`**, **`<`**, **`>`**, **`<=`** and **`>=`**.
  - `value`: The desired value to compare to.

```text
{
      "label": "Type your name:",
      "name": "rit_name",
      "type": "text",
      "default": "Dennis"
},
{
      "condition": {
            "variable": "rit_name",
            "operator": "!=",
            "value": "Dennis"
      }
      "label": "What is your date of birth?",
      "name": "rit_date_of_birth",
      "type": "text",
}
```

- `pattern`: Configure the input value validation.
  - `regex`: The regex pattern to validate the input.
  - `mismatchText`: An error message when the input doesn't match the regex pattern.

```text
{
      "label": "What is your age",
      "name": "rit_age",
      "type": "text",
      "pattern": {
            "regex": "[0-9]",
            "mismatchText": "Only a integer value is allowed here (ex: 20)"
      }
}
```

{{% alert color="warning" %}}

The **`dynamic input`** type will be **deprecated** in the **next releases**.

{{% /alert %}}

- `requestInfo`: A configuration to get the dynamic input type.
  - `url`: An URL to consume a GET service that will return a list of objects.
  - `jsonPath`: A JSON path where the variable extracts a returned list for every object, see `"jsonPath": $['user']['name']` (Check out [**how the JSON path works**](https://goessner.net/articles/JsonPath/)).

```text
{
      "label": "Type your name:",
      "name": "rit_name",
      "type": "text",
      "requestInfo": {
            "url": "https://my-url.com",
            "jsonPath": $['user']['name']
      }
}
```

{{% alert color="info" %}}

Each formula can contain as many inputs as necessary, as well as any association of the above fields.

{{% /alert %}}

### **Conditional input example with Regex pattern:**

```text
"inputs": [
    {
      "label": "Select a system:",
      "name": "rit_system",
      "type": "text",
      "items": [
        "LINUX",
        "MACOS",
        "WINDOWS"
      ],
      "required": true,
      "tutorial": "Select a System from the list."
    },
    {
      "condition": {
        "variable":"rit_system",
        "operator":"==",
        "value":"LINUX"
      },
      "label": "Select a LINUX OS:",
      "name": "rit_linux_os",
      "type": "text",
      "items": [
        "UBUNTU",
        "FEDORA",
        "CENTOS"
      ],
      "pattern": {
        "regex": "UBUNTU|FEDORA|CENTOS",
        "mismatchText": "Invalid option"
      },
      "required": false,
      "tutorial": "Select an Linux Operating System from the list."
    }
  ]
```

{{% alert color="warning" %}}

Once an input is informed on Ritchie CLI, it is saved as a **local variable** during the formula execution.

{{% /alert %}}
