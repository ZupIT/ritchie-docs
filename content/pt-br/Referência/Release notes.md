---
title: Release Notes
weight: 8
description: >-
  Nesta seção, você encontra as Release Notes do Ritchie.
---

{{% release/group %}}
{{% release/item type="feature"  date="Julho 2021" %}}
Adição do comando **'rit list formulas'**.

Adição de uma atualização com a opção para executar a última versão de uma fórmula quando ativada. 
 
Adição de uma biblioteca para dar suporte a internacionalização do Ritchie-CLI. 

Adição da primeira parte do recurso de saída da fórmula.

Detecção da nova versão do repo usando o cache.

Criação de uma configuração para forçar a execução da fórmula na versão mais recente.

Adição de uma configuração para mount volumes via **config.json**.

Criação da fórmula e verificação do arquivo **config.json** para ver a tag da release.


{{% /release/item %}}


{{% release/item type="fix" date="Julho 2021" %}}
Atualização da execução de uma fórmula com Docker para evitar a criação de arquivos com o dono root. 

Adição de um suporte para Docker da versão mais nova até a mais antiga para usuários do MacOS e WSL.

Correção das saídas de fórmulas (formulas outputs).
{{% /release/item  %}}


{{% release/item type="chore" date="Julho 2021" %}}
Adição de testes e sinalizadores de suporte para **rit delete repo**.

Melhoria na mensagem de erro no repositório de atualização. 

Melhoria para salvar e reutilizar credenciais de repositórios para repositórios privados.

Testes de refatoração dos pacotes das flags.

Adição de testes com o testify para repositórios delete. 

Remoção do bot stale.

Melhoria das métricas extraídas pelas input flags.

{{% /release/item  %}}

{{% release/item type="docs"  date="Junho 2021" %}}
 Migração da documentação do Gitbook para o Hugo.
{{% /release/item  %}}
{{% /release/group %}}
 
Veja mais em [**Release Notes**](https://github.com/ZupIT/ritchie-cli/releases). 
