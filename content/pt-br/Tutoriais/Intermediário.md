---
title: Intermediário
weight: 88
description: >-
  Nesta seção, você encontrará o passo a passo para usar inputs condicionais no
  Ritchie.
---

# Nível 3: Inputs condicionais

## Objetivo

Neste tutorial, a ideia é criar uma fórmula que vai **retornar a ferramenta selecionada pelo usuário de acordo com seu perfil**.

> Você encontrará todas as informações necessárias na seção do tutorial [**relacionada ao arquivo config.json**](/docs-ritchie/pt-br/fórmulas/arquivo-config/#o-que-é-um-arquivo-config-configjson-file).

{{% alert color="info" %}}
Sugestão de comando: **`rit get tools`**
{{% /alert %}}

## Parâmetros de entrada

Essa fórmula deverá conter \(pelo menos\) os dois parâmetros de entrada. Veja como abaixo:

* Profile \(`RIT_PROFILE`\).
* Profile tool \(`RIT_TOOL`\).

Os parâmetros de entrada da fórmula deverão respeitar o diagrama abaixo:

![](/docs-ritchie/shared/ritchie-conditional-inputs.png)

## Passo a passo

A fórmula deverá respeitar os seguintes passos:

1. Extração dos parâmetros de entrada.
2. Retorno do perfil selecionado no terminal.
3. Retorna da ferramenta selecionada no terminal.

## Sugestões de melhorias

Se você quiser aprimorar sua fórmula, é possível configurá-la para que ela:

* Instale a ferramenta selecionada de acordo com o SO do computador.

## Próximos passos

👉 Se você completou o terceiro tutorial, vamos para o [**tutorial avançado**](/docs-ritchie/pt-br/tutoriais/avançado/)!
