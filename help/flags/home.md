---
title: Sinalizadores
description: Saiba como usar sinalizadores no Adobe Target para fornecer recursos de forma segura e gradual com implantações controladas, sinalizadores de recursos e gerenciamento de público-alvo direcionado.
hide: true
index: false
exl-id: c400d75d-d928-4cf6-a094-1a2f443389f0
source-git-commit: 8a3a8f0293e32db896f62a63ea6a886868ffe1a3
workflow-type: tm+mt
source-wordcount: '358'
ht-degree: 1%

---

# Sinalizadores {#experience-rollouts-home}

>[!AVAILABILITY]
>
>O sinalizador está atualmente no Beta e está disponível para clientes do Adobe Target. Entre em contato com seu representante da Adobe para solicitar acesso.

Os sinalizadores no Adobe Target permitem que as equipes de produtos enviem novos recursos de forma gradual e segura — sem reimplantações ou tempo de inatividade. Você define quem vê o quê, quando e em que ritmo. Se algo der errado, desligue o recurso imediatamente. Se tudo correr bem, você expande o público-alvo de acordo com sua programação.

## O que você pode fazer

**Controle quem vê os novos recursos.** Versões do Target para usuários, organizações, regiões ou atributos personalizados específicos. Comece com um pequeno grupo, valide a experiência e expanda — tudo a partir do console, sem alterações de código.

**Executar experimentos A/B.** Atenda a diferentes variantes para diferentes segmentos do seu público-alvo e avalie qual tem melhor desempenho. Use os resultados para tomar decisões informadas sobre o produto antes de um lançamento completo.

**Reduzir o risco de lançamento.** Divida grandes alterações em implantações menores e controladas. Se um erro ou problema de desempenho aparecer, desative somente o recurso afetado — o restante do aplicativo permanece estável.

**Coordenar entre aplicativos.** Os grupos de recursos permitem gerenciar vários sinalizadores de recursos juntos, compartilhando um público-alvo de implantação comum entre aplicativos.

**Exportar seus dados.** Exporte dados de Sinalizadores para o ambiente de relatórios de sua preferência para análise e medição junto com outros dados do Adobe.

## Integrar seu primeiro sinalizador

A obtenção de valor dos sinalizadores começa com três etapas:

1. **Acessar Sinalizadores por meio do Adobe Target** — Os sinalizadores estão disponíveis no Adobe Target. [Solicitar acesso](guides/console/request-access.md) e abrir Sinalizadores na interface do Target.

1. **Criar e publicar um sinalizador** — Siga o guia [Criar seu primeiro sinalizador de recurso](guides/feature-flags/create-your-first-feature-flag.md) para definir um sinalizador, definir seu público inicial e publicá-lo em seu ambiente.

1. **Integrar com seu aplicativo** — Conecte seu aplicativo usando o AEP Web SDK ou o AEP Mobile SDK para que ele possa recuperar e aplicar sinalizadores no tempo de execução. Comece com as [etapas de integração](guides/integrate/integration-steps.md) para o seu tipo de aplicativo.

Depois que o primeiro sinalizador estiver ativo, você poderá refinar o público-alvo, configurar uma implantação gradual e promovê-la de salva para implantação completa.

## Precisa de ajuda?

Se algo não se comportar conforme o esperado, entre em contato com o representante da Adobe para obter suporte.

<!-- 
Bob was here. Again.
-->
