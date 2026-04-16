---
title: Usar contexto nas regras de público
description: Saiba como usar variáveis de contexto em regras de público-alvo para sinalizadores de recursos e grupos de recursos em Sinalizadores.
hide: true
exl-id: 0367f475-9209-4d53-86b4-a739a73a23a7
source-git-commit: b3e13a42c19eb7b8b7d5d402bf9a56f89f573044
workflow-type: tm+mt
source-wordcount: '278'
ht-degree: 0%

---

# Usar contexto nas regras de público {#context-in-audience-rules}

As variáveis de contexto são valores fornecidos pelo aplicativo cliente no tempo de execução. Eles permitem definir usuários como alvo com base em informações dinâmicas no nível da sessão, como idioma ativo do usuário, tipo de dispositivo ou estado do aplicativo.

As variáveis de contexto são relevantes para os clientes móveis e da Web.

## Como as variáveis de contexto funcionam {#how-context-works}

Seu aplicativo passa variáveis de contexto para Sinalizadores ao avaliar um sinalizador de recurso. Você define regras no console que verificam esses valores, e a plataforma os usa no momento da avaliação para determinar se o usuário se qualifica.

## Tipos de variável de contexto {#variable-types}

### Tipo predefinido (lista) {#predefined-type}

Uma variável de contexto com um conjunto fixo de valores permitidos, como uma lista de idiomas ou países.

Operadores disponíveis: **Is**, **Is not equal to**, **Exists**, **In**

### Tipo inteiro {#integer-type}

Uma variável de contexto que contém um valor numérico.

Operadores disponíveis: **Maior que**, **Maior ou igual a**, **É**, **Menor que**, **Menor ou igual a**

### Tipo de string {#string-type}

Uma variável de contexto que contém um valor de texto de forma livre.

Operadores disponíveis: **É**, **Não é igual a**

## Adição de uma variável de contexto {#adding-context-variable}

Para adicionar uma variável de contexto a uma regra de público:

1. Abra o sinalizador de recurso ou o grupo de recursos no console.
2. Vá para a guia **Público-alvo**.
3. Em **Context**, adicione uma nova condição.
4. Selecione a variável de contexto, o operador e o valor.

Se a variável de contexto necessária não for exibida na lista, você poderá criar uma nova de maneira automatizada na seção de gerenciamento de variável de contexto do console.

## Consulte também {#see-also}

* [Público-alvo em sinalizadores e grupos de recursos](audience-in-feature-flags-and-feature-groups.md)
* [Adicionar regras de porcentagem aos critérios de público](adding-percentage-rules.md)

<!-- -->
