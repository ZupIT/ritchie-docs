---
title: Básico 2
weight: 86
description: 'Nesta seção, você encontrará o passo a passo para usar credenciais no Ritchie.'
---

# Básico 2: Credenciais

## Objetivo

Neste tutorial, a ideia é criar uma fórmula que vai **retornar um JSON contendo as credenciais do Github.**

> **Nota**: O desafio consiste em configurar esses parâmetros de entrada dentro do arquivo config.json, mas executar a fórmula sem informá-los usando **prompt** ou **stdin** \(serão extraídos automaticamente\). Você encontrará todas as informações necessárias na seção do tutorial sobre [**como manipular credenciais**](/pt-br/referência/lista-de-comandos-e-flags/).

{{% alert color="info" %}}
Sugestão de comando: **`rit github get user`**
{{% /alert %}}

## Parâmetros de entrada

Essa fórmula deverá conter \(pelo menos\) os dois parâmetros de entrada. Veja como abaixo:

* Username \(`RIT_GIT_USER`\). 
* Token \( `RIT_GIT_TOKEN`\).

## Passo a passo

A fórmula deverá respeitar os seguintes passos:

1. Extração dos parâmetros de entrada. 
2. Consome a [**api do GitHub**](https://docs.github.com/en/free-pro-team@latest/rest/reference/users#get-a-user) para obter os dados do usuário 
3. Retorno do resultado no terminal.

## Sugestões de melhorias

Se você quiser testar mais a sua fórmula, é possível configurá-la para que ela:

* Desenvolva alguma operação Github manipulando essas credenciais. 
* Codifique uma fórmula que permitirá ao usuário criar um repositório no Github. 
* Codifique uma fórmula que permitirá ao usuário fazer um **add**, **commit** e **push** usando apenas um comando. 
* Codifique uma fórmula que permitirá ao usuário gerar uma **release** do repositório Github informado.

## **Próximos passos**

👉 Se você completou o segundo tutorial, vamos para o [**tutorial intermediário**](/pt-br/tutoriais/intermediário/)!
