---
title: Comandos Core
weight: 68
description: >-
  Nesta seção, você vau encontrar mais detalhes sobre comandos que podem ser usados via stdin.
---

---

## **Comandos Core com STDIN** 

Aqui está o JSON usado para executar os comandos core do Ritchie através do **stdin**.

{{% alert color="warning" %}}

Será necessário adaptar o valor das variáveis para cada JSON retornar os resultados esperados nas operações.

{{% /alert %}}

### **Comandos gerais**

rit init

```text
echo '{"addCommons":true, "sendMetrics":true, "runType":"local"}' | rit init --stdin
```

rit tutorial

```text
echo '{"tutorial":"enabled"}' | rit tutorial --stdin
```

### **Comandos do Repo**

rit add repo

```text
echo '{"provider":"Github", "name":"repoName", "repoU":"https://github.com/ZupIT/ritchie-formulas", "token": null, "priority":1, "tag"="2.2.0"}' | rit add repo --stdin
```

rit update repo

```text
echo '{"name":"repoName", "tag":"2.2.0"}' | rit update repo --stdin
```

rit delete repo

```text
echo '{"name":"repoName"}' | rit delete repo --stdin
```

### **Comandos de fórmula**

rit create formula

```text
echo '{"formula":"rit demo create formula", "lang":"shell", "workspacePath":"/users/dennis/home/ritchie-formulas", "formulaPath":"/demo/create/formula"}' | rit create formula --stdin
```

rit build formula

{{% alert color="danger" %}}

Sem suporte ainda

{{% /alert %}}

### **Comandos de Ambiente**

rit set env

```text
echo '{"env":"envName"}' | rit set env --stdin
```

rit delete env

```text
echo '{"env":"envName"}' | rit delete env --stdin
```

### **Comandos de Credenciais**

rit set credential

```text
echo '{"service":"provider", "type":"type", "credential": {"username":"credentialUserna
```

rit delete credential

```text
echo '{"provider":"provider"}' | rit delete credential --stdin
```

## **Comandos Core sem STDIN**

Alguns comandos core não precisam da flag stdin para serem executados. Isso acontece porque, nesse caso, eles não precisam informar nenhum parâmetro de entrada:

* **`rit upgrade`**
* **`rit --version`**
* **`rit completion`**
* **`rit list repo`**
* **`rit list credential`**
* **`rit show env`**
