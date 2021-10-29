---
title: How to test formulas outputs 
weight: 90
description: >-
  In this section, you will find a tutorial on how to test formulas outputs on Ritchie.

---

This tutorial will help you to create and configure a Github Action workflow to test your formula outputs.

## **Requirements**

- You need to have the **`rit math sum numbers`** formula on a Github repository. 
- You need a **.github/workflows** directory created on the Github repository.


## **How can you do that?** 

Follow the next steps to test a formula: 

**Step 1:** Create a file on the **.github/workflows** directory named **`test-formula-sum-numbers.yml`**.

**Step 2:** Paste the following yaml implementation inside of it:

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

**Step 2:** After you commit and push your code, go to the **Actions** tab’s repository:

![](/shared/actions-tab.PNG)

You will see the **workflow run** being executed (or the result of its execution), see below: 

![](/shared/formula-sum-numbers.PNG)


That’s it, **each push** to the repository will now trigger this workflow and you can also check if the formula is behaving correctly.

You are able to update the workflow implementation to trigger only when the formula’s root directory is updated, or to test more scenarios according to the formula's inputs.

For more information about workflow syntax, check out [**Github Documentation**](https://docs.github.com/en/enterprise-server@3.0/actions/reference/workflow-syntax-for-github-actions). 
