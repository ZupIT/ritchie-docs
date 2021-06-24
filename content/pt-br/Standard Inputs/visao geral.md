---
title: Visão Geral
weight: 74
description: Nesta seção, você vai encontrar mais detalhes sobre as input flags

---
Informar parâmetros de entrada através de **argumentos** ou **flags** permite que você automatize workflows. É particularmente útil quando você estiver manipulando outras ferramentas dentro do script, assim você automatiza operações sem precisar interagir com o terminal.

![](/shared/screen-shot-2020-08-27-at-15.22.10.png)

Basicamente, há duas formas de informar os parâmetros de entrada diretamente na linha de comando:

1. Por meio da flag STDIN;     _**\(será depreciado no início de 2021\)**_
2. Por meio de Input flags.


{{% alert color="info" %}}

As Input flags do Ritchie foram desenvolvidas para oferecer mais uma opção para quem usa os parâmetros de entrada por meio de linha de comando. 

Nesse caso, os parâmetros de entrada precisam ser informados seguindo o padrão:

`RIT (GROUP) VERB NOUN --input_name='input_value'` 
{{% /alert %}}

Você pode usar as regras do input flags em: 

👉 [**Comandos de fórmulas**](/pt-br/standard-inputs/comandos-de-fórmulas/)