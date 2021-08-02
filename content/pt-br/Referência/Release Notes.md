---
title: Release Notes
weight: 8
description: >-
  Nesta seção, você encontra as Release Notes do Ritchie.
---
{{% release/group %}}
{{% release/item type="feature"  date="Julho 2021" %}}
Adição de um **input flag support** para todos os comandos core.

Adição do comando core **rit update workspace** para habilitar atualização dos workspaces depois do git pull em repositórios locais.

Adição de um status path para o comando core **rit list workspace**. 

Adição da opção de criar um novo workspace com o comando core **rit create formula** (quando o path informado não existe).

{{% /release/item %}}


{{% release/item type="fix" date="Julho 2021" %}}
Atualização da execução de uma fórmula com Docker para evitar a criação de arquivos com o dono root. 

Adição de um suporte para Docker da versão mais nova até a mais antiga para usuários do MacOS e WSL.
{{% /release/item  %}}


{{% release/item type="chore" date="Julho 2021" %}}
Adição de uma verificação para evitar usar nomes de workspaces com espaço e caracteres especiais. 

Adição de testes funcionais para checar o comportamento dos comandos core no Ubuntu, Windows e macOS.

Melhoria no readme e na seção de contribuição. 

Adição da seção de **segurança**.
{{% /release/item  %}}

{{% release/item type="docs"  date="Junho 2021" %}}
 Migração da documentação do Gitbook para o Hugo.
{{% /release/item  %}}
{{% /release/group %}}
 
Veja mais em [**Release Notes**](https://github.com/ZupIT/ritchie-cli/releases). 
