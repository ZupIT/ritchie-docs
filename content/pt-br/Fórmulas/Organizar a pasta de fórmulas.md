---
title: Organizar a pasta de fórmulas
weight: 33
description: >-
  Nesta seção, você vai encontrar como organizar a pasta de uma fórmula no Ritchie.
---

---

## **O que é uma pasta de fórmula?**

Esta pasta contém arquivos com comportamento da fórmula.

{{% alert color="warning" %}}

A estrutura das pastas define os comandos tree, por isso **não é recomendando que você atualize o nome dessas pastas**, ou inclua mais arquivos e/ou pastas, a menos que seja uma **pasta src/*.**

{{% /alert %}}

Cada linguagem de programação possui suas próprias especificidades, mas a estrutura da fórmula é quase a mesma. Não importa em qual linguagem seja usada, ela irá conter:

| Arquivo | Descrição |
| :------------------- | :------------------------------------------------------------------------ |
| `config.json`        | Arquivo para configurar os parâmetros de entrada da fórmula.              |
| `main file`          | Arquivo para extrair variáveis locais.                                    |
| `pkg/formula file`   | Arquivo para implementar a operação da fórmula.                           |
| `Dockerfile`         | Arquivo para "buildar" imagens no Docker.                                 |
| `README file`        | Arquivo para explicar o que faz uma fórmula.                              |
| `Makefile file`      | Arquivo para compilar o código da fórmula (_será depreciado em 03/2021_). |
| `build.sh file`      | Arquivo para compilar o código da fórmula em shell.                        |
| `metadata.json file` | Arquivo para "taguear" informações de uma fórmula.                         |
| `set_unmask.sh file` | Arquivo usado pelo `Makefile file`                                        |
| `help.json files`    | Arquivos usados para configurar mensagens de ajuda da fórmula no CLI.     |

- Você pode encontrar todos os [**templates de linguagens**](https://github.com/ZupIT/ritchie-formulas/tree/master/templates/create_formula/languages) no repositório [**ritchie-formulas**](https://github.com/ZupIT/ritchie-formulas).

### **Exemplos de pastas de fórmulas**

{{< tabs id="T" >}}
{{% tab name="Golang" %}}
![](/shared/go.png)

De acordo com a imagem acima, você deve editar os arquivos:

* **config.json:** Alterar os _**inputs**_ e suas configurações.
* **main.go:** Extrair os inputs, e chamar os métodos da fórmula (na pasta **formula/\***).
* **formula/*:** Implementar a lógica da fórmula.
* **help.json:** Alterar a mensagem de descrição do comando.
{{% /tab %}}

{{% tab name="Java" %}}
![](/shared/java.png)

De acordo com a imagem acima, você deve editar os arquivos:

* **config.json:** Alterar os _**inputs**_ e suas configurações.
* **main.java:** Extrair os inputs, e chamar os métodos da fórmula (na pasta **formula/\***).
* **formula/*:** Implementar a lógica da fórmula.
* **help.json:** Alterar a mensagem de descrição do comando.
{{% /tab %}}

{{% tab name="Node" %}}
![](/shared/node.png)

De acordo com a imagem acima, você deve editar os arquivos:

* **config.json:** Alterar os _**inputs**_ e suas configurações.
* **index.js:** Extrair os inputs, e chamar os métodos da fórmula (na pasta **formula/\***).
* **formula/*:** Implementar a lógica da fórmula.
* **help.json:** Alterar a mensagem de descrição do comando.
{{% /tab %}}

{{% tab name="Python" %}}
![](/shared/python.png)

De acordo com a imagem acima, você deve editar os arquivos:

* **config.json:** Alterar os _**inputs**_ e suas configurações.
* **main.py:** Extrair os inputs, e chamar os métodos da fórmula (na pasta **formula/\***).
* **formula/*:** Implementar a lógica da fórmula.
* **help.json:** Alterar a mensagem de descrição do comando.
{{% /tab %}}

{{% tab name="Shell" %}}
![](/shared/shell.png)

De acordo com a imagem acima, você deve editar os arquivos:

* **config.json:** Alterar os _**inputs**_ e suas configurações.
* **main.sh:** Extrair os inputs, e chamar os métodos da fórmula (na pasta **formula/\***).
* **formula/*:** Implementar a lógica da fórmula.
* **help.json:** Alterar a mensagem de descrição do comando.
{{% /tab %}}
{{< /tabs >}}
