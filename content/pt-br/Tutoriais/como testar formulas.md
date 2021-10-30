---
title: Como testar outputs de formulas 
weight: 90
description: >-
  Nesta seção, você vai encontrar o tutorial para testar outputs de fórmulas no Ritchie.

---

Esse tutorial ajuda a você criar e configurar o workflow do Github actions para testar os outputs das suas fórmulas. 

## **Requisitos**

- Você precisa da fórmula **`rit math sum numbers`** no repositório do Github. 
- Você precisa do diretório **.github/workflows** criado no repositório do Github.


## **Como fazer isso?** 

Siga os próximos passos para testar uma fórmula: 

**Passo 1:** Crie um arquivo no diretório **.github/workflows** com o nome **`test-formula-sum-numbers.yml`**.

**Passo 2:** Cole a implementação do yaml:

```
yaml
name: Formula Sum Numbers

on:
  push:
  workflow_dispatch:

jobs:
  formula-sum-numbers-job:
    runs-on: ubuntu-latest
    steps:
      - uses: actions/checkout@v2.3.4    //requirement to the test-cli-commands-action
      - uses: actions/setup-node@v2    // requirement to the test-cli-commands-action
        with:
          node-version: '14'
      - name: Ritchie Installation
        run: curl -fsSL https://commons-repo.ritchiecli.io/install.sh | bash
      - name: Ritchie Initialization
        run: echo '{"addCommons":false, "sendMetrics":false, "runType":"local"}' | rit init --stdin
      - name: Add current formula repository as workspace
        run: rit add workspace --name="current_repo" --path="./"
      - uses: GuillaumeFalourd/test-cli-commands-action@v1
        with:
          command_line: rit math sum numbers —rit_number_one=1 —rit_number_two=2
          contains: The sum is 3
          expected_result: PASSED

```

**Passo 3:** Depois de comitar e dar o push no seu código, acesse a aba **Actions** do repositório:

![](/shared/actions-tab.PNG)

Você verá o **workflow run** sendo executado (ou o resultado da execução), veja abaixo: 

![](/shared/formula-sum-numbers.PNG)


**Cada push** no repositório irá agora iniciar esse workflow e você pode checar se a fórmula está comportando corretamente. 

Você pode atualizar a implementação do workflow para ser iniciado apenas quando a raiz do diretório da fórmula estiver atualizado, ou testar mais cenários de acordo com os inputs da fórmula. 

Para mais informações sobre sintaxe de workflow, acesse a [**documentação do Github**](https://docs.github.com/en/enterprise-server@3.0/actions/reference/workflow-syntax-for-github-actions). 
