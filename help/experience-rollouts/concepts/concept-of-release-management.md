---
title: Conceito de gerenciamento de versões
description: Saiba como o gerenciamento de versões nas Implantações de experiência ajuda a coordenar implantações de recursos grandes e entre equipes por meio da sinalização de recursos.
source-git-commit: 1c8fd9b42d08f657b4e6b16efae86faa04d15565
workflow-type: tm+mt
source-wordcount: '264'
ht-degree: 0%

---


# Conceito de gerenciamento de versões {#concept-of-release-management}

As versões grandes compartilham alguns desafios comuns: várias equipes estão envolvidas, agendamentos de conflito e dependências são difíceis de coordenar. O gerenciamento de versões aborda esses desafios fornecendo uma maneira estruturada de implantar alterações sem problemas.

## O que significa gerenciamento de versões {#what-it-means}

O gerenciamento de versão abrange a coordenação de uma versão de ponta a ponta — do momento em que as equipes começam a desenvolver por trás dos sinalizadores de recursos até o momento em que o recurso está totalmente disponível para todos os usuários.

Ele permite que as equipes:

* Implantação independente na produção, em seu próprio ritmo, sem revelar recursos aos usuários finais
* Ativar somente quando todas as equipes participantes estiverem prontas
* Implante a versão gradualmente para um subconjunto de usuários antes da disponibilidade total

## Como funciona em implantações de experiência {#how-it-works}

O gerenciamento de versão nas Implantações de Experiência se baseia no conceito de [sinalização de recursos](what-is-a-feature-flag.md). Cada equipe implanta seu código na produção por trás de um sinalizador de recurso. Uma versão é então uma **coleção de sinalizadores de recursos definidos em vários aplicativos e equipes**.

Quando todas as equipes estão prontas, a versão pode ser ativada em uma única operação — ou implementada gradualmente — sem que nenhuma equipe individual precise reimplantar ou coordenar o tempo de implantação.

Essa abordagem oferece:

* **Implantação independente** — As equipes implantam de acordo com seu próprio agendamento sem afetar outras equipes ou usuários finais.
* **Ativação coordenada** — Todos os sinalizadores em uma versão são ativados juntos quando a versão é ativada.
* **Implantação gradual** — a versão pode ser aberta progressivamente para porcentagens crescentes de usuários.

Para obter detalhes sobre como configurar versões nas Implantações de Experiência, consulte [Gerenciamento de versões](release-management.md).
