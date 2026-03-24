---
title: Implantações de experiência do Adobe
description: Saiba como usar as implantações de experiência do Adobe para fornecer recursos de forma segura e gradual com implantações controladas, sinalizadores de recursos e gerenciamento de público-alvo direcionado.
exl-id: c400d75d-d928-4cf6-a094-1a2f443389f0
source-git-commit: 65effd7e3b12404359e3693820bbf9e5080bea03
workflow-type: tm+mt
source-wordcount: '346'
ht-degree: 1%

---

# Implantações de experiência do Adobe {#experience-rollouts-home}

As implantações de experiência da Adobe permitem que as equipes de produtos forneçam novos recursos de forma gradual e segura — sem reimplantações ou tempo de inatividade. Você define quem vê o quê, quando e em que ritmo. Se algo der errado, desligue o recurso imediatamente. Se tudo correr bem, você expande o público-alvo de acordo com sua programação.

## O que você pode fazer

**Controle quem vê os novos recursos.** Versões do Target para usuários, organizações, regiões ou atributos personalizados específicos. Comece com um pequeno grupo, valide a experiência e expanda — tudo a partir do console, sem alterações de código.

**Executar experimentos A/B.** Atenda a diferentes variantes para diferentes segmentos do seu público-alvo e avalie qual tem melhor desempenho. Use os resultados para tomar decisões informadas sobre o produto antes de um lançamento completo.

**Reduzir o risco de lançamento.** Divida grandes alterações em implantações menores e controladas. Se um erro ou problema de desempenho aparecer, desative somente o recurso afetado — o restante do aplicativo permanece estável.

**Coordenar entre equipes.** Os grupos de recursos entre equipes permitem que várias equipes participem de uma única versão coordenada, cada uma gerenciando seus próprios sinalizadores de recursos enquanto compartilham um cronograma de implantação e público-alvo comuns.

## Integre seu primeiro recurso

A obtenção de valor das implantações de experiência começa com três etapas:

1. **Configure sua equipe e seu aplicativo** — [Solicite acesso](guides/console/request-access.md) ao console e [integre seu aplicativo](guides/applications/onboard-your-application.md) para que a Experience Rollups saiba quais clientes devem ser atendidos.

2. **Criar e publicar um sinalizador de recurso** — Siga o guia [Criar seu primeiro sinalizador de recurso](guides/feature-flags/create-your-first-feature-flag.md) para definir um sinalizador, definir seu público inicial e publicá-lo em seu ambiente.

3. **Integrar com seu aplicativo** — Conecte seu aplicativo à API de Implantações de Experiência ou ao SDK para que ele possa recuperar e aplicar sinalizadores de recursos no tempo de execução. Comece com as [etapas de integração](guides/integrate/integration-steps.md) para o seu tipo de aplicativo.

Depois que o primeiro sinalizador estiver ativo, você poderá refinar o público-alvo, configurar uma implantação gradual e promovê-la pelos [estados de versão](guides/feature-flags/release-states.md), desde a implantação salva até a completa.

## Precisa de ajuda?

Se algo não se comportar conforme o esperado, o [guia de solução de problemas](guides/support/troubleshooting.md) aborda os problemas mais comuns. Para qualquer outra coisa, [contate o suporte](guides/support/contact-support.md).
