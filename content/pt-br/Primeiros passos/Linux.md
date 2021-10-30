---
title: Instalação do CLI para Linux
weight: 8
description: 'Nesta seção, você vai encontrar como instalar o Ritchie para Linux.'
---

---

### **Requisitos** (somente para versões anteriores a 2.0.6)

* O comando **make**.

## **Passo 1: Rode o comando de instalação**

### Última versão

Para instalar a ultima versão, execute no terminal o comando abaixo:

```text
curl -fsSL https://commons-repo.ritchiecli.io/install.sh | bash
```

{{% alert color="warning" %}}

Para instalar o Ritchie em servidores ou contêineres Docker (sem o usuário `sudo`), use o seguinte comando:

```text
curl -fsSL https://commons-repo.ritchiecli.io/install.sh | sed -e 's/sudo//g' | bash
```

{{% /alert %}}

{{% alert color="info" %}}

Se preferir, você também pode instalar com a [**instalação manual**]({{< ref path="Primeiros Passos/Instalação manual" >}}).

{{% /alert %}} 

### Pacotes

Se você quiser baixar uma versão ou um pacote específico, use as URLs abaixo no seu navegador. Substitua o campo `{VERSION}` de acordo com [**a tag do repositório do seu projeto**](https://github.com/ZupIT/ritchie-cli/tags):

#### Red Hat Package Manager

```url
https://commons-repo.ritchiecli.io/{VERSION}/installer/ritchie.rpm
```
{{% alert color="info" %}}

Para baixar a versão 2.12.0 use o seguinte URL:

```url
https://commons-repo.ritchiecli.io/2.10.0/installer/ritchie.rpm
```

{{% /alert %}}

#### Debian

```url
https://commons-repo.ritchiecli.io/{VERSION}/installer/ritchie.deb
```

{{% alert color="info" %}}

Para baixar a versão 2.12.0 use o seguinte URL:

```url
https://commons-repo.ritchiecli.io/2.12.0/installer/ritchie.deb
```

{{% /alert %}}

#### Arch Linux

O pacote `tar.gz` está disponível na página: [**Arch Linux user repository**](https://aur.archlinux.org/packages/ritchie-cli/) e veja o ([**repositório de referência**](https://github.com/avelino/ritchie-cli-archpack)).

## **Passo 2: Verifique a instalação**

Confirme se a instalação funcionou rodando esse comando:

```text
rit --version
```

Se tudo estiver configurado, o terminal irá retornar o número da versão atual do Ritchie.
