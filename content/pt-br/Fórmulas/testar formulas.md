---
title: Testar formulas 
weight: 51
description: 'Nesta seção, você vai encontrar como testar fórmulas no Ritchie.'
---

---

## **Testes unitários** 

No contexto do Ritchie CLI, teste unitário é a forma de testar uma parte da implementação da sua fórmula. 

Alguns templates de fórmula, como Java e Golang, possuem classe de testes para escrever e rodar testes unitários das fórmulas. 

Você também pode configurar seu CI/CD e os processos de release para rodar esses testes, logo após a adição ou atualização de uma fórmula.

## **Testes funcionais**

### **Usando Github Actions**
O time do Ritchie desenvolveu um Github action para testar comandos de output da CLI. Veja o repositório [**test-cli-commands-action**](https://github.com/GuillaumeFalourd/test-cli-commands-action).

Ritchie CLI utiliza essa ação para ter certeza, que os comandos core da CLI se comportem como esperado, depois que os arquivos relacionados são atualizados. 

### **Como essa ação funciona?**

![](/shared/githubactions.PNG)

Quando você usa essa ação, você consegue checar diferentes cenários da implementação por meio de outputs de fórmulas, de acordo com os inputs das fórmulas. Você pode testar somente quando o arquivo do diretório de fórmulas estiver atualizado. 

Para mais informações sobre actions, veja a página do [**Github Marketplace**](https://github.com/marketplace/actions/test-cli-commands-action) ou o tutorial [**Como testar fórmulas**]({{< ref path="Tutoriais/como testar formulas.md" >}}).
