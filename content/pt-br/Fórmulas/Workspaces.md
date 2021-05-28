---
title: Workspaces
weight: 44
description: >-
  Você encontrará nessa seção informações sobre como usar workspaces no Ritchie.
---

---

## Qual a diferença entre workspace e repositório?

Repositórios e workspaces são usados para interagir com as fórmulas no Ritchie, mas em situações diferentes, veja abaixo:

**`workspace`** Você pode usar os comandos do workspace para desenvolver, editar e testar fórmulas `locais`.

**`repository`** Você pode usar o repositório para fazer o download de fórmulas de `repositórios git` e usa-las.

*Veja o exemplo de adição de repositório na seção [**Executar uma fórmula Hello World**](/docs-ritchie/pt-br/fórmulas/executar-uma-fórmula-hello-world/).*

Os comandos para repos e workspaces são similares, eles permitem que o CLI 'veja' as fórmulas disponíveis. Os workspaces possuem **prioridade mais alta** que os Repos, se você usar, por exemplo, os dois comandos para os mesmos repositórios de fórmulas, os workspaces serão executados.

Veja mais sobre os comandos de workspace e repositórios na [**lista de comandos e flags**](/docs-ritchie/pt-br/referência/lista-de-comandos-e-flags/).

## Como Adicionar?

Siga os passos para adicionar:

**Passo 1:** Execute o comando abaixo para adicionar um novo workspace:

```text
rit add workspace
```

**Passo 2:** Informe alguns parâmetros de entrada antes da sua execução:

1: Informe o nome do workspace (não use espaços ou caracteres especiais).

2: Informe o caminho (path) do workspace na sua máquina local.

![](static/shared/add-workspace.gif)

## Como Listar?

Execute o comando abaixo para listar os workspaces da máquina:

```text
rit list workspace
```

![](static/shared/list-workspace.gif)

## Como Atualizar?

Se você não é a única pessoa trabalhando em um workspace (por exemplo: se for um repositório clonado do Git), é necessário atualizar o workspace para permitir que a CLI "veja" as novas fórmulas ou atualizações disponíveis na sua máquina local, após fazer o *pull* o código.

Para atualizar um espaço de trabalho, execute o comando abaixo:

```text
rit update workspace
```

Depois disso, selecione o nome do workspace e aguarde a mensagem de saída do CLI.

![](static/shared/update-workspace.gif)

## Como Apagar?

Para excluir um workspace, você só precisa executar este comando:

```text
rit delete workspace
```

Depois disso, siga os passos:

**Passo 1:** Selecione o workspace;

**Passo 2:** Confirme que você deseja excluir o workspace.

![](static/shared/delete-workspace.gif)

## Próximos passos

Nesta seção, você viu como usar workspaces no Ritchie. Para continuar lendo mais:

👉 Conheça a [**lista de comandos**](/docs-ritchie/pt-br/referência/lista-de-comandos-e-flags/) de fórmulas disponíveis no Ritchie.
