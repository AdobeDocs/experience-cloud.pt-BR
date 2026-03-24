---
title: API V3 de recursos do GET
description: Referência de API para a API de recurso de implantações de experiência V3, usada para recuperar sinalizadores de recursos para aplicativos da Web e móveis.
source-git-commit: 6ecedbfc6c7de392f214f3f8f2e71aa18e1bacb9
workflow-type: tm+mt
source-wordcount: '679'
ht-degree: 9%

---


# API V3 de recursos do GET {#get-feature-api-v3}

A API de recurso V3 é o endpoint principal para recuperar sinalizadores de recursos em aplicativos web e móveis. Retorna os recursos e versões para os quais um usuário está qualificado, com base em sua identidade e nas regras de público-alvo configuradas no console.

**Ponto de extremidade:** `GET {HOST}/fg/api/v3/feature`

Use `https://p13-stage.adobe.io` para Preparo e `https://p13n.adobe.io` para Produção.

## Solicitação {#request}

### Cabeçalhos de solicitação {#request-headers}

| Header | Tipo | Descrição | Obrigatório |
|---|---|---|---|
| `x-api-key` | String | A chave de API do seu aplicativo na Adobe Developer Console. Deve ser provisionado separadamente para Preparo e Produção. | Sim |
| `Authorization` | String | **Não necessário** para cenários não autenticados. Use `Bearer <AccessToken>` para usuários autenticados. Use `Bearer <ServiceToken>` para cenários de cache do SDK do lado do servidor. | Não |
| `x-adobe-uuid` | String | Um visitante único ou ID de dispositivo. Usado para oferecer suporte à implantação percentual para usuários não autenticados e para manter a adesão entre sessões e transições não autenticadas para autenticadas. | Não |

### Parâmetros de consulta {#query-parameters}

| Parâmetro | Tipo | Descrição | Obrigatório |
|---|---|---|---|
| `clientId` | String | A ID do cliente do aplicativo, conforme integrada no console de Implantações de experiência. | Sim |
| `ignore_rf` | Booleano | Se `true`, os sinalizadores de versão serão ignorados e todas as versões do cliente serão retornadas. Padrão: `false`. | Não |
| `rf` | String | Sinalizador de liberação. Usado apenas quando `ignore_rf` é `false`. | Não |
| `meta` | Booleano | Se `true`, os metadados de cada recurso serão incluídos na resposta, retornados como um par de valores chave no qual o valor é codificado na Base64. Padrão: `false`. | Não |
| `userId` | String | Requer um token de serviço. O GUID do usuário para o qual você deseja recuperar sinalizadores de recursos. | Não |
| *Parâmetros de contexto* | N/D | Qualquer parâmetro de consulta não listado acima é tratado como uma variável de contexto e usado para avaliar as regras de público-alvo. Passe vários valores como `?key1=val1&key2=val2`. Exemplo: `?clientLanguage=ja_JP&contractCurrency=JPY`. | Não |

## Resposta {#response}

### Códigos de status de resposta {#response-status}

| Código de status | Descrição |
|---|---|
| `200 OK` | Os dados do sinalizador de recurso são retornados no corpo da resposta. |
| `304 Not Modified` | O ETag passado pelo cliente corresponde ao estado mais recente do servidor. Trate como uma operação inútil. Sem alterações a serem aplicadas. |
| `400 Bad Request` | O `clientId` não está integrado ou a solicitação está malformada. |
| `403 Forbidden` | Chave de API inválida ou o aplicativo não está inscrito na API de implantações de experiência no Adobe Developer Console. |

### Cabeçalhos de resposta {#response-headers}

| Header | Descrição |
|---|---|
| `x-request-id` | Um identificador de solicitação exclusivo para depuração. Inclua isso em qualquer solicitação de suporte. |
| `ETag` | Um token que representa o estado atual do servidor para os recursos deste usuário. Transmita este valor como `If-None-Match` em solicitações subsequentes. Se o estado não foi alterado, a API retorna `304`. |
| `x-adobe-fg-poll-interval` | O TTL (em segundos) para o cache local do cliente. Chame a API novamente somente após esse intervalo ter decorrido. |

### Corpo da resposta {#response-body}

A resposta é um objeto JSON com os seguintes campos de nível superior:

| Campo | Tipo | Descrição |
|---|---|---|
| `api_version` | String | Versão da API. Campo interno — processamento não necessário. |
| `json_version` | String | Versão do esquema JSON. Campo interno — processamento não necessário. |
| `ttl` | Número inteiro | TTL de cache em segundos. Mesmo valor que o cabeçalho de resposta `x-adobe-fg-poll-interval`. Padrão: 300. |
| `caching_enabled` | Booleano | Se `true`, a avaliação de recursos ocorrerá localmente no cliente. Se `false`, a avaliação acontece no lado do servidor em cada solicitação. |
| `client_analytics_params` | Objeto | Configuração do Analytics para o aplicativo. Consulte os [campos de client_analytics_params](#client-analytics-params) abaixo. |
| `releases` | Matriz | Lista de versões e sinalizadores de recursos para os quais o usuário está qualificado. Consulte [campos de lançamentos](#releases-fields) abaixo. |

#### campos client_analytics_params {#client-analytics-params}

| Campo | Descrição |
|---|---|
| `app_id` | A ID numérica do aplicativo. |
| `safe_event_required` | `true` se os eventos de redirecionamento estiverem habilitados para este cliente. |
| `analytics_required` | Sempre `false` em respostas V3. |

#### campos de lançamentos {#releases-fields}

| Campo | Descrição |
|---|---|
| `release_name` | O nome da versão ou do grupo de recursos para o qual o usuário está qualificado. |
| `bit_index` | O índice de bits da versão. Valores negativos indicam um estado de Implantação completa. |
| `features` | Matriz de chaves de sinalizador de recurso para a qual o usuário está qualificado. Uma chave de recurso é retornada somente se o usuário estiver qualificado e o sinalizador estiver em um estado ativado. Este é o campo principal no qual a lógica do aplicativo deve ser criada. |
| `meta` | Metadados opcionais codificados na Base64 associados ao recurso. Decodifique antes de usar. |
| `release_analytics_params` | Matriz de objetos de metadados de análise para cada recurso elegível. Consulte os [campos de release_analytics_params](#release-analytics-params) abaixo. Em cenários de Grupo de Controle, `features` está vazio. |

#### campos release_analytics_params {#release-analytics-params}

| Campo | Tipo | Descrição |
|---|---|---|
| `app_id` | Número inteiro | ID do aplicativo. |
| `release_id` | Número inteiro | ID da versão. |
| `bit_index` | Número inteiro | Liberar índice de bits. Obsoleto. |
| `variant_id` | Número inteiro | `0` se o usuário estiver no Grupo de Controle; caso contrário, será diferente de zero. |
| `feature_id` | Número inteiro | ID do recurso interno. |
| `f_key` | String | Chave do sinalizador de recurso. |

## Exemplo de solicitação e resposta {#sample}

### Exemplo de solicitação {#sample-request}

```http
GET /fg/api/v3/feature?clientId=MyWebApp&meta=true HTTP/1.1
Host: p13n.adobe.io
Authorization: Bearer <ACCESS_TOKEN>
x-api-key: <YOUR_API_KEY>
If-None-Match: <ETAG>
```

### Resposta de amostra — usuário no grupo de teste {#sample-response-test}

```json
{
  "api_version": "0.1",
  "json_version": "0.1",
  "clients": {
    "MyWebApp": {
      "analyticsVersion": "2.0",
      "client_analytics_params": {
        "app_id": 1378,
        "safe_event_required": false,
        "analytics_required": false
      },
      "releases": [
        {
          "bit_index": -160,
          "release_name": "||features||",
          "features": ["ff1", "ff2", "ff3"],
          "release_analytics_params": [
            {
              "app_id": 1378,
              "release_id": -1,
              "bit_index": -160,
              "variant_id": 10040476,
              "feature_id": 26059,
              "f_key": "ff1",
              "analytics_required": true
            }
          ]
        }
      ]
    }
  },
  "ttl": 60
}
```

### Exemplo de resposta — usuário no grupo de controle {#sample-response-control}

Quando um usuário está no Grupo de Controle, a matriz `features` está vazia e `variant_id` é `0`:

```json
{
  "api_version": "0.1",
  "json_version": "0.1",
  "clients": {
    "MyWebApp": {
      "releases": [
        {
          "bit_index": -160,
          "release_name": "||features||",
          "features": [],
          "release_analytics_params": [
            {
              "app_id": 1378,
              "release_id": -1,
              "bit_index": -160,
              "variant_id": 0,
              "feature_id": 26059,
              "f_key": "ff1"
            }
          ]
        }
      ]
    }
  },
  "ttl": 60
}
```

## Consulte também {#see-also}

* [API V2 de recursos do GET](get-feature-api-v2.md)
* [Aplicações web](../guides/integrate/web-applications.md)
* [Aplicativos móveis](../guides/integrate/mobile-applications.md)
* [Etapas de integração](../guides/integrate/integration-steps.md)
