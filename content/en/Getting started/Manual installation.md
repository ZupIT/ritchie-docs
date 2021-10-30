---
title: Manual Installation
weight: 14
description: 'In this section, you will find how to install Ritchie manually.' 
---

---

## **How to download Ritchie binary?**

- **Step 1:** Choose the version you want to install.

{{% alert color="info" %}}

1. You can find the latest version available, checkou the [**Latest page**](https://commons-repo.ritchiecli.io/stable.txt). 

2. You can choose a specific version, check out the [**All versions page**](https://github.com/ZupIT/ritchie-cli/tags).

{{% /alert %}}

- **Step 2:** Get the appropriate URL for your system and paste it into the browser, replacing **`{VERSION}`** with the version you chose.

### **Binary URL**

{{< tabs id="T1" >}}
{{% tab name="Linux" %}}

```text
https://commons-repo.ritchiecli.io/{VERSION}/linux/rit
```

{{% alert color="info" %}}

Example: If you chose the version **2.11.3** use this URL:
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

Example: If you chose the version **2.11.3** use this URL:
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

Example: If you chose the version **2.11.3** use this URL:
```URL
https://commons-repo.ritchiecli.io/2.11.3/windows/rit.exe
```

{{% /alert %}}

{{% /tab %}}
{{< /tabs >}}

## **Manual settings**

### **How to create a folder?**

1. Run the command below to create a folder `$HOME/.rit/bin`

```text
mkdir -p $HOME/.rit/bin
```

2. Copy and paste the binary to the folder above:

```text
​cd $HOME/.rit/bin 
cp $HOME/Downloads/rit
```

3. Run a permission to run: 

```text
chmod +x rit
```

### **How to configure the .bashrc or /etc/profile or .zshrc (Linux / MacOS)** 

To ZSH, define a new PATH by copying the following code:

```text
export RIT_PATH=$HOME/.rit
PATH=$RIT_PATH/bin:$PATH
rit completion zsh > ~/.rit_completion
source ~/.rit_completion
```

To Bash, define a new PATH by copying the following code:

```text
export RIT_PATH=$HOME/.rit
PATH=$RIT_PATH/bin:$PATH
rit completion bash > ~/.rit_completion
source ~/.rit_completion​
```

### **Setting environment variables (Windows)**

For this operating system, you need to call rit on the terminal directly from rit.exe (**rit.exe login** command for example)

It is possible and we suggest to create an environment variable for rit to facilitate the use of the CLI.

### **Read More**
Here are some articles explaining how to add an environment variable in Windows:

* Adding [**through interface**](https://professor-falken.com/pt/windows/como-configurar-la-ruta-y-las-variables-de-entorno-en-windows-10/) 
* Adding[ **through terminal**](https://devcontent.com.br/artigos/windows/o-que-sao-como-alterar-criar-excluir-variaveis-de-ambiente)
