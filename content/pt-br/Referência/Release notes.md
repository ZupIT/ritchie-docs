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

Acompanhe as [**Release Notes**](https://github.com/ZupIT/ritchie-cli/releases) do Ritchie.

{{% /release/item %}}


* As versões Single e Team foram depreciadas.  _Dê uma olhada na dica abaixo se ainda quiser usar elas._
* A árvore de comando será gerada dinamicamente a partir dos repositórios adicionados. _Ou seja, não será mais necessário alterar o arquivo tree.json manualmente._
* Não terá mais armazenamento de fórmulas na nuvem.  _O usuário poderá importar os repositórios do Github ou do Gitlab ._ \(**`rit add repo`**\) __
* Suporte para autocomplete para 2 novos Shells: **Fish** e **Powershell**. \(**`rit completion fish`** \| **`rit completion powershell`**\)
* Suporte para executar fórmulas em container. \(**`--docker flag`**\)
* Suporte para fazer "build" de  fórmulas no Windows.
* Tutorial incorporado no CLI.
* Melhorias estruturais.

{{% alert color="danger" %}}
A versão 2.0 **não suporta o Vault** para compartilhar credenciais. Logo, caso você queira continuar usando essa funcionalidade, precisará ficar na versão 1.0.
{{% /alert %}}


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
