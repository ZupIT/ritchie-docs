---
title: Criar  e atualizar fórmulas
weight: 29
description: 'Nesta seção, você vai encontrar o passo a passo para criar e atualizar fórmulas no Ritchie.'
---

---

## **Como criar?**

### **Crie sua fórmula**

Execute esse comando para criar uma fórmula:

```text
rit create formula
```

{{% alert color="warning" %}}

Para executar esse comando, você precisa ter, ao menos, um template no seu repositório Ritchie.

{{% /alert %}}

Você deverá informar alguns parâmetros de entrada antes da sua execução:

1. O **comando** (de preferência, com o **padrão `rit + grupo + verbo + substantivo`** para respeitar a [**árvore de comando**]({{< ref path="Referência/Glossário" >}})).
2. A **linguagem de programação** da fórmula.
3. O **espaço de trabalho (workspace)** utilizado para salvar os arquivos da fórmula.

{{% alert color="info" %}}

Quando você terminar de criar sua fórmula, ela será compilada (“buildada”) de acordo com o template e enviada para um repositório específico conforme o **espaço de trabalho** selecionado.

**Exemplo:** Se você escolher o **espaço de trabalho** `Default`:

```text
{
    "Default":"/home/user/ritchie-formula-local"
}
```

Um repositório associado a esse workspace será criado na pasta **`/home/user/.rit/repos`**, e adicionado no arquivo **`repositories.json`**:

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

{{% /alert %}}

**Exemplo:** `rit demo create formula`

![](/shared/rit_create_formula.gif)

### **Atualize sua fórmula**

Você pode atualizar a fórmula modificando seus arquivos do **espaço de trabalho**.
Para obter mais informações sobre quais arquivos modificar, acesse [**Organizar a pasta de fórmulas**]({{< ref path="Fórmulas/Organizar a pasta fórmulas" >}}).

Ao executar a fórmula pela primeira vez após modificar os arquivos no **espaço de trabalho**, o Ritchie aplicará a modificação e reconstruirá a fórmula automaticamente.

{{% alert color="warning" %}}

Não se esqueça de atualizar os testes unitários.

{{% /alert %}}

### **Teste sua fórmula**

Você pode testar a fórmula diretamente após sua criação. Isso é possível porque o comando **`rit create formula`** também constrói a fórmula automaticamente (ela gera os arquivos executáveis da fórmula e os adiciona na pasta **.rit folder**).

Nesse caso, o template da fórmula "Hello World"** será executado como você pode ver abaixo:

![](/shared/rit_demo_hello-world.gif)

Este template é composto por 4 parâmetros de entrada, que representam os tipos de inputs atualmente disponíveis para serem usados no Ritchie:

1. Uma amostra da **`variável de texto`**
2. Uma amostra da **`lista de variáveis de texto`**
3. Uma amostra da **`variável booleana`**
4. Uma amostra da **`variável de password`** 

## **Próximos passos**

Continue configurando a sua fórmula:
- Vá para a seção de como [**Organizar a pasta de fórmulas**]({{< ref path="Fórmulas/Organizar a pasta de fórmulas" >}}) para ver como organizar as fórmulas que você criou.
