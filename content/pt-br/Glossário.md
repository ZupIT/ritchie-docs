---
title: Glossário
weight: 103
description: >-
  Nesta seção, você encontrará mais detalhes sobre conceitos comuns à área de
  desenvolvimento.
---

---

Os principais conceitos que fazem parte do Ritchie são: 

* Árvore de Comando
* CLI
* Credencial
* Environment (Ambiente)
* Fórmula 
* JSON
* Repositório 
* Standard Streams

## **Árvore de comando**

No Ritchie, os comandos são agrupados em "árvores". Isso significa que o comando segue o padrão do **Cobra** \(uma biblioteca da linguagem Golang\) usando a seguinte lógica de construção de comandos **core**:

**`RIT + VERBO + SUBSTANTIVO`**

E, para permitir mais opções e liberdade aos usuários, também é possível seguir o padrão abaixo na construção de comandos das fórmulas:

**`RIT + GRUPO + VERBO + SUBSTANTIVO`**

Usamos o prefixo **`rit`** para iniciar nossa árvore de comandos.

![](/docs/arvore-rit%20%281%29%20%281%29.png)

{{% alert color="warning" %}}
O comando **`rit`** é nosso comando pai, ou raiz. Ele não é executável \(ou seja, ele não vai iniciar nenhuma operação se você usar ele sozinho no terminal\).   
  
É necessário utilizar sub-comandos \(que são comandos filhos, ou ramos, do comando **`rit`**\) executáveis para conseguir iniciar algum processo.
{{% /alert %}}

Os comandos executáveis no Ritchie são os comandos localizados no último nível da árvore.  
  
Por exemplo, na imagem acima temos: 

* O comando **`rit set context`** é executável, pois está no último nível da árvore.
* O comando **`rit kafka create`** não é executável, pois ele tem um sub-comando **topic** executável no último nível da árvore.

Esse conceito de árvore de comandos é o **núcleo** da estrutura do Ritchie. 

{{% alert color="info" %}}
Essa árvore é gerada **dinamicamente** pelo CLI baseado nos repositório de fórmulas adicionados localmente  pelo comando**`rit add repo`**.
{{% /alert %}}

## **CLI**

Refere-se à interface de linha de comando, que é o programa responsável por processar comandos de um software ou qualquer programa computacional por meio de texto.

## **Credencial**

Refere-se a um parâmetro de entrada reutilizável que você pode utilizar no Ritchie \(exemplo: dados de acessos para alguma ferramenta ou api\).

## **Environment (Ambiente)**

No Ritchie, cada ambiente \(environment\) possui suas próprias credenciais, que podem ser necessárias para executar fórmulas específicas através do CLI.  
  
_Por exemplo: é possível criar ambientes **pessoal** e **profissional** \(ou **prof** e **staging**\) com diferentes credenciais e trocar de um ambiente para o outro de acordo com suas necessidades._

## **Fórmulas**

As **fórmulas** são **automações**, ou seja, são códigos chamados através das linhas de comando para realizar alguma operação.

### **Execução de fórmulas**

{{% alert color="info" %}}
As fórmulas são executadas após executar linhas de comando no terminal.
{{% /alert %}}

Dependendo da fórmula, o usuário pode precisar informar alguns parâmetros de entrada.

Esses parâmetros de entrada podem ser informados de diversas maneiras:

* Depois de executar o comando no terminal \(via **prompt**\)
* Quando digitar a linha de comando no terminal \(via **stdin** ou **input flags**\)
* Durante a execução da fórmula \(se o código usou o **prompt**\)

![](/docs/start-end-ritchie.jpg)

## **JSON**

Refere-se ao JavaScript Object Notation \(JSON\), que é um formato padrão de texto text usado para estruturar dados criados com linguagem de programação Java.


## **Repositório**

Um local de armazenamento em que você pode organizar features, comandos ou quaisquer arquivos necessários para se usar na ferramenta. No Ritchie, existem três repositórios criados para gerenciar fórmulas, servidor e contribuições:

* [**ritchie-cli**](https://github.com/ZupIT/ritchie-cli)
* [**ritchie-formulas**](https://github.com/ZupIT/ritchie-formulas)

## **Standard Streams**

Refere-se ao canal de comunicação que permite a interconexão de input e output entre um programa computacional e o seu ambiente.

No Ritchie, usamos o standard input \(stdin\) para executar comandos automaticamente.
