---
title: Workspaces
weight: 44 
description: >-
  Nesta seção, Você vai encontrar informações como usar workspaces no Ritchie.
---

---

## **Qual a diferença entre workspace e repositório?**

Repositórios e workspaces são usados para interagir com as fórmulas no Ritchie, mas em situações diferentes, veja abaixo:

1. **`workspace`**: Você pode usar os comandos do workspace para desenvolver, editar e testar fórmulas `locais`.

2. **`repository`**: Você pode usar o repositório para fazer o download de fórmulas de `repositórios Git` e usá-las.

- Veja um exemplo de adição de repositório na página [**Executar uma fórmula Hello World**]({{< ref path="Fórmulas/Executar uma fórmula hello world" >}}).

Os comandos para repos e workspaces são similares, eles permitem que o CLI 'veja' as fórmulas disponíveis. Os workspaces possuem **prioridade mais alta** que os Repos, se você usar, por exemplo, os dois comandos para os mesmos repositórios de fórmulas, os workspaces serão executados.

Para mais informações sobre os comandos de workspace e repositórios, veja a [**lista de comandos e flags**]({{< ref path="Referência/Lista de comandos e flags" >}}).

## **Como adicionar?**

Siga os passos para adicionar:

**Passo 1:** Execute o comando abaixo para adicionar um novo workspace:

```text
rit add workspace
```

**Passo 2:** Informe alguns parâmetros de entrada antes da sua execução:

- 1: Informe o nome do workspace (não use espaços ou caracteres especiais).
- 2: Informe o caminho (path) do workspace na sua máquina local.

![](/shared/rit-add-workspace.gif)

## **Como listar?**

Execute o comando abaixo para listar os workspaces da máquina:

```text
rit list workspace
```

![](/shared/rit-list-workspace.gif)

## **Como atualizar?**

Se você não é a única pessoa trabalhando em um workspace (por exemplo: se for um repositório clonado do Git), é necessário atualizar o workspace para permitir que a CLI "veja" as novas fórmulas ou atualizações disponíveis na sua máquina local, após fazer o *pull* o código.

Para atualizar um espaço de trabalho, execute o comando abaixo:

```text
rit update workspace
```

Depois disso, selecione o nome do workspace e aguarde a mensagem de saída do CLI:

![](/shared/rit-update-workspace.gif)

## **Como apagar?**

Para excluir um workspace, execute o comando:

```text
rit delete workspace
```

Depois disso, siga os passos:

**Passo 1:** Selecione o workspace;

**Passo 2:** Confirme que você deseja excluir o workspace:

![](/shared/rit-delete-workspace.gif)

## **Aprenda Mais**
- Conheça a [**lista de comandos**]({{< ref path="Referência/Lista de comandos e flags" >}}) de fórmulas disponíveis no Ritchie.
