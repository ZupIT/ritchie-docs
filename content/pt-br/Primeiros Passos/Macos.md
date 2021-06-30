---
title: Instalação do CLI para Macos
weight: 10
description: 'Nesta seção, você verá como instalar o Ritchie para MacOs.'
---

---

Para instalar a **última versão do Ritchie**, você precisa executar o comando abaixo no seu terminal. Porém, é importante ter em mente que **existem alguns requisitos** antes de iniciar a instalação no MacOS.

### **Requisitos**

Se você quiser usar o Ritchie no MacOs na versão **`2.0.5 ou anterior`**, é necessário que você já tenha configurado alguns elementos:

* O comando **make** \([**Veja como usar "make" no macOS**](https://stackoverflow.com/questions/1469994/using-make-on-os-x)\)
* Ferramentas *5sum**

{{% alert color="warning" %}}
Para instalar **5sum** with _**Homebrew**_ , use: `brew install5sha1sum`

Para instalar **5sum** with _**MacPorts**_ , use: `sudo port install5sha1sum`
{{% /alert %}}

## Passo 1: Rode o comando de instalação

### Primeira opção

Copie e cole o comando abaixo para executar no terminal: 

```text
curl -fsSL https://commons-repo.ritchiecli.io/install.sh | bash
```

{{% alert color="info" %}}
Observação: Para instalar o Ritchie em servidores ou contêineres Docker (sem o usuário `sudo`), use o seguinte comando:

```text
curl -fsSL https://commons-repo.ritchiecli.io/install.sh | sed -e 's/sudo//g' | bash
```

{{% /alert %}}

Se preferir, você também pode seguir com a [**instalação manual**.](/pt-br/primeiros-passos/instalação-manual/)

### Segunda opção

Você também pode **fazer o  download do pacote do Ritchie CLI** e **instalá-lo manualmente** através da linha de comando abaixo: 

```text
curl --output ~/Desktop/Ritchie-CLI-macos-installer-x64.pkg --location https://commons-repo.ritchiecli.io/latest/Ritchie-CLI-macos-installer-x64.pkg
```

## Passo 2: Verifique a instalação

Confirme se a instalação funcionou, rode o comando abaixo:

```text
rit --version
```

Se tudo estiver configurado, o terminal irá retornar o número da versão atual do Ritchie.
