---
title: Escolhendo uma versão
weight: 4
description: >-
  Nesta seção, você vai conhecer as versões disponíveis do Ritchie para fazer
  download.
---

---

## Introdução

Antes de começar a usar o Ritchie, é preciso optar por uma das versões disponíveis do nosso CLI:

* **Versão Single:** indicada para profissionais autônomos;
* **Versão Team:** indicada para equipes ou profissionais de uma corporação.

As duas versões foram criadas para atender às diferentes necessidades de analistas de infraestrutura, SREs, arquitetos ou engenheiros de software.

Na prática, a principal diferença entre as versões está no uso \(ou não\) de um servidor para armazenamento das **fórmulas**, obrigatório para quem utiliza a Versão Team, já que, no caso de quem utilizar o Ritchie para projetos corporativos, é necessário garantir segurança da informação para proteção de dados sensíveis.

![Arquitetura das vers&#xF5;es single e team](/shared/team-and-single.png)

## **Comparando versões**

![](/shared/screenshot-2020-06-15-at-16.48.44.png)

## Versão Single

As **principais características** desta versão são:

* Acesso às fórmulas desenvolvidas pela comunidade;
* Possibilidade de testar novas fórmulas em repositório local;
* Informações criptografadas na máquina local.

### Repositórios

Caso opte por utilizar a Versão Single, estes serão os repositórios que poderá acessar:

1. [**ritchie-cli**](https://github.com/ZupIT/ritchie-cli): contém o núcleo da ferramenta.
2. [**ritchie-formulas**](https://github.com/ZupIT/ritchie-formulas): contém as fórmulas compartilhadas com a comunidade que cada usuário do Ritchie pode acessar, atualizar e executar pelo terminal.

![Arquitetura da vers&#xE3;o single](/shared/single-ritchie.png)

## Versão Team

As **principais características** desta versão são:

* Acesso às fórmulas desenvolvidas pela comunidade e também às fórmulas da equipe;
* Possibilidade de testar novas fórmulas em repositório local;
* Informações criptografadas no servidor.

### Repositórios

No caso da Versão Team, é possível acessar mais repositórios. São eles:

1. [**ritchie-cli**](https://github.com/ZupIT/ritchie-cli): contém o núcleo da ferramenta.
2. [**ritchie-formulas**](https://github.com/ZupIT/ritchie-formulas): contém as fórmulas compartilhadas com a comunidade que cada usuário do Ritchie pode acessar, atualizar e executar pelo terminal.
3. [**ritchie-server**](https://github.com/ZupIT/ritchie-server): contém as integrações com as plataformas do [**Keycloak**](https://www.keycloak.org/) e do [**Vault**](https://www.vaultproject.io/), usados para criar a sessão e armazenar os dados do usuário com segurança.

{{% alert color="warning" %}}
Além de armazenar fórmulas organizacionais dentro de outros repositórios, é possível também acessá-las executando o [**comando do login**]({{< ref "Inicialização.md#comando-do-login" >}})
{{% /alert %}}

![Arquitetura da vers&#xE3;o team](/shared/team-ritchie-white.png)
