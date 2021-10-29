---
title: Upgrade do CLI
weight: 19
description: 'Nesta seção, você vai encontrar como fazer o upgrade do CLI.'
---

---

{{% alert color="info" %}}

Quando for lançada uma nova versão do CLI version, um aviso irá aparecer quando você for executar um dos comandos abaixo:

- **`rit`** _(helper)_
- **`rit -v`** _(version)_

{{% /alert %}}

Para atualizar a versão do Ritchie CLI quando a mensagem aparecer, rode o seguinte comando:

```text
rit upgrade
```

#### **Exemplo de comando output para versão 2.6.0**

```text
➜ rit upgrade

Rit upgraded with success
Release 2.6.0 description:
* Added multiselect input for formulas
* User is notified when adding the same repo and version
* Release notes are displayed on every upgrade
* Rit add repo will only add valid repos
* Context commands substituted by env commands
* Deprecated stdin
```

Esse output é baseado na descrição da tag da release na [**página de release notes do ritchie-cli no Github**](https://github.com/ZupIT/ritchie-cli/releases).
