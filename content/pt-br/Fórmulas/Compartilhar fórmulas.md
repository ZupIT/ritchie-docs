---
title: Compartilhar fórmulas
weight: 46
description: >-
  Nesta seção, você vai encontrar detalhes de como compartilhar suas fórmulas em um repositório já
  criado no Ritchie.
---

---

## Como compartilhar?

Depois que o repositório de fórmulas for publicado, outros usuários podem adicionar suas fórmulas localmente a partir da URL de acesso a elas.

**Exemplo**: [**`https://github.com/ZupIT/ritchie-formulas`**](https://github.com/ZupIT/ritchie-formulas)

Para adicionar um novo repositório no Ritchie, é necessário rodar o comando abaixo:

```text
rit add repo
```

Uma vez que o repositório for adicionado, o Ritchie irá usar a versão da release selecionada do repositório para acessar as fórmulas disponíveis.

![](/shared/rit-add-repo-3.gif)

{{% alert color="warning" %}}

Se o repositório de fórmulas for **privado**, será necessário informar o token do seu Github/Gitlab.

{{% /alert %}}

##  Como checar a última versão do repositório?

{{% alert color="info" %}}

Essa feature está disponível a partir da versão 2.2 do Ritchie.

{{% /alert %}}

No Ritchie, é possível checar novos comandos de fórmulas adicionados e checar se há uma nova versão de algum repositório que você tenha importado localmente.

Para isso, basta você seguir os seguintes passos:

1. Executar o comando de ajuda **`rit --help`**. O sistema deve retornar a lista com grupo de repositórios disponíveis.

```text
(new version 2.12.1) commons repo commands:
  beagle      Beagle commands
  bitbucket   Manage bitbucket objects
  clean-swift Manage clean-swift objects
  docker      Manipulate Docker objects
  git         Manipulate Git objects
  github      Manipulate GitHub objects
  gitlab      Manipulate GitLab objects
  istio       Istio Service Mesh commands
  jupyter     Manage jupyter objects
  kafka       Kafka commands
  kubernetes  Manipulate kubernetes objects
  publish     Publish command
  scaffold    Manipulate scaffold objects
  xcode       Manage xcode objects
```

   2. Se preferir, execute o comando **`rit list repo`**, que retorna informações dos repositórios importados, como a versão atual e a última versão disponível.

### Como atualizo?

Para atualizar a versão de algum repositório local, você só precisa rodar o comando abaixo informando o nome do repositório e a versão desejada.

```text
rit update repo
```

## Próximos passos

Nesta seção, você viu como compartilhar uma fórmula no Ritchie. Para continuar configurando sua fórmula:

👉 Vá para página [**definir credenciais**](/docs-ritchie/pt-br/credenciais/definir-credenciais/) e veja como rodar esse comando com suas fórmulas.

👉 Vá para página de [**lista de comandos**](/docs-ritchie/pt-br/referência/lista-de-comandos-e-flags/) para ver as automações disponíveis no repositório da nossa comunidade.
