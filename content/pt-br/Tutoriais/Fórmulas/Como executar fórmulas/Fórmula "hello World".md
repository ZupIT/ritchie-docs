---
title: Fórmula "Hello World"
weight: 26
description: >-
  Nesta seção, você vai encontrar o passo a passo para executar nosso "Hello
  World".
---

---

## Hello World

{{% alert color="warning" %}}
**Premissa**: Depois de finalizar os passos anteriores -  [**instalação**](../../../getting-started/instalacao-cli/) e [**inicialização**](../../../getting-started/inicializacao-cli) -,  para acessar a [**fórmula hello world**](https://github.com/ZupIT/ritchie-formulas/tree/master/demo/hello-world) para testar o Ritchie, será necessário adicionar o repositório [**ritchie-formulas-demo**](https://github.com/ZupIT/ritchie-formulas-demo) localmente.
{{% /alert %}}

Para fazer isso, você pode usar o comando **`rit add repo`**, ou executar a linha de comando abaixo:

```text
echo '{"provider":"Github", "name":"demo", "url":"https://github.com/ZupIT/ritchie-formulas-demo", "priority":1}' | rit add repo --stdin
```

{{% alert color="info" %}}
É possível ainda verificar os repositórios que estão sendo usados na execução do comando com **`rit list repo`**.
{{% /alert %}}

**Agora que você adicionou o repositório de demo, você pode executar os comandos desse tutorial.**

### **Premissa: Confira os detalhes da fórmula**

Para obter os detalhes de uso de uma fórmula, é possível executar o comando usando a flag **`--help`**.

```text
rit demo hello-world --help
```

O retorno informará todas as flags disponíveis para a execução do comando.

**No Ritchie, você tem 6 possibilidades de rodar uma fórmula através dessas flags:**

1. Via Prompt
2. Via Prompt e Docker
3. Via Input Flags
4. Via Input Flags e Docker
5. Via Stdin
6. Via Stdin e Docker

Veja a seguir como você pode utilizar cada uma dessas formas:

### Caso 1: Usando Prompt

{{% alert color="warning" %}}
Como **essa fórmula  foi desenvolvida usando Golang**, é preciso ter **Golang** instalado para conseguir  executá-la **localmente**.
{{% /alert %}}

```text
rit demo hello-world
```

Selecione uma opção para cada parâmetro de entrada e, em seguida, execute a fórmula como no exemplo abaixo:

![rit demo hello-world](/large-gif-1054x366-%20%281%29.gif)

Essa é a execução padrão de linhas de comando no Ritchie, que roda fórmulas localmente através de **prompt** \(interagindo com o CLI no terminal\) para informar os parâmetros de entrada.

### Caso 2: Usando Prompt & Docker

Você pode rodar o mesmo comando usando a flag **--docker** para executar a fórmula remotamente \(em um container\), mas ainda informando os parâmetros de entrada via **prompt**:

```text
rit demo hello-world --docker
```

{{% alert color="warning" %}}
O **Docker** precisa estar instalado e iniciado para conseguir executar comandos usando essa flag.
Nesse caso, não é necessário ter **Golang** instalado.
{{% /alert %}}

### Caso 3: Usando Input Flags

Você também pode executar o comando informando as entradas por meio de flags \(você pode saber quais flags estão disponíveis usando  a flag **`--help`** ao executar um comando\). 

Desta forma, os parâmetros de entradas são informados diretamente na linha de comando.

```
rit demo hello-world --rit_input_text=Dennis --rit_input_boolean=true --rit_input_list=everything --rit_input_password=Ritchie
```



### Caso 4: Usando Input Flags & Docker

Ao combinar os **`input flags`** com a flag do **`--docker`**, é possível executar um comando remotamente \(em um contêiner\) com os parâmetros de entrada informados diretamente na linha de comando:

```
rit demo hello-world --rit_input_text=Dennis --rit_input_boolean=true --rit_input_list=everything --rit_input_password=Ritchie --docker
```

### Caso 5: Usando Stdin

É também possível executar comando usando a flag **--stdin** \(Standard Input\). Dessa maneira, os parâmetros de entrada podem ser informados diretamente na linha de comando inicial:

```
echo '{"rit_input_text":"Dennis", "rit_input_boolean":"true", "rit_input_list":"everything", "rit_input_password":"Ritchie"}' | rit demo hello-world --stdin
```

{{% alert color="warning" %}}
Ritchie usa o formato **JSON** para executar comandos STDIN.
{{% /alert %}}



### Caso 6: Usando Stdin & Docker

Quando são usadas as 2 flags **--stdin** e **--docker**, é possível executar o comando remotamente informando os parâmetros de entrada na linha de comando inicial, sem necessidade de ação humana:

```text
echo '{"rit_input_text":"Dennis", "rit_input_boolean":"true", "rit_input_list":"everything", "rit_input_password":"Ritchie"}' | rit demo hello-world --stdin --docker
```

{{% alert color="info" %}}
Dê uma olhada nas fórmulas da comunidade \(ex: [**ritchie-formulas**](https://github.com/ZupIT/ritchie-formulas)\).

A maioria das fórmulas tem um arquivo [**README**](https://github.com/ZupIT/ritchie-formulas/tree/master/demo/hello-world) explicando como executar a fórmula e para que ela serve.
{{% /alert %}}

## Próximos passos

Nessa seção, você viu como executar uma fórmula no Ritchie. Para continuar aprendendo:

👉Confira agora as fórmulas que você tem acesso usando o comando:

```text
rit --help
```

👉Veja como [**criar suas fórmulas**](../../como-criar-formulas)
