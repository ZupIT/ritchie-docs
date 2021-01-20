---
title: Comandos Core
weight: 66
description: >-
  Nesta seção, você encontrará mais detalhes sobre comandos que podem ser usados
  via stdin.
---

---

## Comandos Core com STDIN

Aqui está o JSON usado para executar os comandos core do Ritchie através do **stdin**.

{{% alert color="warning" %}}
Será necessário adaptar o valor das variáveis para cada JSON retornar os resultados esperados nas operações. 
{{% /alert %}}

### Comandos gerais

rit init

```text
echo '{"addCommons":true, "sendMetrics":true, "runType":"local"}' | rit init --stdin
```

rit tutorial

```text
echo '{"tutorial":"enabled"}' | rit tutorial --stdin
```

### Comandos do Repo

rit add repo

```text
echo '{"provider":"Github", "name":"repoName", "version":"2.2.0", "url":"https://github.com/ZupIT/ritchie-formulas", "token": null, "priority":1}' | rit add repo --stdin
```

rit update repo

```text
echo '{"name":"repoName", "version":"2.2.0"}' | rit update repo --stdin
```

rit delete repo

```text
echo '{"name":"repoName"}' | rit delete repo --stdin
```

### Comandos de fórmula

rit create formula

```text
echo '{"formulaCmd":"rit demo create formula", "lang":"shell", "workspacePath":"/users/dennis/home/ritchie-formulas", "formulaPath":"/demo/create/formula"}' | rit create formula --stdin
```

rit build formula 

{{% alert color="danger" %}}
Sem suporte ainda
{{% /alert %}}

### Comandos de Contexto 

rit set context

```text
echo '{"context":"contextName"}' | rit set context --stdin
```

rit delete context

```text
echo '{"context":"contextName"}' | rit delete context --stdin
```

rit set credential

```text
echo '{"service":"provider", "type":"type", "credential": {"username":"credentialUsername","token": "credentialToken"}}' | rit set credential --stdin
```

## Comandos Core sem STDIN

Alguns comandos core não precisam da flag stdin para serem executados. Isso acontece porque, nesse caso, eles não precisam informar nenhum parâmetro de entrada:

* **`rit upgrade`**
* **`rit --version`**
* **`rit completion`**
* **`rit list repo`**
* **`rit list credential`**