---
title: Guia de inicialização
description: Siga estas etapas para integrar seu aplicativo às implantações de experiência da Adobe, desde a solicitação de acesso até a criação do primeiro sinalizador de recurso.
exl-id: 7aa09535-45fa-4ddf-9e3f-a23f8a8ee666
source-git-commit: 2a946868f58e25f8aafbf3ccfcf6571e7d0d8d20
workflow-type: tm+mt
source-wordcount: '286'
ht-degree: 1%

---

# Guia de inicialização {#startup-guide}

Siga estas etapas para integrar Implantações de experiência ao seu aplicativo.

## Etapa 1: solicitar acesso {#step-1-access}

Solicite acesso ao console Implantações de experiência e junte-se à sua equipe. Consulte [Solicitar acesso](../console/request-access.md) para obter instruções passo a passo.

## Etapa 2: integrar seu aplicativo {#step-2-onboard}

Depois de obter acesso, faça logon no console Implantações de experiência e verifique se seu aplicativo está listado na equipe. Caso contrário, peça ao administrador da equipe para adicioná-lo. Consulte [Integrar seu aplicativo](../applications/onboard-your-application.md).

Antes da integração, prepare o seguinte:

| Requisito | Detalhes |
|---|---|
| **ID do aplicativo** | Um identificador de cliente exclusivo usado ao chamar as APIs de Implantações de experiência. Use a ID de cliente existente do aplicativo, quando disponível. |
| **Clientes do lado do servidor** | Se estiver integrando com um SDK do lado do servidor, você precisará de uma ID de cliente administrador com permissões apropriadas. |
| **Clientes de desktop** | Um código de produto e uma versão de produto podem ser usados no lugar de uma ID de cliente. |

## Etapa 3: Obter suas credenciais {#step-3-credentials}

Se estiver integrando via SDK do lado do servidor, você precisará de uma ID de cliente do token de serviço. Entre em contato com o suporte de Implantações de experiência para que suas IDs de clientes sejam incluídas na lista de permissões antes que você possa fazer chamadas de API do SDK.

## Etapa 4: integrar usando uma SDK {#step-4-integrate}

Siga as [etapas de integração](integration-steps.md) para o seu tipo de aplicativo. Escolha o caminho que se ajusta à sua pilha:

* **Serviços da Web** → Java SDK ou Node.js SDK
* **Aplicativos da Web e móveis** → Web SDK ou SDK móvel (em breve)
* **Aplicativos da área de trabalho** → SDK (em breve)

## Etapa 5: criar e testar o primeiro sinalizador de recurso {#step-5-feature-flag}

Quando a integração for concluída, crie seu primeiro sinalizador de recurso no console e teste-o:

* [Criar o primeiro sinalizador de recurso](../feature-flags/create-your-first-feature-flag.md)

## Consulte também {#see-also}

* [Integrar implantações de experiência no seu aplicativo](integrating-in-your-app.md)
* [Etapas de integração](integration-steps.md)
* [SDKs](sdks.md)
