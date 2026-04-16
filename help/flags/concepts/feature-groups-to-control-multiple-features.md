---
title: Grupos de recursos para controlar vários recursos
description: Saiba como os grupos de recursos em Sinalizadores permitem agrupar e gerenciar sinalizadores de recursos relacionados entre aplicativos como uma única unidade.
hide: true
exl-id: dfeb7eff-34f1-4cb5-9c3e-a40d1eda3016
source-git-commit: b3e13a42c19eb7b8b7d5d402bf9a56f89f573044
workflow-type: tm+mt
source-wordcount: '173'
ht-degree: 0%

---

# Grupos de recursos para controlar vários recursos {#feature-groups}

Um [sinalizador de recurso](what-is-a-feature-flag.md) controla um único recurso. Quando você precisar gerenciar vários sinalizadores de recursos relacionados juntos e garantir que eles atinjam o mesmo público-alvo, use um **grupo de recursos**.

## O que um grupo de recursos faz {#what-it-does}

Um grupo de recursos agrupa vários sinalizadores de recursos e permite aplicar uma única regra de público-alvo a todos eles de uma só vez. Isso é útil quando um único recurso voltado para o usuário abrange vários aplicativos ou serviços.

Por exemplo, considere um recurso de colaboração que envolve alterações em um aplicativo de desktop, um aplicativo móvel e um serviço de back-end. Ao criar um grupo de recursos com sinalizadores dos três aplicativos, você pode abrir o recurso para 1% dos usuários e garantir que esses usuários vejam uma experiência consistente em todas as três superfícies simultaneamente.

## Agrupamento entre aplicativos {#cross-application}

Os grupos de recursos oferecem suporte ao gerenciamento de recursos entre aplicativos. Sinalizadores relacionados em vários aplicativos podem ser agrupados.


<!-- -->
