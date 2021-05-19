---
title: Renomear fórmulas
weight: 44
description: Você encontrará nessa seção informações sobre como renomear uma fórmula no Ritchie.
---

---

## Como renomear?

### Premissas

{{% alert color="warning" %}}
Somente fórmulas locais podem ser renomeadas.
{{% /alert %}}

## Renomeando sua fórmula

Você pode usar o comando core do Ritchie **`rit rename formula`** para renomear uma fórmula local. Os parâmetros de entrada necessários são:

1. O nome da fórmula antiga;
2. O novo nome da fórmula.

Exemplo: `rit group old` > `rit group new`

![](/shared/rit-rename-formula.gif)

{{% alert color="info" %}}

- O Ritchie identificará automaticamente o workspace a qual a fórmula pertence.
  - Caso identifique mais de um workspace com a fórmula informada, um passo extra necessário será executado pelo Ritchie para escolha do workspace a qual deve ter a fórmula renomeada.
- Essa fórmula possui entrada via _flags_, mais informações em [**Commandos core > Comandos de fórmula**](/docs-ritchie/pt-br/standard-inputs/comandos-core/#comandos-de-fórmula).
  {{% /alert %}}

## Efeitos

1. Todos os arquivos que identificam a fórmula serão alterados para o novo nome da fórmula

   _essas alterações refletirão tanto nas pastas internas de controle do Ritchie, quanto na pasta do workspace (sendo ele o default ou personalizado)_.

2. O autocomplete do Ritchie identificará somente o novo nome de fórmula.

## Próximos passos

Nessa seção, você viu como renomear uma fórmula no Ritchie. Para continuar configurando sua fórmula:

👉 Veja a seção [**como compartilhar fórmulas**](/docs-ritchie/pt-br/fórmulas/compartilhar-fórmulas/).
