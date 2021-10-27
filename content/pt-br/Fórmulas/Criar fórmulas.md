---
title: Criar fórmulas
weight: 29
description: 'Nesta seção, você vai encontrar o passo a passo para criar fórmulas no Ritchie.'
---

---

## Como criar?

### Passo 1: Execute o comando de criação de formula

Execute esse comando para criar uma fórmula:

```text
rit create formula
```

Você deverá informar alguns parâmetros de entrada antes da sua execução:

1. O **comando** (de preferência, com o **padrão `rit + grupo + verbo + substantivo`** para respeitar a [**árvore de comando**]({{< ref path="Glossário" >}})).
2. A **linguagem de programação** da fórmula.
3. **O caminho (path)** para salvar os arquivos da fórmula.

Exemplo: `rit demo create formula`

![](/shared/rit_create_formula.gif)

### **Passo 2: Teste sua fórmula**

Você pode testar diretamente a fórmula depois de sua criação. Isso é possível porque o comando **`rit create formula`** também constrói a fórmula automaticamente (ela gera os arquivos executáveis da fórmula e adiciona-os no **.rit folder**).

Nesse caso, o template da formula **"Hello World"** será executado como mostrado abaixo:

![](/shared/rit_demo_hello-world.gif)

Este template é composto por **3 parâmetros de entrada**, que representam os tipos de inputs atualmente disponíveis para serem usados no Ritchie:

1. Uma amostra das **`variáveis de texto`**
2. Uma amostra da **`lista de variáveis`**
3. Uma amostra das **`variáveis booleanas`**
4. Uma amostra das **`variáveis de password`**

Quando você terminar a criação da sua fórmula, ela será "buildada" e enviada para um repositório local específico de acordo com o nome do seu workspace, com o prefixo **"local"**.

Exemplo: se tiver um workspace com o nome `Default`.

```text
{
    "Default":"/home/user/ritchie-formula-local"
}
```

Um repositório associado a esse workspace será criado na pasta `/home/user/.rit/repos`, e adicionado no arquivo `repositories.json`.

```text
[
	{
		"provider": "Local",
		"name": "local-default",
		"version": "0.0.0",
		"url": "local repository",
		"priority": 0,
		"isLocal": true
	}
]
```

## Próximos passos

Nessa seção, você viu como criar e testar uma fórmula no Ritchie. Para continuar configurando a fórmula:

👉 Vá para a seção de como[ **organizar uma pasta de fórmula**]({{< ref path="Fórmulas/Organizar a pasta de fórmulas" >}}) para entender como editar os arquivos que o Ritchie cria depois da criação de uma fórmula.
