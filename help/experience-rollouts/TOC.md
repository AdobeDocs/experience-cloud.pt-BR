---
audience: user
user-guide-title: Implantações de experiência do Adobe
user-guide-description: Saiba como usar implantações da Adobe Experience para gerenciar sinalizadores de recursos, implantações controladas e versões direcionadas em seus aplicativos.
source-git-commit: c654ca1507abcefcff84cef9f99830042939805d
workflow-type: tm+mt
source-wordcount: '291'
ht-degree: 6%

---


# Implantações de experiência do Adobe {#experience-rollouts}

+ [Visão geral](home.md)
+ Introdução {#get-started}
   + [Introdução às implantações de experiência](getting-started/introduction.md)
   + [Por que usar implantações de experiência](getting-started/why-use-experience-rollouts.md)
   + [Modos de implantações de experiência](getting-started/experience-rollouts-modes.md)
+ Conceitos {#concepts}
   + [O que é um sinalizador de recurso](concepts/what-is-a-feature-flag.md)
   + [Sinalizadores de recursos para ativar e desativar recursos](concepts/feature-flags-to-enable-disable-features.md)
   + [Grupos de recursos para controlar vários recursos](concepts/feature-groups-to-control-multiple-features.md)
   + [Conceito de gerenciamento de versões](concepts/concept-of-release-management.md)
   + [Gerenciamento de versões em implantações de experiência](concepts/release-management.md)
   + [Implantação gradual](concepts/gradual-rollout.md)
+ Guias {#guides}
   + Introdução ao console {#console}
      + [Faça logon no console Implantações de experiência](guides/console/log-in-to-the-console.md)
      + [Selecione sua sandbox](guides/console/environments-overview.md)
      + [Solicitar acesso](guides/console/request-access.md)
   + Aplicativos {#applications}
      + [Gerenciar aplicativos](guides/applications/manage-applications.md)
      + [Integrar seu aplicativo](guides/applications/onboard-your-application.md)
   + Integrar implantações de experiência {#integrate}
      + [Integrar implantações de experiência no seu aplicativo](guides/integrate/integrating-in-your-app.md)
      + [Guia de inicialização](guides/integrate/startup-guide.md)
      + [Aplicativos de desktop](guides/integrate/desktop-applications.md)
      + [Aplicativos móveis](guides/integrate/mobile-applications.md)
      + [Aplicações web](guides/integrate/web-applications.md)
      + [Serviços da web](guides/integrate/web-services.md)
      + [SDKs](guides/integrate/sdks.md)
      + [Etapas de integração](guides/integrate/integration-steps.md)
      + [Assinar o aplicativo de API no Adobe Developer Console](guides/integrate/subscribe-to-api-application.md)
   + Sinalizadores de recursos {#feature-flags}
      + [Recursos e grupos de recursos](guides/feature-flags/features-feature-groups-releases.md)
      + [Criar o primeiro sinalizador de recurso](guides/feature-flags/create-your-first-feature-flag.md)
      + [Definir um recurso para implantação gradual](guides/feature-flags/set-feature-gradual-rollout.md)
      + [Criar um grupo de recursos](guides/feature-flags/create-a-feature-group.md)
      + [Definir um grupo de recursos para implantação gradual](guides/feature-flags/set-feature-group-gradual-rollout.md)
      + [Teste A/B com sinalizadores de recursos](guides/feature-flags/a-b-testing.md)
      + [Perguntas frequentes sobre gerenciamento de versão](guides/feature-flags/release-management-faqs.md)
      + [Analytics](guides/feature-flags/analytics.md)
      + [Agendar](guides/feature-flags/schedule.md)
   + Critérios de público {#audience}
      + [Público-alvo em sinalizadores e grupos de recursos](guides/audience/audience-in-feature-flags-and-feature-groups.md)
      + [Usar contexto nas regras de público](guides/audience/using-context-in-audience-rules.md)
      + [Regras complexas de público](guides/audience/complex-rules.md)
      + [Usar dados da organização corporativa nas regras de público-alvo](guides/audience/using-enterprise-org-data.md)
      + [Adicionar regras de porcentagem aos critérios de público](guides/audience/adding-percentage-rules.md)
      + [Regra de público-alvo com variável de contexto de IP do cliente](guides/audience/clientip-rule.md)
   + Fluxos de trabalho entre ambientes {#cross-environment}
      + [Conceito entre ambientes](guides/cross-environment/cross-environment-concept.md)
      + [Associar ambientes a um aplicativo](guides/cross-environment/associate-environments.md)
      + [Exibir sinalizadores de recursos entre ambientes](guides/cross-environment/view-feature-flags-across-environments.md)
      + [Importar sinalizadores de recursos](guides/cross-environment/import-feature-flags.md)
   + Suporte {#support}
      + [Solução de problemas](guides/support/troubleshooting.md)
      + [Obter suporte](guides/support/get-support.md)
      + [Entrar em contato com o suporte](guides/support/contact-support.md)
   + Versões do SDK {#sdk-releases}
      + SDK do Java {#java-sdk}
         + [Guia de integração do Java SDK](guides/sdk-releases/java/java-sdk-integration-guide.md)
         + [Notas de versão do Java SDK](guides/sdk-releases/java/java-sdk-release-notes.md)
      + SDK Node.js {#nodejs-sdk}
         + [Guia de integração do SDK Node.js](guides/sdk-releases/nodejs/nodejs-sdk-integration-guide.md)
         + [Notas de versão do Node.js SDK](guides/sdk-releases/nodejs/nodejs-sdk-release-notes.md)
      + [Benchmarking SDK](guides/sdk-releases/java-sdk-benchmarking.md)
+ API de recurso {#feature-api}
   + [API V3 de recursos do GET](feature-api/get-feature-api-v3.md)
   + [API V2 de recursos do GET](feature-api/get-feature-api-v2.md)
+ API de gerenciamento {#management-api}
   + [Visão geral das APIs de gerenciamento de recursos](management-api/feature-management-apis-overview.md)
   + [API de gerenciamento de sinalizadores de recursos](management-api/feature-flags-management-api.md)
   + [API de gerenciamento de grupos de recursos](management-api/feature-group-management-api.md)
   + [APIs de gerenciamento de versão](management-api/release-management-apis.md)
   + [Obter a ID do cliente para um aplicativo](management-api/get-client-id.md)
   + [Obtenha os critérios de público desejados](management-api/get-audience-criteria.md)
   + [API de patch de gerenciamento](management-api/management-patch-api.md)
