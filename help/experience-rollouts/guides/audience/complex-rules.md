---
title: Regras complexas de público
description: Saiba como trabalhar com conjuntos de regras de público-alvo grandes ou complexos em implantações do Adobe Experience, incluindo limites de valor em massa e como dividir regras em várias condições.
exl-id: 37e037b6-45eb-4261-b580-30d94d8e55da
source-git-commit: 4a3133f014a9bb9d6ed26eb9d9f763db79ce63b3
workflow-type: tm+mt
source-wordcount: '230'
ht-degree: 0%

---

# Regras complexas de público {#complex-rules}

## Limites de valor em massa {#bulk-value-limits}

Ao adicionar um grande número de valores a uma única regra de público-alvo (por exemplo, uma longa lista de endereços de email), você pode encontrar um erro indicando que a regra excedeu o tamanho máximo permitido.

Cada regra de público-alvo tem um limite de tamanho por atributo. Para endereços de email, o limite depende do comprimento total de caracteres das entradas, em vez de uma contagem fixa. Como orientação geral, use aproximadamente **100-115 endereços de email por regra**.

Se você precisar direcionar mais entradas do que esse limite permite, divida a lista em partes menores e aplique-as como condições separadas conectadas OR usando a lógica aninhada.

## Uso de lógica aninhada para regras complexas {#nested-logic}

A lógica aninhada permite combinar várias condições de público-alvo com controle AND/OR preciso. Para ativá-lo:

1. Adicione as condições de público-alvo necessárias.
2. Habilite a **Lógica aninhada** na seção de regras de público-alvo.
3. Cada condição recebe um número. Insira uma expressão lógica que faça referência a esses números, por exemplo:
   * `1 and (2 or 3)`
   * `(1 and 2) or 3`
   * `(1 and 2) or (3 and 4)`

Esse é o mesmo mecanismo usado para regras de porcentagem em combinação com outros critérios. Consulte [Adicionar regras de porcentagem nos critérios de público-alvo](adding-percentage-rules.md) para ver exemplos trabalhados.

## Consulte também {#see-also}

* [Público-alvo em sinalizadores e grupos de recursos](audience-in-feature-flags-and-feature-groups.md)
* [Adicionar regras de porcentagem aos critérios de público](adding-percentage-rules.md)
