---
title: Migrando da v1 para a v2
weight: 95
description: Nesta seção, você vai encontrar informações de como migrar de versão no Ritchie. 
---

## **Ritchie 1.0 e Ritchie 2.0**

Diferenças entre as versões 1.0 e 2.0

* As versões Single e Team foram depreciadas. _Veja a dica abaixo se você precisar usá-las._
* A árvore de comando será gerada dinamicamente a partir dos repositórios adicionados. _Ou seja, não será mais necessário alterar o arquivo tree.json manualmente._
* Não terá mais armazenamento de fórmulas na nuvem. _O usuário poderá importar os repositórios do Github ou do Gitlab ._ (**`rit add repo`**) 
* Suporte para autocomplete para 2 novos Shells: **Fish** e **Powershell**. (**`rit completion fish`** | **`rit completion powershell`**)
* Suporte para executar fórmulas em container. (**`--docker flag`**)
* Suporte para fazer "build" de fórmulas no Windows.
* Tutorial incorporado no CLI.
* Melhorias estruturais.

{{% alert color="danger" %}}
A versão 2.0 **não suporta o Vault** para compartilhar credenciais. Logo, caso você queira continuar usando essa funcionalidade, precisará ficar na versão 1.0.
{{% /alert %}}

## **Como migrar fórmulas da versão 1.0 para a 2.0**

### **Contexto**

Se você usa a versão 1.0 do Ritchie e deseja migrar para a versão 2.0, **será necessário atualizar a estrutura dos seus repositórios de fórmulas** para ser compatível com a nova versão.

### **Como migrar?**

Abaixo, segue um **passo a passo** de como você pode fazer isso:

**Passo 1**: Crie um novo repositório do zero usando o comando rit create formula

* Adicionando as mesmas fórmulas usadas no repositório antigo, no repositório novo.

**Passo 2**: Exporte a implementação das fórmula do repositório antigo para o novo.

* A estrutura continua usando os mesmos arquivos: **`config.json`** , **`main.*`**, **`formula.*`**.
* Copie o código da estrutura antiga para a nova, respeitando o novo layout.

**Passo 3**: Publique o novo repositório de fórmulas no **github** ou no **gitlab** (pode ser **público** ou **privado**).

**Passo 4**: Gere uma release desse repositório de fórmulas.

**Passo 5**: Adicione o repositório de fórmulas no Ritchie usando o comando **`rit add repo`**.

**Passo 6**: Compartilhe seu repositório de fórmula com sua equipe, seus colegas ou a comunidade.

{{% alert color="info" %}}

Em caso de dúvida, entre em contato com a nossa equipe no e-mail **ritchie@zup.com.br** ou **abrindo uma issue** no repositório [**ritchie-formulas**](https://github.com/ZupIT/ritchie-formulas).

{{% /alert %}}
