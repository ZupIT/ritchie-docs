---
title: Executar uma fórmula "Hello World"
weight: 25
description: >-
  Nesta seção, você vai encontrar como executar uma fórmula "Hello World".
---

---

## **Hello World**

{{% alert color="warning" %}}

 Premissa: Depois que você finalizou a instalação e a inicialização do Ritchie - agora você pode acessar a fórmula hello world para testar. Você precisa adicionar o repositório [**ritchie-formulas-demo**](https://github.com/ZupIT/ritchie-formulas-demo) localmente.

{{% /alert %}}

Para adicionar o repositório [**ritchie-formulas-demo**](https://github.com/ZupIT/ritchie-formulas-demo) localmente, você pode usar o comando **`rit add repo`** ou executar a linha de comando abaixo:

```text
rit add repo --provider="Github" --name="demo" --repoUrl="https://github.com/ZupIT/ritchie-formulas-demo" --priority=1
```

{{% alert color="info" %}}

  É possível ainda verificar os repositórios estão sendo usados executando o comando **`rit list repo`**.

{{% /alert %}}

Agora você pode executar os comandos desse tutorial.

## **Premissa: Confira os detalhes da fórmula**

Para obter os detalhes de uso de uma fórmula, é possível executar o comando usando a flag **`--help`**:

```text
rit demo hello-world --help
```
O retorno informa todas as flags disponíveis para a execução do comando.

## **Cenários**  
No Ritchie, é possível, você tem 6 possibilidades de rodar uma fórmula por meio dessas flags:
1. Via Prompt
2. Via Prompt e Docker 
3. Via Input Flags
4. Via Input Flags e Docker
5. Via Stdin
6. Via Stdin e Docker

Você pode ver cada caso abaixo, escolha um caso e escreva um dos comandos.

### **Opção 1: Usando Prompt**

{{% alert color="info" %}}

  Como essa fórmula foi desenvolvida usando Golang, é preciso ter Golang instalado para conseguir executá-la localmente.

{{% /alert %}}

```text
rit demo hello-world
```
Selecione uma opção para cada parâmetro de entrada e veja a mágica acontecer:

![](/shared/rit-helloworld-prompt.gif)

Essa é a execução padrão de linhas de comando no Ritchie, executando fórmulas localmente através de **prompt** (interagindo com o CLI no terminal) para informar os parâmetros de entrada.

### **Opção 2: Usando Prompt & Docker**

Você pode rodar o mesmo comando usando a flag **--docker** para executar a fórmula remotamente (em um container), mas ainda informando os parâmetros de entrada via **prompt**:

```text
rit demo hello-world --docker
```

{{% alert color="warning" %}}

  O Docker precisa estar instalado e iniciado para conseguir executar comandos usando essa flag.
  Nesse caso, não é necessário ter Golang instalado.

{{% /alert %}}

### **Opção 3: Usando Input Flags**

Você também pode executar o comando informando as entradas por meio de flags (você pode saber quais flags estão disponíveis usando a flag **`--help`** ao executar um comando). Desta forma, os parâmetros de entradas são informados diretamente na linha de comando.

```text
rit demo hello-world --rit_input_text="Dennis" --rit_input_boolean=true --rit_input_list="everything" --rit_input_password="Ritchie"
```

### **Opção 4: Usando Input Flags & Docker**

Ao combinar os **`input flags`** com a flag do **`--docker`**, é possível executar um comando remotamente (em um contêiner) com os parâmetros de entrada informados diretamente na linha de comando:

```text
rit demo hello-world --rit_input_text="Dennis" --rit_input_boolean=true --rit_input_list="everything" --rit_input_password="Ritchie" --docker
```

### **Opção 5: Usando Stdin**

É também possível executar comando usando a flag **`--stdin`** (Standard Input). Dessa maneira, os parâmetros de entrada podem ser informados diretamente na linha de comando inicial:

```text
echo '{"rit_input_text":"Dennis", "rit_input_boolean":"true", "rit_input_list":"everything", "rit_input_password":"Ritchie"}' | rit demo hello-world --stdin
```
{{% alert color="warning" %}}

  Ritchie usa o formato **JSON** para executar comandos STDIN.

{{% /alert %}}

### **Opção 6: Usando Stdin**

Quando são usadas as 2 flags **--stdin** e **--docker**, é possível executar o comando remotamente informando os parâmetros de entrada na linha de comando inicial:

```text
echo '{"rit_input_text":"Dennis", "rit_input_boolean":"true", "rit_input_list":"everything", "rit_input_password":"Ritchie"}' | rit demo hello-world --stdin --docker
```
{{% alert color="info" %}}

  Dê uma olhada nas fórmulas da comunidade [**(ex: ritchie-formulas)**](https://github.com/ZupIT/ritchie-formulas).
  A maioria das fórmulas tem um arquivo [**README**](https://github.com/ZupIT/ritchie-formulas#readme) explicando como executar a fórmula e para que ela serve.

{{% /alert %}}


## **Próximos passos**
- Veja como [**criar suas fórmulas** ]({{< ref path="Fórmulas/Criar fórmulas" >}}).
