---
title: Grupos de recursos para controlar vários recursos
description: Saiba como os grupos de recursos em Implantações de experiência permitem agrupar e gerenciar sinalizadores de recursos relacionados entre aplicativos como uma única unidade.
source-git-commit: 1c8fd9b42d08f657b4e6b16efae86faa04d15565
workflow-type: tm+mt
source-wordcount: '251'
ht-degree: 1%

---


# Grupos de recursos para controlar vários recursos {#feature-groups}

Um [sinalizador de recurso](what-is-a-feature-flag.md) controla um único recurso. Quando você precisar gerenciar vários sinalizadores de recursos relacionados juntos e garantir que eles atinjam o mesmo público-alvo, use um **grupo de recursos**.

## O que um grupo de recursos faz {#what-it-does}

Um grupo de recursos agrupa vários sinalizadores de recursos e permite aplicar uma única regra de público-alvo a todos eles de uma só vez. Isso é útil quando um único recurso voltado para o usuário abrange vários aplicativos ou serviços.

Por exemplo, considere um recurso de colaboração que envolve alterações em um aplicativo de desktop, um aplicativo móvel e um serviço de back-end. Ao criar um grupo de recursos com sinalizadores dos três aplicativos, você pode abrir o recurso para 1% dos usuários e garantir que esses usuários vejam uma experiência consistente em todas as três superfícies simultaneamente.

## Agrupamento entre aplicativos {#cross-application}

Os grupos de recursos oferecem suporte ao gerenciamento de recursos entre aplicativos, desde que os sinalizadores pertençam à **mesma equipe** nas Implantações de Experiência. Uma equipe pode ter vários aplicativos, de modo que sinalizadores relacionados entre esses aplicativos possam ser agrupados.

## Grupos de recursos versus versões {#vs-releases}

| | Grupo de recursos | Versão |
|---|---|---|
| Escopo | Em uma única equipe | Em várias equipes |
| Caso de uso | Coordenar sinalizadores na sua equipe | Coordenação de lançamento de grandes equipes |
| Privilégios necessários | Nível da equipe | Mais alto (gerenciador de versões) |

Se os sinalizadores de recursos que você deseja agrupar pertencerem a aplicativos de propriedade de equipes diferentes, use uma [versão](release-management.md) em vez de um grupo de recursos.
