---
title: Exclusão de subscrições
description: Saiba como excluir assinaturas com APIs
role: Data Engineer
level: Experienced
badge: label="DISPONIBILIDADE LIMITADA" type="Informative" url="../campaign-standard-migration-home.md" tooltip="Restrito a usuários migrados do Campaign Standard"
source-git-commit: 84b72258789ba61016deb813e93bdca0ea142712
workflow-type: tm+mt
source-wordcount: '246'
ht-degree: 0%

---

# Exclusão de assinaturas com APIs {#mdeleting-subscriptions-api}

<!--NOTE TO WRITER: There are two duplicate headings that seem to have the same content. Delete one? Rename if different?-->

## Exclusão de uma assinatura de serviço para um perfil específico {#deleting-service-subscription}

Este é um procedimento de três etapas.

1. Recupere o URL de assinaturas para o perfil desejado.
1. Execute uma solicitação GET no URL de assinaturas.
1. Execute uma solicitação DELETE no URL do serviço desejado.

Se a solicitação de exclusão for bem-sucedida, o status da resposta será 204 Sem conteúdo.

<br/>

***Exemplo de solicitação***

As cargas de exemplo abaixo mostram como cancelar a assinatura de um perfil de um serviço. Primeiro, execute uma solicitação GET para recuperar o perfil.

```
-X GET https://mc.adobe.io/<ORGANIZATION>/campaign/profileAndServices/profile/<PKEY> \
-H 'Content-Type: application/json' \
-H 'Authorization: Bearer <ACCESS_TOKEN>' \
-H 'Cache-Control: no-cache' \
-H 'X-Api-Key: <API_KEY>'
```

Ele retorna o URL de assinaturas do perfil.

```
  {
    ...
    "postalAddress":...,
    "preferredLanguage": "none",
    "subscriptions": {
      "href": "https://mc.adobe.io/<ORGANIZATION>/campaign/profileAndServices/profile/<PKEY>/subscriptions/"
    },
  }
```

Execute uma solicitação GET no URL de assinaturas.

```
-X GET https://mc.adobe.io/<ORGANIZATION>/campaign/profileAndServices/profile/<PKEY>/subscriptions \
-H 'Content-Type: application/json' \
-H 'Authorization: Bearer <ACCESS_TOKEN>' \
-H 'Cache-Control: no-cache' \
-H 'X-Api-Key: <API_KEY>'
```

Ele retorna a lista de assinaturas do perfil selecionado, com um URL para cada serviço assinado.

```
...
"service": {
  "PKey": "<PKEY>",
  "href": "https://mc.adobe.io/<ORGANIZATION>/campaign/profileAndServices/service/<PKEY>",
  "label": "Sport Newsletter",
  "name": "SVC1",
  "title": "Sport Newsletter (SVC1)"
},
...
```

Execute uma solicitação DELETE no URL do serviço desejado.

```
-X DELETE https://mc.adobe.io/<ORGANIZATION>/campaign/profileAndServices/service/<PKEY> \
-H 'Content-Type: application/json' \
-H 'Authorization: Bearer <ACCESS_TOKEN>' \
-H 'Cache-Control: no-cache' \
-H 'X-Api-Key: <API_KEY>'
```

<!-- + réponse -->

## Exclusão de uma assinatura de serviço para um perfil específico

Este é um procedimento de três etapas.

1. Recupere o serviço desejado e seu URL de assinatura.
1. Execute uma solicitação GET no URL de assinaturas para recuperar todas as assinaturas de perfis.
1. Execute uma solicitação DELETE no URL de assinatura de perfil desejado.

Se a solicitação de exclusão for bem-sucedida, o status da resposta será 204 Sem conteúdo.

<br/>

***Exemplo de solicitação***

Recuperar o registro de serviço.

```
-X GET https://mc.adobe.io/<ORGANIZATION>/campaign/profileAndServices/service/<PKEY> \
-H 'Content-Type: application/json' \
-H 'Authorization: Bearer <ACCESS_TOKEN>' \
-H 'Cache-Control: no-cache' \
-H 'X-Api-Key: <API_KEY>'
```

Ele retorna o URL de subscrições do serviço.

```
{
  ...
  "messageType": "email",
  "mode": "newsletter",
  "name": "SVC3",
  "subScenarioEventType": "subscriptionEvent",
  "subscriptions": {
    "href": "https://mc.adobe.io/<ORGANIZATION>/campaign/profileAndServices/service/<PKEY>/subscriptions/"
  },
  "targetResource": "profile",
  ...
},
```

Execute uma solicitação GET no URL de assinaturas.

```
-X GET https://mc.adobe.io/<ORGANIZATION>/campaign/profileAndServices/service/<PKEY>/subscriptions \
-H 'Content-Type: application/json' \
-H 'Authorization: Bearer <ACCESS_TOKEN>' \
-H 'Cache-Control: no-cache' \
-H 'X-Api-Key: <API_KEY>'
```

Ele retorna a lista de assinaturas do serviço selecionado, com um URL (href) para cada assinatura de perfil.

```
{
  "PKey": "<PKEY>",
  "created": "2019-03-26 08:58:04.764Z",
  "email": "",
  "expirationDate": "",
  "href": "https://mc.adobe.io/<ORGANIZATION>/campaign/profileAndServices/service/<PKEY>/subscriptions/<PKEY>",
  "metadata": "subscriptionRcp",
  "service": ...,
  "serviceName": "SVC3",
  "subscriber": ...,
  ...
}
```

Execute uma solicitação DELETE no URL de assinatura de perfil desejado.

```
-X DELETE https://mc.adobe.io/<ORGANIZATION>/campaign/profileAndServices/service/<PKEY>/subscriptions/<PKEY> \
-H 'Content-Type: application/json' \
-H 'Authorization: Bearer <ACCESS_TOKEN>' \
-H 'Cache-Control: no-cache' \
-H 'X-Api-Key: <API_KEY>'
```

<!-- + réponse -->
