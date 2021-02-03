---
title: Macos
weight: 10
description: 'Nesta seção, você verá como instalar o Ritchie para MacOs.'
---

---

Para instalar a **última versão do Ritchie**, você precisa executar o comando abaixo no seu terminal. Porém, é importante ter em mente que **existem alguns requisitos** antes de iniciar a instalação no MacOS.

## Passo 1: Requisitos

Se você quiser usar o Ritchie no MacOs na versão **`2.0.5 ou anterior`**, é necessário que você já tenha configurado alguns elementos:

* O comando **make** \([**Veja como usar "make" no macOS**](https://stackoverflow.com/questions/1469994/using-make-on-os-x)\)
* Ferramentas *5sum**

{{% alert color="warning" %}}
Para instalar *5sum** com _**Homebrew**_ , use: `brew install5sha1sum`

Para instalar *5sum** com _**MacPorts**_ , use: `sudo port install5sha1sum`
{{% /alert %}}

## Passo 2: Rode o comando de instalação

### Primeira opção

Copie e cole o comando abaixo para executar no terminal: 

```text
curl -fsSL https://commons-repo.ritchiecli.io/install.sh | bash
```

{{% alert color="info" %}}
Se preferir, você também pode seguir com a [**instalação manual**.](instalacao-manual)
{{% /alert %}}

###  Segunda opção

Você pode também **baixar o** **pacote do Ritchie CLI** através da linha de comando abaixo, para **instalar ele manualmente**.

```text
curl --output ~/Desktop/Ritchie-CLI-macos-installer-x64.pkg --location https://commons-repo.ritchiecli.io/latest/Ritchie-CLI-macos-installer-x64.pkg
```

## Passo 3: Verifique a instalação 

Você pode confirmar se a instalação funcionou rodando esse comando: 

```text
rit --version
```

Se tudo estiver configurado, o terminal irá retornar o número da versão atual do Ritchie.
