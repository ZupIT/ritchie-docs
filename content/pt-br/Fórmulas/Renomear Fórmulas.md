---
title: Renomear fórmulas
weight: 45
description: Nesta seção, você vai encontrar informações como renomear uma fórmula no Ritchie.
---

---

## **Como renomear uma fórmula?**

### **Premissas**

{{% alert color="warning" %}}

Somente fórmulas locais podem ser renomeadas.

{{% /alert %}}

## **Renomeando sua fórmula**

Você pode usar o comando core do Ritchie **`rit rename formula`** para renomear uma fórmula local. Os parâmetros de entrada necessários são:

1. O nome da fórmula antiga;
2. O novo nome da fórmula;
3. O nome do workspace.

- **Exemplo:** `rit group old` > `rit group new` > `Default`

![](/shared/rit-rename-formula.gif)

{{% alert color="info" %}}

- O Ritchie identifica automaticamente o workspace que a fórmula pertence.
- Se o CLI identificar mais de um workspace com a fórmula informada, um passo extra necessário (_quando for usada a execução via prompt_) será pedido pelo Ritchie, para escolher o workspace que deve ter a fórmula renomeada.
- Essa fórmula possui entrada via _flags_. 

Para mais informações, veja a seção [**Comandos de fórmula**]({{< ref path="/Standard Inputs/Comandos de fórmulas.md" >}}).
.
  {{% /alert %}}

## **Efeitos**

1. Todos os arquivos que identificam a fórmula serão alterados para o novo nome da fórmula. _Essas alterações refletirão tanto nas pastas internas de controle do Ritchie, quanto na pasta do workspace (sendo ele o default ou personalizado)_.

2. O autocomplete do Ritchie identificará somente o novo nome de fórmula.

## **Próximos passos**
Continue configurando a sua fórmula:

👉 Veja a seção [**como compartilhar fórmulas**]({{< ref path="/Fórmulas/Compartilhar fórmulas.md" >}}).
