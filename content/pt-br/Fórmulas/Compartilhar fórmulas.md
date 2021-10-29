---
title: Compartilhar fórmulas
weight: 47
description: >-
  Nesta seção, você vai encontrar como compartilhar suas fórmulas em um repositório já criado no Ritchie.
---

---

## **Como compartilhar?**

Depois que o repositório de fórmulas for publicado, outros usuários podem adicionar suas fórmulas localmente a partir da **URL** de acesso a elas.

Exemplo: [**`https://github.com/ZupIT/ritchie-formulas`**](https://github.com/ZupIT/ritchie-formulas)

Para adicionar um novo repositório no Ritchie, é necessário rodar o comando abaixo:

```text
rit add repo
```

Uma vez que o repositório for adicionado, o Ritchie irá usar a versão da release selecionada do repositório para acessar as fórmulas disponíveis.

![](/shared/rit-share-formula.gif)

{{% alert color="warning" %}}

Se o repositório de fórmulas for **privado**, será necessário informar o token do seu Github/Gitlab.

{{% /alert %}}

## **Como checar a última versão do repositório?**

{{% alert color="info" %}}

Essa feature está disponível a partir da versão 2.2 do Ritchie.

{{% /alert %}}

No Ritchie, é possível checar novos comandos de fórmulas adicionados e checar se há uma nova versão de algum repositório que você tenha importado localmente.
Siga os próximos passos:

**Passo 1.** Executar o comando de ajuda **`rit --help`**. O sistema deve retornar a lista com grupo de repositórios disponíveis.

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

**Passo 2.** Se preferir, execute o comando **`rit list repo`**, que retorna informações dos repositórios importados, como a versão atual e a última versão disponível.

### **Como encontrar fórmulas de um repositório?**

{{% alert color="info" %}}

Essa feature está disponível a partir da versão 2.11 do Ritchie.

{{% /alert %}}

Quando você trabalha com vários grupos de fórmulas, pode ser difícil lembrar de cada comando disponível.

Se você quiser listar as fórmulas de um repositório específico, siga os passos abaixo:

1. Execute o comando de lista **`rit list formula`**. O sistema deve retornar a lista com o grupo de repositórios diponíveis e também a opção '**ALL**':

```text
? Repository:
  ALL
> repo-name-1
  repo-name-2
  ```

2. Selecione o repositório que você deseja (ou ALL para todos) e o sistema retorna uma lista com os comandos e uma breve descrição que foi definida no arquivo **`help.json`** de cada fórmula:

```text
? Repository: repo-name-1
COMMAND                                 DESCRIPTION
rit aws add terraform-eks               Generate terraform AWS eks
rit aws add terraform-vpc               Generate terraform AWS vpc
rit aws apply terraform                 Apply terraform on AWS
rit aws clean bucket                    Clean bucket AWS
rit aws create bucket                   Create bucket AWS
rit aws delete bucket                   Delete AWS objects

There are 6 formulas
```

### **Como eu posso atualizar?**

Para atualizar a versão de algum repositório local, você só precisa rodar o comando abaixo informando o nome do repositório e a versão desejada:

```text
rit update repo
```

## **Próximos passos**

Nesta seção, você viu como compartilhar uma fórmula no Ritchie. Para continuar configurando sua fórmula:

👉 Vá para página [**definir credenciais**]({{< ref path="Credenciais/Definir credenciais" >}}) e veja como rodar esse comando com suas fórmulas.

👉 Vá para página de [**lista de comandos**]({{< ref path="Referência/Lista de comandos e flags" >}}) para ver as automações disponíveis no repositório da nossa comunidade.
