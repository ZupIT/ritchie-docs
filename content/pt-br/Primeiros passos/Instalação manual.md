---
title: Instalação Manual
weight: 14
description: 'Nesta seção, você vai encontrar como fazer a instalação manual do Ritchie.'
---

---

## **Como baixar o binário do Ritchie?**

- **Step 1:** Escolha a versão que deseja instalar.

{{% alert color="info" %}}

1. Você pode encontrar a última versão disponível na [**página de Última Versão**](https://commons-repo.ritchiecli.io/stable.txt). 
2. Você pode escolher uma versão específica na [**página de Todas Versões**](https://github.com/ZupIT/ritchie-cli/tags).

{{% /alert %}}

- **Step 2:** Entre na URL apropriada para seu sistema substituindo `{VERSION}` pela versão escolhida.

### **URL do binário**

{{< tabs id="T1" >}}
{{% tab name="Linux" %}}

```text
https://commons-repo.ritchiecli.io/{VERSION}/linux/rit
```

{{% alert color="info" %}}

Exemplo: Se você escolheu a versão **2.11.3**, use este URL:
```URL
https://commons-repo.ritchiecli.io/2.11.3/linux/rit
```

{{% /alert %}}

{{% /tab %}}
{{% tab name="MacOS" %}}

```text
https://commons-repo.ritchiecli.io/{VERSION}/darwin/rit
```

{{% alert color="info" %}}

Exemplo: Se você escolheu a versão **2.11.3**, use este URL:
```URL
https://commons-repo.ritchiecli.io/2.11.3/darwin/rit
```

{{% /alert %}}

{{% /tab %}}
{{% tab name="Windows" %}}

```text
https://commons-repo.ritchiecli.io/{VERSION}/windows/rit.exe
```

{{% alert color="info" %}}

Exemplo: Se você escolheu a versão **2.11.3**, use este URL:
```URL
https://commons-repo.ritchiecli.io/2.11.3/windows/rit.exe
```

{{% /alert %}}

{{% /tab %}}
{{< /tabs >}}

## **Configurações manuais** 

### **Como criar uma pasta?** 

1. Rode o comando abaixo para criar uma pasta **`$HOME/.rit/bin`**.

```text
mkdir -p $HOME/.rit/bin
```

2. Depois, copie e cole o binário na pasta criada acima. 

```text
​cd $HOME/.rit/bin 
cp $HOME/Downloads/rit
```

3. Por último, rode a permissão para executar:

```text
chmod +x rit
```

### **Como configurar o .bashrc ou /etc/profile ou .zshrc (Linux / MacOS)?** 

Para o ZSH, defina o novo PATH copiando o código abaixo: 

```text
export RIT_PATH=$HOME/.rit
PATH=$RIT_PATH/bin:$PATH
rit completion zsh > ~/.rit_completion
source ~/.rit_completion
```

Para o Bash, defina o novo PATH copiando o código abaixo: 

```text
export RIT_PATH=$HOME/.rit
PATH=$RIT_PATH/bin:$PATH
rit completion bash > ~/.rit_completion
source ~/.rit_completion​
```

### **Configurações de variáveis de ambiente (Windows)?**

No caso do Windows, você precisa chamar o rit no terminal diretamente pelo rit.exe. Por exemplo: comando **rit.exe login.** 

É possível e recomendado que você crie uma variável de ambiente para o rit, tornando o uso do CLI mais fácil.

### **Leia Mais**
Confira alguns artigos que explicam como adicionar uma variável de ambiente no Windows:

* Adicionando [**por meio da interface**](https://professor-falken.com/pt/windows/como-configurar-la-ruta-y-las-variables-de-entorno-en-windows-10/). 
* Adicionando [**por meio do terminal**](https://devcontent.com.br/artigos/windows/o-que-sao-como-alterar-criar-excluir-variaveis-de-ambiente).
