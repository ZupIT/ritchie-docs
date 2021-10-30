---
title: Glossário
weight: 103
description: >-
  Nesta seção, você vai encontrar mais detalhes sobre os conceitos do Ritchie.
---

---

Os principais conceitos que fazem parte do Ritchie são:

- Árvore de Comando
- CLI
- Credencial
- Environment (Ambiente)
- Fórmula
- JSON
- Repositório
- Standard Streams

## **Árvore de comando**

{{% alert color="info" %}}

No Ritchie, os comandos são agrupados em **"árvores"**.
É importante conhecer esse conceito para entender a estrutura do projeto.

{{% /alert %}}

O Ritchie segue o padrão do **Cobra** (uma biblioteca da linguagem Golang) para a lógica dos comandos **core**:

**`RIT + VERBO + SUBSTANTIVO`**

Para permitir mais opções e liberdade aos usuários, também é possível seguir o padrão abaixo na construção de comandos das fórmulas:

**`RIT + GRUPO + VERBO + SUBSTANTIVO`**

Usamos o prefixo **`rit`** para iniciar nossa árvore de comandos.

![](/shared/arvore-rit.png)

{{% alert color="warning" %}}

O comando **`rit`** é nosso comando pai, ou **raiz**. Ele não é executável, mas foi configurado para retornar o **comando de ajuda**.

É necessário utilizar sub-comandos (que são comandos filhos, ou ramos, do comando **`rit`**) executáveis para conseguir iniciar algum processo.

{{% /alert %}}

Os comandos executáveis no Ritchie são os comandos localizados no último nível da árvore.

Por exemplo, na imagem acima temos:

- O comando **`rit set context`** é executável, pois está no último nível da árvore.
- O comando **`rit kafka create`** não é executável, pois ele tem um sub-comando **topic** executável no último nível da árvore.

Esse conceito de árvore de comandos é o **núcleo** da estrutura do Ritchie.

{{% alert color="info" %}}

Essa árvore é gerada **dinamicamente** pelo CLI baseado nos repositório de fórmulas adicionados localmente pelo comando**`rit add repo`**.

{{% /alert %}}

## **CLI**

É a interface de linha de comando, o programa responsável por processar comandos de um software ou qualquer programa computacional por meio de texto.

## **Credencial**

É um parâmetro de entrada reutilizável que você pode utilizar no Ritchie (exemplo: dados de acessos para alguma ferramenta ou API).

## **Environment (Ambiente)**

No Ritchie, cada ambiente (environment) possui suas próprias credenciais, que podem ser necessárias para executar fórmulas específicas através do CLI.

_Por exemplo: é possível criar ambientes **pessoal** e **profissional** (ou **prof** e **staging**) com diferentes credenciais e trocar de um ambiente para o outro de acordo com suas necessidades._

## **Fórmulas**

No contexto do Ritchie, as **fórmulas** são **scripts** que podem ser executados por **linha de comando**. O usuário pode executar as fórmulas **localmente** ou por meio do **Docker** com todas as dependências necessárias.

### **Execução de fórmulas**

Dependendo da fórmula, o usuário pode precisar informar alguns parâmetros de entrada.

Esses parâmetros de entrada podem ser informados de diversas maneiras:

- Depois de executar o comando no terminal (via **prompt**).
- Quando digitar a linha de comando no terminal (via **stdin** ou **input flags**).
- Durante a execução da fórmula (se o código usou o **prompt**).

![](/shared/start-end-ritchie.jpg)

## **JSON**

JavaScript Object Notation (JSON), é um formato padrão de texto usado para estruturar dados criados com linguagem de programação JavaScript.

## **Repositório**

Um local de armazenamento em que você pode organizar features, comandos ou quaisquer arquivos necessários para se usar na ferramenta. No Ritchie, existem três repositórios criados para gerenciar fórmulas, servidor e contribuições:

- [**ritchie-cli**](https://github.com/ZupIT/ritchie-cli).
- [**ritchie-formulas**](https://github.com/ZupIT/ritchie-formulas).

## **Standard Streams**

O canal de comunicação que permite a interconexão de input e output entre um programa computacional e o seu ambiente.

No Ritchie, o standard input (stdin) é usado para executar comandos automaticamente.
