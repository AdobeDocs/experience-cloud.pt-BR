---
title: Obter a ID do cliente para um aplicativo
description: Saiba como encontrar a ID numérica do cliente para um aplicativo no console Implantações de experiência, que é necessária ao chamar as APIs de gerenciamento.
source-git-commit: 6ecedbfc6c7de392f214f3f8f2e71aa18e1bacb9
workflow-type: tm+mt
source-wordcount: '193'
ht-degree: 1%

---


# Obter a ID do cliente para um aplicativo {#get-client-id}

Os sinalizadores de recursos e as APIs de gerenciamento de grupos de recursos exigem um `clientId` numérico para identificar a qual aplicativo o recurso pertence. Isso é diferente da ID do cliente IMS com base em sequência usada para autenticação da API.

Siga estas etapas para encontrar a ID numérica do cliente para uma aplicação.

## Etapas {#steps}

Para localizar a ID numérica do cliente para um aplicativo, siga estas etapas:

1. Faça logon no console Implantações de experiência.
2. Navegue até **Recursos e versões**.
3. Selecione a guia **Sinalizadores de Recursos**.
4. Abra a lista suspensa **Aplicativo** e selecione o aplicativo cuja ID de cliente você precisa.
5. Observe o URL na barra de endereços do navegador. Depois de `feature-flags/`, o número exibido é a ID numérica do cliente para esse aplicativo.

Por exemplo, se a URL termina com `.../feature-flags/1191/...`, a ID do cliente é `1191`.

## Usar a ID do cliente em chamadas de API {#use-in-api}

Passe esse valor como o parâmetro `clientId` nas solicitações de API de gerenciamento. Por exemplo, ao criar um sinalizador de recurso:

```json
{
  "name": "my-feature-flag",
  "clientId": 1191,
  "state": "disabled"
}
```

## Consulte também {#see-also}

* [API de gerenciamento de sinalizadores de recursos](feature-flags-management-api.md)
* [API de gerenciamento de grupos de recursos](feature-group-management-api.md)
* [Obtenha os critérios de público desejados](get-audience-criteria.md)
