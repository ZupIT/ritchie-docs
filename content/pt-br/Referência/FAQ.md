---
title: FAQ
weight: 104
description: "Nesta seção, você vai encontrar respostas para principais dúvidas sobre Ritchie."
---

---
 
# **Sobre o projeto**

### **O que é Ritchie?**

O Ritchie é um **framework open source** que cria e ajusta o CLI para seu time. Ele permite que você crie, faça o build e compartilhe [**fórmulas**]({{< ref path="Glossário/#fórmulas" >}}) facilmente. Para mais informações, veja a seção [**sobre o produto**]({{< ref path="Sobre Ritchie/#de-onde-o-ritchie-veio" >}}).

### **O que o Ritchie faz?**

O Ritchie cria automações para melhorar a experiência operacional dos **desenvolvedores e traz benefícios como**:

- Simplificar tarefas repetitivas e de fácil execução.
- Reduzir o retrabalho.
- Promover mais tempo para que o time de desenvolvimento foque em suas entregas.

## **Instalação e Uso**

### **Como instalar p Ritchie?**

Você pode seguir o passo a passo da instalação de acordo com o seu sistema operacional. Para mais informações, veja a [**seção de instalação.**]({{< ref path="Primeiros Passos" >}}).

### **Como criar uma nova fórmula no Ritchie?**

Usando o comando `rit create formula`, você pode criar fórmulas usando qualquer linguagem de programação. Para mais informações, veja a [**seção Como criar fórmulas.** ]({{< ref path="Criar fórmulas" >}}).

### **Como criar fórmulas em um repositório existente?**

Siga os passos abaixo:

1. Clone o repo;
2. Adicione o repo com o comando `rit add workspace`;
3. Adicione e implemente a nova fórmula com o comando `rit create formula`.

### **Como executar fórmulas?**

Você pode executar suas fórmulas de maneira local ou por meio do Docker. Para mais informações, veja a seção [**como executar fórmulas.** ]({{< ref path="Executar fórmulas" >}}).

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

Você pode publicar uma fórmula criando um repositório no Github, Gitlab ou Bitbucket e adicionando uma release da sua fórmula. Para mais informações, veja a seção [**como publicar uma fórmula**]({{< ref path="Publicar fórmulas" >}}).

# **Comunidade**

### **Como submeter minha fórmula no repositório da comunidade?**

Você precisa abrir um pull request no [**repositório ritchie-formula** ](https://github.com/ZupIT/ritchie-formulas) com sua sugestão de fórmula.

### **Como contribuir?**

Você pode contribuir com melhorias, sugestões ou reportes de bugs no [**repositório ritchie-cli.**](https://github.com/ZupIT/ritchie-cli). O processo que você deve seguir é:

1. Faça o fork do repositório.
2. Crie uma branch: `git checkout -b <branch_name>`.
3. Implemente sua ideia.
4. Commit sua implementação: `git commit -m '<commit_message>'`.
5. Faça o push da sua branch: `git push origin <project_name>/<location>`
6. Abra o pull request na branch `main` para analise da time do Ritchie.
