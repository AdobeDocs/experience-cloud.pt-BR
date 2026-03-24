---
title: API V2 de recursos do GET
description: Referência de API para a API de recurso de implantações de experiência V2, usada para recuperar sinalizadores de recursos para aplicativos de desktop.
source-git-commit: 6ecedbfc6c7de392f214f3f8f2e71aa18e1bacb9
workflow-type: tm+mt
source-wordcount: '525'
ht-degree: 11%

---


# API V2 de recursos do GET {#get-feature-api-v2}

A API de recurso V2 foi projetada para integração de aplicativos de desktop. Ele recupera sinalizadores de recursos e dados de lançamento para o usuário autenticado, oferecendo suporte ao código do produto e à versão do produto como o identificador do aplicativo, além de uma ID de cliente padrão.

**Ponto de extremidade:** `GET {HOST}/fg/api/v2/feature`

Use `https://p13-stage.adobe.io` para Preparo e `https://p13n.adobe.io` para Produção.

## Solicitação {#request}

### Cabeçalhos de solicitação {#request-headers}

| Header | Tipo | Descrição | Obrigatório |
|---|---|---|---|
| `x-api-key` | String | A chave de API do seu aplicativo na Adobe Developer Console. Deve ser provisionado separadamente para Preparo e Produção. | Sim |
| `Authorization` | String | `Bearer <AccessToken>` ou `Bearer <ServiceToken>`. | Sim |
| `x-adobe-uuid` | String | Um visitante único ou ID de dispositivo. Usado para implantação percentual em cenários não autenticados e para manter a adesão à sessão. | Não |

### Parâmetros de consulta {#query-parameters}

| Parâmetro | Tipo | Descrição | Obrigatório |
|---|---|---|---|
| `clientId` | String | A ID do cliente do aplicativo, conforme integrada no console de Implantações de experiência. Valores múltiplos podem ser passados: `clientId=C1&clientId=C2`. | Não |
| `p` | String | Produto, versão, plataforma, sequência de caracteres de localidade (formato PVPL). Exemplo: `PHSP:17.0:WIN:en_US`. Valores múltiplos podem ser passados: `p=PHSP:17.0:WIN:en_US&p=PPRO:8:WIN:en_US`. Somente o código e a versão do produto são usados na avaliação. | Não |
| `meta` | Booleano | Se `true`, metadados codificados em Base64 são retornados para cada recurso. Padrão: `false`. | Não |
| *Parâmetros de contexto* | N/D | Qualquer par de valor principal adicional é tratado como uma variável de contexto para a avaliação da regra de público-alvo. Exemplo: `clientLanguage=ja_JP&contractCurrency=JPY`. | Não |

>[!NOTE]
>
>Pelo menos um de `clientId` ou `p` é necessário para identificar o aplicativo.

## Resposta {#response}

### Códigos de status de resposta {#response-status}

| Código de status | Descrição |
|---|---|
| `200 OK` | Os dados do sinalizador de recurso são retornados no corpo da resposta. |
| `304 Not Modified` | O ETag corresponde ao estado atual do servidor. Trate como uma operação inútil — sem alterações a serem aplicadas. |
| `401 Unauthorized` | Token de autorização inválido. |

### Cabeçalhos de resposta {#response-headers}

| Header | Descrição |
|---|---|
| `x-request-id` | Um identificador de solicitação exclusivo para depuração. Inclua isso em qualquer solicitação de suporte. |
| `ETag` | Token que representa o estado do recurso atual do usuário. Passar como `If-None-Match` em solicitações subsequentes. Retorna `304` se inalterado. |
| `x-adobe-fg-poll-interval` | TTL em segundos para o cache local do cliente. Chame a API novamente somente após esse intervalo expirar. |

### Corpo da resposta {#response-body}

A resposta é um objeto JSON com os seguintes campos de nível superior:

| Campo | Tipo | Descrição |
|---|---|---|
| `api_version` | String | Versão da API. Campo interno — processamento não necessário. |
| `json_version` | String | Versão do esquema JSON. Campo interno — processamento não necessário. |
| `ttl` | Número inteiro | TTL de cache em segundos. Padrão: 300. |
| `clients` | Objeto | Mapa de IDs de clientes (ou strings PVPL) para os dados de lançamento. Cada chave contém os campos descritos abaixo. |

#### Campos de resposta por cliente {#per-client-fields}

| Campo | Descrição |
|---|---|
| `releases` | Matriz de versões para as quais o usuário está qualificado. Consulte [campos de lançamentos](#releases-fields) abaixo. |
| `client_analytics_params` | Objeto de configuração do Analytics. Consulte os [campos de client_analytics_params](#analytics-fields) abaixo. |

#### campos de lançamentos {#releases-fields}

| Campo | Descrição |
|---|---|
| `release_name` | Nome da versão ou do grupo de recursos. |
| `bit_index` | Liberar índice de bits. Obsoleto. Pode ser `null` ou negativo, dependendo do estado da versão. |
| `features` | Matriz de chaves de sinalizador de recurso para a qual o usuário está qualificado. Uma chave de recurso será exibida somente se o usuário estiver qualificado e o sinalizador estiver habilitado. |
| `meta` | Metadados codificados em Base64 opcionais. Decodifique antes de usar. |
| `release_analytics_params` | Metadados do Analytics para recursos qualificados. Em cenários de Grupo de Controle, `features` está vazio. |

#### campos release_analytics_params {#release-analytics-params}

| Campo | Tipo | Descrição |
|---|---|---|
| `app_id` | Número inteiro | ID do aplicativo. |
| `release_id` | Número inteiro | ID da versão. |
| `bit_index` | Número inteiro | Obsoleto. |
| `variant_id` | Número inteiro | `0` se for Grupo de Controle; caso contrário, será diferente de zero. |
| `feature_id` | Número inteiro | ID do recurso interno. |
| `f_key` | String | Chave do sinalizador de recurso. |

#### campos client_analytics_params {#analytics-fields}

| Campo | Tipo | Descrição |
|---|---|---|
| `app_id` | Número inteiro | ID do aplicativo. |
| `safe_event_required` | Booleano | `true` se os eventos de redirecionamento estiverem habilitados. |
| `analytics_required` | Booleano | `false` se a análise estiver desabilitada ou no fluxo padrão; `true` se o fluxo Kinesis estiver habilitado. |

## Exemplo de solicitação e resposta {#sample}

### Exemplo de solicitação {#sample-request}

```http
GET /fg/api/v2/feature?clientId=MyDesktopApp&p=PHSP:17.0:WIN:en_US&meta=true HTTP/1.1
Host: p13n.adobe.io
Authorization: Bearer <ACCESS_TOKEN>
x-api-key: <YOUR_API_KEY>
If-None-Match: <ETAG>
```

### Exemplo de resposta {#sample-response}

```json
{
  "api_version": "0.1",
  "json_version": "0.1",
  "clients": {
    "PHSP:17.0:WIN:en_US": {
      "analyticsVersion": "1.0",
      "releases": []
    },
    "MyDesktopApp": {
      "analyticsVersion": "1.0",
      "client_analytics_params": {
        "app_id": 388,
        "safe_event_required": false,
        "analytics_required": false
      },
      "releases": [
        {
          "bit_index": 160,
          "release_name": "||features||",
          "features": ["feature_a", "feature_b"],
          "release_analytics_params": [
            {
              "app_id": 388,
              "release_id": -1,
              "bit_index": 160,
              "variant_id": 10031741,
              "feature_id": 2918,
              "f_key": "feature_a"
            }
          ],
          "meta": []
        }
      ]
    }
  },
  "ttl": 300
}
```

## Consulte também {#see-also}

* [API V3 de recursos do GET](get-feature-api-v3.md)
* [Aplicativos de desktop](../guides/integrate/desktop-applications.md)
* [Etapas de integração](../guides/integrate/integration-steps.md)
