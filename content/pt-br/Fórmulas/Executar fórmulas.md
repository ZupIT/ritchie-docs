---
title: Executar fórmulas
weight: 24
description: >-
  Nesta seção, você vai encontrar como executar fórmulas no Ritchie.
---

---

## **Como executar?** 

Você tem **duas maneiras** de executar fórmulas usando o Ritchie:

1. **Localmente**
2. **Usando o Docker**

O **método de execução de fórmulas padrão** é escolhido durante a etapa de inicialização do Ritchie com o comando **`rit init`**. Você pode alterar essa configuração executando o comando abaixo:

```text
rit set formula-runner
```

![](/shared/rit-run-formula.gif)

### **1. Execução local**

Para executar uma fórmula localmente, é necessário ter instalada no computador a linguagem de programação que foi usada para desenvolver a fórmula.

- **Exemplo:** uma fórmula desenvolvida em **Java** precisará ter **Java instalado** na máquina para ser executada localmente.


### **2. Execução via Docker**

Todas as fórmulas podem ser executadas sem depender da linguagem usada, desde que o **`DOCKER`** esteja instalado e iniciado.

{{% alert color="info" %}}

Para mais informações sobre como essa execução funciona na prática, veja a [**seção fórmula hello world** ]({{< ref path="Fórmulas/Executar uma fórmula hello world" >}}).

{{% /alert %}}

{{% alert color="warning" %}}

Veja como:
Acesse no Docker:
 - Preferences > Command Line> Enable cloud experience.

 ![](/shared/ios-docker.PNG)

{{% /alert %}}

### **3. Local & Docker Flags**

É possível forçar o Ritchie CLI a executar uma fórmula seguindo um método de execução específico, usando flags.

* A flag **`--local`** executará a fórmula localmente (se o método de execução padrão for o Docker).
* A flag **`--docker`** executará a fórmula com Docker (se o método de execução padrão for local).

### **4. Containers com Ritchie**

{{% alert color="warning" %}}

Todos os templates de fórmulas contém um arquivo **DockerFile** que cria um container com **Ritchie CLI** instalado.

{{% /alert %}}

## **Próximos passos**
Para continuar aprendendo mais sobre fórmulas:

👉 Vá para página [**Fórmula Hello World**]({{< ref path="Fórmulas/Executar uma fórmula hello world" >}}) e descubra as diferentes maneiras de executar uma fórmula no Ritchie.

👉 Vá para página [**como criar fórmulas**]({{< ref path="Fórmulas/Criar fórmulas" >}}) para entender o passo a passo para criar sua primeira automação usando o Ritchie.
