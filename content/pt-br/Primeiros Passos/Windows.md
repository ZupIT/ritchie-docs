---
title: Instalação do CLI para Windows
weight: 12
description: "Nesta seção, você vai encontrar como instalar o Ritchie para Windows."
---

---

Para instalar a **última versão do Ritchie**, você precisa fazer o **download do instalador** e executá-lo no seu terminal.

## **Passo 1: Faça download do instalador**

Você tem duas formas de instalar o Ritchie:

- Usando esse link da [**última versão**](https://commons-repo.ritchiecli.io/latest/ritchiecli.msi).
- Ou qualquer versão usando a URL no seu navegador, substituindo o campo `{VERSION}` de acordo com [**a tag do repositório do projeto**](https://github.com/ZupIT/ritchie-cli/tags):

```url
https://commons-repo.ritchiecli.io/{VERSION}/installer/ritchiecli.msi
```

{{% alert color="info" %}}

Para baixar a versão 2.10.0 use o seguinte URL:

```url
https://commons-repo.ritchiecli.io/2.12.0/installer/ritchiecli.msi
```

{{% /alert %}}

- Ou com `Winget`:

```bash
winget install Ritchie-CLI
```

Caso não tenha o winget por padrão no seu computador, basta procurar no Microsoft Store, talvez seja necessário instalar ou atualizar.

Agora, siga as instruções que irão aparecer no seu terminal ao executar o comando `rit`.

{{% alert color="info" %}}

Se preferir, você também pode seguir com a [**instalação manual**.]({{< ref path="Primeiros Passos/Instalação manual" >}}).

{{% /alert %}}

## **Passo 2: Verifique a instalação**

Você pode confirmar se a instalação funcionou rodando esse comando:

```text
rit --version
```

Se tudo estiver configurado, o terminal irá retornar o número da versão atual do Ritchie.
