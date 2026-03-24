---
title: Adicionar regras de porcentagem aos critérios de público
description: Saiba como adicionar regras baseadas em porcentagem nos critérios de público-alvo em implantações de experiência do Adobe para direcionar porcentagens de implantação diferentes para segmentos de público-alvo diferentes.
source-git-commit: ae420329b94b24fcd173734b414aecf1c5fc16ca
workflow-type: tm+mt
source-wordcount: '376'
ht-degree: 0%

---


# Adicionar regras de porcentagem aos critérios de público {#adding-percentage-rules}

## Quando usar as regras de porcentagem na guia Público-alvo {#when-to-use}

O campo **porcentagem de implantação** da guia Detalhes básicos aplica uma única porcentagem a todo o público-alvo. Por exemplo, 50% de implantação significa que 50% de todos os usuários que correspondem aos critérios de público-alvo recebem o recurso.

No entanto, alguns cenários de implantação exigem porcentagens diferentes para grupos diferentes — por exemplo:

* 100% dos usuários do Reino Unido e 50% dos usuários dos EUA
* Todos os usuários de uma lista de email importada, mais 50% dos usuários de um país específico

Nesses casos, use a regra de **Porcentagem** na seção de perfil da guia **Público**, combinada com lógica aninhada.

>[!TIP]
>
>Se você quiser aplicar uma única porcentagem a todo o público-alvo (por exemplo, 10% dos usuários nos EUA e Reino Unido), use a **porcentagem de implantação** na guia Detalhes básicos.

## Como adicionar uma regra de porcentagem {#how-to-add}

A opção **Percentage** está disponível como uma regra na seção Perfil da guia Público-alvo.

1. Vá para a guia **Público** do sinalizador de recurso ou grupo de recursos.
2. Em **Perfil**, adicione uma regra de **Porcentagem** e defina o valor desejado.
3. Adicione outras condições de público-alvo necessárias (por exemplo, uma regra de País).

## Combinação de regras de porcentagem com lógica aninhada {#nested-logic}

Para aplicar porcentagens diferentes a segmentos diferentes, use a **lógica aninhada** para combinar as condições:

1. Habilite a **Lógica aninhada** na seção de regras de público-alvo.
2. Cada condição recebe um número automaticamente.
3. Insira uma expressão lógica que faça referência a esses números.

Use uma das seguintes expressões para descrever a relação entre suas condições:

* `1 and (2 or 3)` — condição 1 AND (condição 2 OR condição 3)
* `(1 and 2) or 3` — (condição 1 E condição 2) OU condição 3
* `(1 and 2) or (3 and 4)` — dois grupos independentes

## Exemplos {#examples}

**Exemplo 1: Todos os usuários de uma lista importada e 10% dos usuários de um país específico**

Adicione duas regras: uma para a lista de usuários importada e uma regra de Porcentagem (10%) combinada com uma regra de País. Usar lógica aninhada: `1 or (2 and 3)`.

**Exemplo 2: 10% de usuários dos EUA e 20% de usuários do Reino Unido**

Adicione quatro regras: País = EUA, Porcentagem = 10%, País = Reino Unido, Porcentagem = 20%. Usar lógica aninhada: `(1 and 2) or (3 and 4)`.

## Consulte também {#see-also}

* [Público-alvo em sinalizadores e grupos de recursos](audience-in-feature-flags-and-feature-groups.md)
* [Regras complexas de público](complex-rules.md)
* [Definir um recurso para implantação gradual](../feature-flags/set-feature-gradual-rollout.md)
