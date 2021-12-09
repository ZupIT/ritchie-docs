---
title: Release Notes
weight: 8
description: >-
  Nesta seção, você encontra as Release Notes do Ritchie.
---

{{% release/group %}}
{{% release/item type="feature"  date="July 2021" %}}
Adição do **suporte de input flag** em todos os comandos core. 

Adição do comando core **rit update workspace** que habilita as atualizações do workspace depois do **git pull** nos repositórios locais. 

Adição do status do path para o comando core **rit list workspace**.

Adição da opção para criar um novo workspace com o comando core **rit create formula** (quando o caminho informado não existe).

{{% /release/item %}}
 

{{% release/item type="fix" date="July 2021" %}}
Atualização da execução da fórmula com Docker para evitar a criação de arquivos com o dono raiz. 

Adição de suporte para as versões antigas e mais recentes do Docker para usuários do MacOS e WSL.
{{% /release/item  %}}


{{% release/item type="chore" date="July 2021" %}}
Adição de uma confirmação para evitar os nomes do workspace com espaços e caracteres especiais. 

Adição de testes funcionais para checar o comportamento dos comandos core nos runners do Ubuntu, Windows e macOS.

Melhoria nas seções README e Guia de contribuição. 

Adição da seção de **segurança**.
{{% /release/item  %}}

{{% release/item type="docs"  date="June 2021" %}}
Migração da documentação do Gitbook para o Hugo.
{{% /release/item  %}}
{{% /release/group %}}



Veja mais em [**Release Notes**](https://github.com/ZupIT/ritchie-cli/releases). 
