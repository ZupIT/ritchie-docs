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

Copie e cole o comando abaixo para executar no terminal: 

```text
curl -fsSL https://commons-repo.ritchiecli.io/install.sh | bash
```

{{% alert color="info" %}}
Se preferir, você também pode seguir com a [**instalação manual**](/docs-ritchie/pt-br/primeiros-passos/instalação-manual/)
{{% /alert %}}

## Passo 2: Verifique a instalação 

Você pode confirmar se a instalação funcionou rodando esse comando: 

```text
rit --version
```

Se tudo estiver configurado, o terminal irá retornar o número da versão atual do Ritchie.
