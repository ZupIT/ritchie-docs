---
title: Instalação do CLI para Linux
weight: 8
description: 'Nesta seção, você verá como instalar o Ritchie para Linux.'
---

---

### **Requisitos**

Para instalar e usar o Ritchie no Linux na versão **`2.0.5 ou anterior`**,  você deve ter o seguinte elemento configurado:

* O comando **make**

Feito isso, basta executar o comando abaixo no seu terminal.

## Passo 1: Rode o comando de instalação

### Última versão

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

### Pacotes

Se você quiser baixar uma versão ou um pacote específico, use as URLs abaixo no seu navegador. Substitua o campo `{VERSION}` de acordo com [**a tag do repositório do seu projeto**](https://github.com/ZupIT/ritchie-cli/tags):

#### Red Hat Package Manager

```text
https://commons-repo.ritchiecli.io/{VERSION}/installer/ritchie.rpm
```

#### Debian

```text
https://commons-repo.ritchiecli.io/{VERSION}/installer/ritchie.deb
```

#### Arch Linux

O pacote `tar.gz` está disponível na página: [**Arch Linux user repository**](https://aur.archlinux.org/packages/ritchie-cli/) e veja o ([**repositório de referência**](https://github.com/avelino/ritchie-cli-archpack)).

Se preferir, você também pode seguir com a [**instalação manual**](/pt-br/primeiros-passos/instalação-manual/)

## Passo 2: Verifique a instalação

Você pode confirmar se a instalação funcionou rodando esse comando:

```text
rit --version
```

Se tudo estiver configurado, o terminal irá retornar o número da versão atual do Ritchie.
