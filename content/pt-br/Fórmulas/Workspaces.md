---
title: Workspaces
weight: 44
description: >-
  Você encontrará nessa seção informações sobre como usar workspaces no Ritchie.
---

---

## Qual a diferença entre workspace e repositório?

Repositórios e workspaces são ambos usados para interagir com as fórmulas no Ritchie em situações diferenciadas, veja abaixo a diferença:

**`workspace`** Você pode usar os comandos do workspace para desenvolver, editar e testar fórmulas `locais`.

**`repository`** Você pode usar o repositório para fazer o download de fórmulas de `repositórios git` e usa-las.

*Tem um exemplo de adição de repositório na seção [**Executar uma fórmula Hello World**](/docs-ritchie/pt-br/fórmulas/executar-uma-fórmula-hello-world/).*

Os comandos para repos e workspaces são similares, ambos permitem o CLI 'ver' as fórmulas disponíveis. Os workspaces possuem **prioridade mais alta** que os Repos (se você usar os dois comandos para os mesmos repositórios de fórmulas, os workspaces serão executados).

Veja mais sobre os comandos de workspace e repositórios na [**lista de comandos e flags**](/docs-ritchie/pt-br/referência/lista-de-comandos-e-flags/).

## Como Adicionar?

Execute esse comando para adicionar um novo workspace:

```text
rit add workspace
```

Você deverá informar alguns parâmetros de entrada antes da sua execução:

**Etapa 1:** Informe o nome do workspace (não use *espaços* ou *caracteres especiais*).

**Etapa 2:** Informe o caminho (*path*) do workspace na máquina local.

![](/shared/add-workspace.gif)

## Como Listar?

Execute esse comando para adicionar listar os workspaces da máquina:

```text
rit list workspace
```

![](/shared/list-workspace.gif)

## Como Atualizar?

Se você não é a única pessoa trabalhando num workspace (por exemplo: se for um repositório clonado do git), pode ser necessário atualizar o workspace para permitir que a CLI "veja" novas fórmulas disponíveis (ou atualizações) na máquina local, após fazer o *pull* o código.

Para atualizar um espaço de trabalho, você só precisa executar este comando:

```text
rit update workspace
```

Depois disso, selecione o nome do workspace e aguarde a mensagem de saída do CLI.

![](/shared/update-workspace.gif)

## Como Apagar?

Para excluir um workspace, você só precisa executar este comando:

```text
rit delete workspace
```

Depois disso, siga as etapas:

**Etapa 1:** Selecione o workspace

**Step 2:** Confirme que deseja excluir o workspace.

![](/shared/delete-workspace.gif)

## Próximos passos

Nesta seção, você viu como usar workspacesno Ritchie. Para continuar lendo mais:

👉 Vá para seção [**como encapsular fórmulas**](/docs-ritchie/pt-br/fórmulas/encapsular-fórmulas/) para descobrir como se executa uma fórmula dentro de outra fórmula.

👉 Conheça a [**lista de comandos**](/docs-ritchie/pt-br/referência/lista-de-comandos-e-flags/) de fórmulas disponíveis no Ritchie.
