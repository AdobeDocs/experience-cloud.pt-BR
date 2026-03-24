---
title: Assinar o aplicativo de API no Adobe Developer Console
description: Saiba como assinar seu aplicativo para a API de implantações de experiência por meio do Adobe Developer Console para poder chamar os endpoints do sinalizador de recurso.
source-git-commit: 120a2ea34682c878aaf6f6cb75504a8704d10e3d
workflow-type: tm+mt
source-wordcount: '278'
ht-degree: 3%

---


# Assinar o aplicativo de API no Adobe Developer Console {#subscribe-to-api}

Para chamar a API de Implantações de Experiência do seu aplicativo, você precisa se inscrever nela por meio da [Adobe Developer Console](https://developer.adobe.com/console). Isso fornece ao aplicativo uma ID do cliente que as Implantações de experiência usam para identificar o chamador.

## Pré-requisitos {#prerequisites}

Antes de se inscrever, confirme o seguinte:

* Seu aplicativo está integrado no console de Implantações de Experiência — consulte [Integrar seu aplicativo](../applications/onboard-your-application.md)
* Você tem acesso à Adobe Developer Console para sua organização

## Assinar a API de implantações de experiência {#subscribe}

Para assinar seu aplicativo para a API de implantações de experiência, siga estas etapas:

1. Vá para [Adobe Developer Console](https://developer.adobe.com/console) e entre com as credenciais da organização.
2. Selecione seu projeto ou crie um novo.
3. Selecione **Adicionar API**.
4. Procure e selecione **API de Implantações de Experiência**.
5. Siga as instruções para configurar a API e gerar credenciais.
6. Anote a **ID do cliente** gerada para o seu projeto. Esse é o identificador que você usa ao chamar a API de implantações de experiência e ao integrar seu aplicativo no console de implantações de experiência.

## Integrações do SDK no lado do servidor {#server-sdk}

Se estiver integrando usando o Java SDK ou Node.js SDK, você precisará de uma ID de cliente do **token de serviço** além de uma chave de API. O token de serviço permite que o SDK chame as APIs de implantações de experiência em segundo plano.

>[!NOTE]
>
>As IDs de cliente do lado do servidor devem ser pelo suporte a Implantações de experiência antes de poderem fazer chamadas de API. Entre em contato com o suporte depois de concluir a configuração do Developer Console.

## Consulte também {#see-also}

* [Guia de inicialização](startup-guide.md)
* [SDKs](sdks.md)
* [Integrar seu aplicativo](../applications/onboard-your-application.md)
* [Etapas de integração](integration-steps.md)
