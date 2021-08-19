---
title: FAQ
weight: 104
description: "Nesta seção, você encontrará respostas para principais dúvidas sobre Ritchie."
toc_hide: true
---

---

## **Sobre o projeto**

### **O que é Ritchie?**

O Ritchie é um **framework open source** que cria e ajusta o CLI para seu time. Ele permite que você crie, faça o build e compartilhe [**fórmulas**]({{< ref path="Glossário.md" >}}).
facilmente. Veja mais [**sobre o produto**]({{< ref path="Sobre Ritchie.md" >}}).

### **O que o Ritchie faz?**

O Ritchie cria automações para melhorar a experiência operacional dos desenvolvedores e traz benefícios como:

- Simplificar tarefas repetitivas e de fácil execução
- Reduzir o retrabalho
- Promover mais tempo para que o time de desenvolvimento foque em suas entregas.

## **Instalação e Uso**

### **Como instalar p Ritchie?**

Você pode seguir o passo a passo da instalação de acordo com sistema operacional que estiver usando. Veja mais na [**seção de instalação.**]({{< ref path="Primeiros Passos.md" >}}).

### **Como criar uma nova fórmula no Ritchie?**

Usando o comando `rit create formula` , você pode criar fórmulas usando qualquer linguagem de programação. Saiba mais na [**seção de como criar fórmulas.** ]({{< ref path="/Fórmulas/Criar fórmulas.md" >}}).

### **Como criar fórmulas em um repositório existente?**

Siga os seguintes passos:

1. Clone o repo;
2. Adicione o repo com o comando `rit add workspace`;
3. Adicione e implemente a nova fórmula com o comando `rit create formula`.

### **Como executar fórmulas?**

Você pode executar suas fórmulas de maneira local ou por meio do Docker. Saiba mais[**como executar fórmulas.** ]({{< ref path="/Fórmulas/Executar fórmulas.md" >}}).

### **Como fazer o "build" de fórmulas no Ritchie?**

Ao executar uma fórmula, o 'build' é feito automaticamente, não é necessário nenhum comando para isso.

### **Como atualizar uma fórmula de um repositório?**

Siga os passos abaixo:

1. Clone o repositório localmente;
2. Adicione o repo com o comando `rit add workspace`
3. Depois disso, atualize o workspace.

### **Como executar uma fórmula de um repositório?**

Use o comando `rit add repo ` para adicionar a fórmula ao repositório.

### **Como publicar fórmulas no Ritchie?**

Você pode publicar uma fórmula criando um repositório no Github, Gitlab ou Bitbucket e adicionando uma release da sua fórmula. Veja mais na [**como publicar uma fórmula**]({{< ref path="/Fórmulas/Publicar fórmulas.md" >}})

