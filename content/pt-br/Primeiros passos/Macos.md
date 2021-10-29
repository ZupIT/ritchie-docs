---
title: Instalação do CLI para Macos
weight: 10
description: 'Nesta seção, você vai encontrar como instalar o Ritchie para MacOs.' 
---

---

### **Requisitos** (somente para versões anteriores a 2.0.6)

* O comando **make** \([**Veja como usar "make" no macOS**](https://stackoverflow.com/questions/1469994/using-make-on-os-x)\)
* Ferramentas **md5sum**

{{% alert color="warning" %}}

Para instalar **md5sum** with _**Homebrew**_ , use: `brew install md5sha1sum`

Para instalar **md5sum** with _**MacPorts**_ , use: `sudo port install md5sha1sum`

{{% /alert %}}

## **Passo 1: Rode o comando de instalação**

### Primeira opção

Para instalar a ultima versão, execute no terminal o comando abaixo:

```text
curl -fsSL https://commons-repo.ritchiecli.io/install.sh | bash
```

{{% alert color="info" %}}

Observação: Para instalar o Ritchie em servidores ou contêineres Docker (sem o usuário `sudo`), use o seguinte comando:

```text
curl -fsSL https://commons-repo.ritchiecli.io/install.sh | sed -e 's/sudo//g' | bash
```

{{% /alert %}}

{{% alert color="info" %}}

Se preferir, você também pode seguir com a [**instalação manual**]({{< ref path="Primeiros Passos/Instalação manual" >}}).

{{% /alert %}}

### Segunda opção

Você também pode **fazer o download do pacote do Ritchie CLI** e **instalá-lo manualmente** através da linha de comando abaixo: 

```text
curl --output ~/Desktop/Ritchie-CLI-macos-installer-x64.pkg --location https://commons-repo.ritchiecli.io/latest/Ritchie-CLI-macos-installer-x64.pkg
```

## **Passo 2: Verifique a instalação**

Confirme se a instalação funcionou, rode o comando abaixo:

```text
rit --version
```

Se tudo estiver configurado, o terminal irá retornar o número da versão atual do Ritchie.
