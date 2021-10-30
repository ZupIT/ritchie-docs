---
title: Inicialização do CLI
weight: 17
description: 'Nesta seção, você vai encontrar como inicializar o rit.'
---

---
Veja abaixo os passos para você inicializar a CLI: 

## **Passo 1: Inicialização** 

Execute o comando para inicializar o Ritchie:

```text
rit init
```

Esse comando vai pedir **três informações**:

1. Se o usuário **quer contribuir anonimamente** as métricas do produto.
2. Se o usuário **quer adicionar as fórmulas** da comunidade localmente.
3. Qual **método de execução** o usuário deseja usar por **padrão** (local ou docker). [**método de execução de fórmulas**]({{< ref path="Fórmulas/Executar fórmulas" >}}) **local ou via docker**.

![](/shared/rit-init.gif)

Depois disso, todos os arquivos de configuração para a máquina funcionar serão criados.

## **Passo 2: Verifique a inicialização**

### 1. Repositório da comunidade

Se você adicionou o repositório da comunidade, é possível verificar a importação com o comando:

```text
rit list repo
```

Esse comando retorna todos os repositórios de fórmulas que o usuário tem acesso localmente.

![](/shared/rit-list-repo.gif)

### 2. Pasta Ritchie

Você pode verificar se a pasta **`.rit`** foi criada no diretório **`$HOME`** da máquina.

{{% alert color="info" %}}

Todas as operações realizadas usando o Ritchie são salvas nessa pasta **.rit** (credenciais, repos, métricas...).

{{% /alert %}}
