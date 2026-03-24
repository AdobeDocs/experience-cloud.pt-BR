---
title: Guia de inicialização
description: Siga estas etapas para integrar seu aplicativo às implantações de experiência da Adobe, desde a solicitação de acesso até a criação do primeiro sinalizador de recurso.
source-git-commit: 9bfe0e55e89c1d7fbd77cde63831a6a186820e24
workflow-type: tm+mt
source-wordcount: '309'
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

## Etapa 3: assinar a API de implantações de experiência {#step-3-subscribe}

Assine a API de Implantações de experiência por meio do Adobe Developer Console para que seu aplicativo possa chamar os endpoints do sinalizador de recurso. Consulte [Assinar o aplicativo de API no Adobe Developer Console](subscribe-to-api-application.md).

>[!NOTE]
>
>Se estiver integrando via SDK do lado do servidor, você precisará de uma ID de cliente do token de serviço. Entre em contato com o suporte de Implantações de experiência para que suas IDs de clientes sejam incluídas na lista de permissões.

## Etapa 4: integrar usando uma SDK ou a API {#step-4-integrate}

Siga as [etapas de integração](integration-steps.md) para o seu tipo de aplicativo. Escolha o caminho que se ajusta à sua pilha:

* **Serviços da Web** → Java SDK ou Node.js SDK
* **Aplicativos da Web e móveis** → API de Recurso V3
* **Aplicativos da área de trabalho** → API de Recurso V2

## Etapa 5: criar e testar o primeiro sinalizador de recurso {#step-5-feature-flag}

Quando a integração for concluída, crie seu primeiro sinalizador de recurso no console e teste-o:

* [Criar o primeiro sinalizador de recurso](../feature-flags/create-your-first-feature-flag.md)

## Consulte também {#see-also}

* [Integrar implantações de experiência no seu aplicativo](integrating-in-your-app.md)
* [Etapas de integração](integration-steps.md)
* [SDKs](sdks.md)
