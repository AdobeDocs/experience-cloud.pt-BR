---
title: Guia de integração do SDK Node.js
description: Saiba como integrar o SDK Node.js de Implantações de Experiência ao seu serviço de back-end para recuperar e avaliar sinalizadores de recursos.
source-git-commit: 9bfe0e55e89c1d7fbd77cde63831a6a186820e24
workflow-type: tm+mt
source-wordcount: '254'
ht-degree: 1%

---


# Guia de integração do SDK Node.js {#nodejs-sdk-integration-guide}

A SDK Node.js de implantações de experiência é uma biblioteca do lado do servidor destinada aos serviços Node.js. Ele armazena dados de sinalizador de recursos em cache localmente e avalia sinalizadores sem uma chamada de API síncrona em cada solicitação.

>[!NOTE]
>
>O Node.js SDK foi projetado apenas para uso no lado do servidor. Para aplicações Web do lado do cliente, chame o endpoint REST da API de recurso V3 diretamente.

## Pré-requisitos {#prerequisites}

Antes de integrar o SDK Node.js, verifique se você tem:

* Um aplicativo do lado do servidor Node.js
* Uma **chave de API** e um **token de serviço** obtidos por meio do Adobe Developer Console — consulte [Assinar o aplicativo de API](../../integrate/subscribe-to-api-application.md)
* Suas **IDs de clientes de aplicativos** registradas no console de Implantações de Experiência — consulte [Integrar seu aplicativo](../../applications/onboard-your-application.md)

## Instalar o SDK {#install}

Adicione a SDK ao `package.json` do seu projeto:

```json
"@floodgate/fg-client-sdk": "~1.0.10"
```

Em seguida, exija-o no código:

```javascript
const { floodgateClient } = require('@floodgate/fg-client-sdk');
```

## Inicializar o SDK {#initialize}

Chamar `createInstance()` uma vez na inicialização do aplicativo:

```javascript
floodgateClient.createInstance(
  {
    adobeIoApiKey: "<YOUR_API_KEY>",
    clientIds: ["<CLIENT_ID_1>", "<CLIENT_ID_2>"],
    env: "PRD",    // Use "STG" for Stage
    featureRequestHttpParams: {
      timeout: 60 * 1000  // Optional: request timeout in ms
    },
    ingestAnalyticsHttpParams: {
      timeout: 5 * 1000   // Optional: analytics timeout in ms
    }
  },
  function(cb) {
    // Fetch a fresh service token from IMS and pass it in the callback
    cb(null, SERVICE_TOKEN);
  },
  function() {
    return true;  // Return false to disable analytics
  },
  function(response) {
    // Called when the SDK initializes successfully
    console.log("SDK initialized");
  },
  function(err) {
    // Called if initialization fails
    console.error("SDK init error:", err);
  }
);
```

## Recuperar sinalizadores de recursos {#retrieve-features}

Sinalizadores de recursos são retornados de forma assíncrona em um retorno de chamada. Escolha o método apropriado com base no contexto do usuário.

### Usuário autenticado {#authenticated-user}

```javascript
floodgateClient.getFeatures(
  {
    userAccessToken: "<USER_ACCESS_TOKEN>",
    visitorId: "<VISITOR_ID>",
    clientId1: "<CLIENT_ID>",
    meta: true
  },
  function(err, features) {
    if (err) {
      // Handle error and serve default experience
      return;
    }
    const isEnabled = floodgateClient.isFeatureEnabled(features, "MY_FEATURE_FLAG");
    // Serve experience based on isEnabled
  }
);
```

### Usuário anônimo {#anonymous-user}

Quando nenhum token de acesso do usuário estiver disponível, use um sinalizador de liberação ou omita o token para receber versões de implantação completa:

```javascript
floodgateClient.getFeatures(
  {
    releaseFlag: "<RELEASE_FLAG>",
    visitorId: "<VISITOR_ID>",
    clientId1: "<CLIENT_ID>",
    meta: false
  },
  callback
);
```

### Versões padrão de implantação completa {#default-releases}

Quando nenhum token de acesso ou sinalizador de liberação é fornecido, o SDK retorna recursos no estado **Implantação completa** ou **Linha de base**:

```javascript
floodgateClient.getFeatures(
  {
    clientId1: "<CLIENT_ID>",
    visitorId: "<VISITOR_ID>",
    meta: false
  },
  callback
);
```

## Verificar se um recurso está habilitado {#check-feature}

```javascript
const isEnabled = floodgateClient.isFeatureEnabled(features, "MY_FEATURE_FLAG");

if (isEnabled) {
  // Serve the new experience
} else {
  // Serve the default experience
}
```

## Habilitar log de depuração {#debug-logging}

Para habilitar logs detalhados do SDK, passe uma instância de agente de depuração ao chamar `createInstance()`:

```javascript
const bunyan = require('bunyan');
const logger = bunyan.createLogger({ name: "fg", sourceType: "SDK", level: "debug" });

floodgateClient.createInstance(
  { ..., log: logger },
  ...
);
```

## Consulte também {#see-also}

* [Notas de versão do Node.js SDK](nodejs-sdk-release-notes.md)
* [SDKs](../../integrate/sdks.md)
* [Inscrever-se no aplicativo de API](../../integrate/subscribe-to-api-application.md)
* [Etapas de integração](../../integrate/integration-steps.md)
