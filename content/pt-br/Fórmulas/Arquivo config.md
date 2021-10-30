---
title: Configurar inputs
weight: 35
description: Nesta seção, você vai encontrar mais informações sobre o arquivo config.json.
---

---

## **O que é um arquivo config (config.json file)?**

O arquivo **config.json** contém os parâmetros de entrada da fórmula. Ele permite que o CLI saiba quais dados devem ser pedidos ao usuário quando ele executa o comando no terminal, a fim de que processe a fórmula corretamente.

Essas entradas são feitas para os seguintes campos:

- **dockerImageBuilder**: Uma imagem para buildar o docker (de acordo com a linguagem de programação escolhida para criar a fórmula).
- **dockerVolumes**: Lista de volumes locais que você deseja montar no container de execução em docker.
- **inputs**: Lista com os parâmetros de entrada de uma fórmula.
- **requireLatestVersion**: Um parâmetro booleano que indica a necessidade (ou não) de uma fórmula ser executada na última versão do repositório.

```text
{
  "dockerImageBuilder": "dockerImage",
  "dockerVolumes": [],
  "inputs": [],
  "requireLatestVersion": false,
}
```

## **Configuração dos volumes do Docker a serem mapeados**

Para cada volume que será mapeado, você deve informar a origem e o destino, utilizando dois pontos **":"** como separador. 

#### Exemplo:
O diretório de origem sendo **`/home/user-name/folder`** e o diretório de destino **`/mount/folder`**
```text
{
    "dockerVolumes": [
        "/home/user-name/folder:/mount/folder"
    ],
}
```

## **Configuração dos parâmetros de entrada**

Cada parâmetro de entrada é composto pelos seguintes campos:

### Campos obrigatórios

- `name`: nome da variável para extração.

{{% alert color="warning" %}}

Uma vez que o valor de um parâmetro de entrada é informado no Ritchie CLI, ele é salvo como uma **variável local** durante a execução da fórmula.

O **nome** da variável será convertida em **maiúscula** como o **nome da variável local**.

{{% /alert %}}

> Uma boa prática é adicionar o sufixo **_`RIT_`** para cada **`input name`** para evitar conflitos com variáveis locais.
> **Exemplo: `rit_file_name` --&gt; `RIT_FILE_NAME`**

- `type`:
  - **text** _(string)_.
  - **bool** _(boolean)_.
  - **password** _(string escondida no CLI)_.
  - **multiselect** lista valores predefinidos, é possível selecionar vários valores _(string)_.
  - **credentials** _(tipo específico, veja mais sobre [**nesse tutorial**]({{< ref path="Tutoriais/usar inputs condicionais.md" >}}))_.
  - **dynamic** _(associado ao campo opcional`request_info`)_.
  - **path:** habilita o `autocomplete` para o usuário informar o passo para uma pasta ou um arquivo _(string)_.
- `label`: texto que aparecerá no CLI para pedir o input ao usuário.

#### **Exemplo de parâmetro de entrada com campos obrigatórios:**

```text
{
      "label": "Type your name:",
      "name": "rit_name",
      "type": "text",
}
```

#### **Exemplo de parâmetro de entrada com o tipo multiselect:**

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

### **Algumas observações sobre o tipo **`multiselect`****

1. Para selecionar uma das opções com o tipo `multiselect`: 
 - Aperte a chave `space` (a chave `enter` irá mover para o próximo parâmetro de entrada, se houver).

2. As opções selecionadas no campo do tipo `multiselect` retornam:
 - Uma string com as opções separadas por barra (`|`) e sem espaço, por exemplo: `Monday | Wednesday | Friday`.

3. Use o campo `required` como `true`, caso contrário, se não houver uma opção selecionada, a variável local será salva como `undefined`.

#### **Exemplo de parâmetro de entrada usando o tipo autocomplete:**

```text
{
      "label": "Type the path to the folder with your file:",
      "name": "rit_path",
      "type": "path",
}
```

### **Campos opcionais**

- `default`: Valor padrão do parâmetro (se valor é nulo).

```text
{
      "label": "Type your name:",
      "name": "rit_name",
      "type": "text",
      "default": "Dennis"
}
```

{{% alert color="info" %}}

Você pode ainda fazer essa configuração default com a flag default, que te permite atribuir valores default configurados na fórmula.

Caso não haja campos com valor default, a flag continuará solicitando os parâmetros de entrada que devem ser configurados no seu arquivo config.json.

{{% /alert %}}

- `required`: Boolean que indica se um campo é obrigatório ou opcional.

```text
{
      "label": "Type your name:",
      "name": "rit_name",
      "type": "text",
      "required": true
}
```

- `tutorial`: Campo de ajuda para o parâmetro de entrada _[? for help]_

```text
{
      "label": "Type your name:",
      "name": "rit_name",
      "type": "text",
      "tutorial": "We are expecting you to write your name (ex: John)"
}
```

- `items`: Lista de opções para o parâmetro.

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

- `cache`: Salva os valores de parâmetros de entrada anteriores.
  - `active`: Se o cache é habilitado ou não.
  - `qty`: A quantidade de valor armazenada no cache.
  - `newLabel`: Texto que aparece no CLI para pedir um novo input ao usuário.

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

- `condition`: Esse parâmetro só aparece se a condicional funcionar.
  - `variable`: O nome da variável usada em um parâmetro anterior para comparação.
  - `operator`: O operador lógico usado para comparar. Suporta **`==`**, **`!=`**, **`<`**, **`>`**, **`<=`** e  **`>=`**.
  - `value`: O valor que você deseja usar para comparação.

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

- `pattern`: Configura a validação de um parâmetro de entrada.
  - `regex`: O modelo regex para validar o parâmetro.
  - `mismatchText`: A mensagem de erro se o parâmetro de entrada seja invalidado pelo regex.

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

O tipo de **`entrada dinâmico`** será **depreciado** nas **próximas liberações**.

{{% /alert %}}

- `requestInfo`: Configuração para ter o parâmetro de entrada do tipo dinâmico.
  - `url`: Uma URL que consome o serviço GET e é responsável por retornar a lista de objetos.
  - `jsonPath`: O caminho da variável para extrair da lista retornada uma variável de cada objeto. Exemplo: `"jsonPath": $['user']['name']` (Veja mais sobre [**como funciona esse path json**](https://goessner.net/articles/JsonPath/)).

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

Cada fórmula contém quantos parâmetros de entrada forem necessários, assim como qualquer associação nos campos acima.

{{% /alert %}}

#### **Exemplo de parâmetros de entrada com campo condicional e padrão Regex:**

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

Uma vez que o valor de um parâmetro de entrada é informado no Ritchie CLI, ele é salvo como uma **variável local** durante a execução da fórmula.

{{% /alert %}}
