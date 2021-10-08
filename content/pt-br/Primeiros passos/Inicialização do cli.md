---
title: Inicialização do CLI
weight: 17
description: 'Nesta seção, você verá como inicializar o rit.'
---

---

## Passo 1: Inicialização

Você deve executar o comando abaixo para inicializar o Ritchie:

```text
rit init
```

Esse comando vai pedir **três informações:**

1. Se o usuário **quer contribuir anonimamente** as métricas do produto.
2. Se o usuário **quer adicionar as fórmulas** da comunidade localmente.
3. Se o usuário **quer usar o** [**método de execução de fórmulas**]({{< ref path="Fórmulas/Executar fórmulas" >}}) **local ou via docker**.

![](/shared/rit-init.gif)

Após a execução desse comando, todos os arquivos de configuração para a máquina funcionar serão criados.

## Passo 2: Verifique a inicialização

### 1. Repositório da comunidade

Caso foi adicionado o repositório da comunidade, é possível verificar sua importação através do seguinte comando:

```text
rit list repo
```

Esse comando retorna todos os repositórios de fórmulas que o usuário tem acesso localmente.

![](/shared/rit-list-repo.gif)

### 2. Pasta Ritchie

É possível verificar que a pasta **`.rit`** foi criada no diretório **`$HOME`**  da máquina.

{{% alert color="info" %}}
Todas as operações realizadas usando o Ritchie são salvas nessa pasta  **.rit**  \(credenciais, repos, métricas...\)
{{% /alert %}}
