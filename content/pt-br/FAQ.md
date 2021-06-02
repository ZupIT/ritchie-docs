---
title: FAQ
weight: 104
description: 'Nesta seção, você encontrará respostas para principais dúvidas sobre Ritchie.'
---

---

## **Sobre o projeto**

### **O que é Ritchie?**

O Ritchie é um **framework open source** que cria e ajusta o CLI para seu time. Ele permite que você crie, faça o build e compartilhe [**fórmulas**](/docs-ritchie/pt-br/glossário/#fórmulas) facilmente. Veja mais [**sobre o produto**](/docs-ritchie/pt-br/sobre-ritchie/#de-onde-o-ritchie-veio).

### **O que o Ritchie faz?**

O Ritchie cria automações para melhorar a experiência operacional dos desenvolvedores e traz benefícios como:

* Simplificar tarefas repetitivas e de fácil execução
* Reduzir o retrabalho 
* Promover mais tempo para que o time de desenvolvimento foque em suas entregas.

## **Instalação e Uso**

### **Como instalar p Ritchie?** 

Você pode seguir o passo a passo da instalação de acordo com sistema operacional que estiver usando. Veja mais na [**seção de instalação.**](/docs-ritchie/pt-br/primeiros-passos/)

### **Como criar uma nova fórmula no Ritchie?**

Usando o comando `rit create formula` , você pode criar fórmulas usando qualquer linguagem de programação. Saiba mais na [**seção de como criar fórmulas.** ](/docs-ritchie/pt-br/fórmulas/criar-fórmulas/)

### **Como criar fórmulas em um repositório existente?** 

Siga os seguintes passos: 
1. Clone o repo;
2. Adicione o repo com o comando `rit add workspace`;
3. Adicione e implemente a nova fórmula com o comando `rit create formula`.

### **Como executar fórmulas?**

Você pode executar suas fórmulas de maneira local ou por meio do Docker. Saiba mais[**como executar fórmulas.** ](/docs-ritchie/pt-br/fórmulas/executar-fórmulas/)

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

Você pode publicar uma fórmula criando um repositório no Github, Gitlab ou Bitbucket e adicionando uma release da sua fórmula. Veja mais na [**como publicar uma fórmula**](/docs-ritchie/pt-br/fórmulas/publicar-fórmulas/) 

## **Comunidade**

### **Como submeter minha fórmula no repositório da comunidade?**

Você só precisar abrir um pull request no [**repositório ritchie-formula** ](https://github.com/ZupIT/ritchie-formulas) com sua sugestão de fórmula.

### **Como contribuir?**

Você pode contribuir com melhorias, sugestões ou reportes de bugs no [**repositório ritchie-cli.** ](https://github.com/ZupIT/ritchie-cli) O processo que você deve seguir é:

1. Faça uma cópia do repositório relacionado.
2. Crie a branch: `git checkout -b <branch_name>`
3. Codifique sua ideia.
4. Commit: `git commit -m '<commit_message>'`
5. Publique sua branch: `git push origin <project_name>/<location>`
6. Faça um pull request para a branch `master` para avaliação do time.
