---
title: API de gerenciamento de sinalizadores de recursos
description: Referência de API para a API de gerenciamento de sinalizadores de recursos de Implantações de Experiência, incluindo endpoints para obter, criar, atualizar e excluir sinalizadores de recursos de um aplicativo.
source-git-commit: 8a92b7a3e8c52da8bb2474f52c831e159420b878
workflow-type: tm+mt
source-wordcount: '650'
ht-degree: 12%

---


# API de gerenciamento de sinalizadores de recursos {#feature-flags-management-api}

A API de gerenciamento de sinalizadores de recursos permite criar, ler, atualizar e excluir de forma programática sinalizadores de recursos para seus aplicativos em implantações de experiência.

**Caminho base:** `/m/api/v1/mgmt/feature`

Todas as solicitações exigem os cabeçalhos descritos nos [requisitos comuns](feature-management-apis-overview.md#common-requirements).

## Obter todos os sinalizadores de recursos {#get-all-features}

Recupera todos os sinalizadores de recursos de um aplicativo especificado.

| | |
|---|---|
| **Ponto de extremidade** | `GET /m/api/v1/mgmt/feature` |
| **Método** | GET |

### Parâmetros de consulta {#get-all-query-params}

| Parâmetro | Tipo | Descrição | Obrigatório |
|---|---|---|---|
| `clientId` | Número inteiro | ID numérica do aplicativo. Consulte [Obter ID do cliente](get-client-id.md). Necessário se `imsClientId` não for fornecido. | Condicional |
| `imsClientId` | String | ID do cliente em formato de cadeia de caracteres do aplicativo. Necessário se `clientId` não for fornecido. | Condicional |
| `nonReleaseFeature` | Booleano | Defina como `true` para incluir sinalizadores de recursos independentes não associados a nenhum grupo ou versão. Obrigatório para fluxos de trabalho baseados em API. | Sim |

### Resposta {#get-all-response}

| Status | Descrição |
|---|---|
| `200` | Sucesso. O corpo da resposta contém uma lista de objetos sinalizadores de recursos. |

O corpo da resposta contém uma matriz `features`. Cada elemento é um objeto de sinalizador de recurso com os campos descritos na [referência de objeto FeatureDTO](#featuredto-object).

**Exemplo de resposta:**

```json
{
  "features": [
    {
      "id": 22079,
      "name": "new.FF.1",
      "clientId": 1191,
      "state": "enabled",
      "description": "first feature flag",
      "release": { "id": 2631, "name": "FF.group", "status": "SAVED" },
      "audience": null,
      "params": { "label": "new FF 1", "rolloutType": "manual" }
    },
    {
      "id": 22080,
      "name": "new.FF.2",
      "clientId": 1191,
      "state": "enabled",
      "description": "second feature flag",
      "audience": [
        {
          "id": 10034665,
          "criteria": { "and": [{ "operator": "EQ", "attr": "LOCALE", "val": "EN" }] }
        }
      ]
    }
  ]
}
```

## Obter sinalizador de recurso por ID {#get-feature-by-id}

Recupera um único sinalizador de recurso por sua ID numérica.

| | |
|---|---|
| **Ponto de extremidade** | `GET /m/api/v1/mgmt/feature/{featureId}` |
| **Método** | GET |

### Resposta {#get-by-id-response}

| Status | Descrição |
|---|---|
| `200` | Sucesso. O corpo da resposta é um único [objeto FeatureDTO](#featuredto-object). |
| `400` | ID de recurso inválida. |

## Criar sinalizador de recurso {#create-feature}

Cria um novo sinalizador de recurso.

| | |
|---|---|
| **Ponto de extremidade** | `POST /m/api/v1/mgmt/feature` |
| **Método** | POST |

### Corpo da solicitação {#create-request-body}

O corpo da solicitação é um [objeto FeatureDTO](#featuredto-object). Os seguintes campos são obrigatórios para criação:

| Campo | Obrigatório | Notas |
|---|---|---|
| `name` | Sim | Chave do sinalizador de recurso. Máximo de 50 caracteres. Padrão: `^[a-zA-Z0-9_.-]*$` |
| `clientId` | Sim | ID numérica do aplicativo. Consulte [Obter ID do cliente](get-client-id.md). |
| `state` | Sim | `"enabled"` ou `"disabled"` |

### Resposta {#create-response}

| Status | Descrição |
|---|---|
| `200` | Sucesso. O corpo da resposta contém `{ "generatedFeatureId": <id> }`. |
| `400` | Conteúdo inválido. |
| `403` | Permissões insuficientes para este cliente ou regra de público-alvo. |
| `417` | Os usuários com a função Desenvolvedor não podem salvar um recurso com uma regra pública — é necessária pelo menos uma regra de público-alvo. |

**Solicitação de exemplo:**

```json
{
  "name": "my-new-feature",
  "clientId": 1191,
  "state": "disabled",
  "description": "A new feature flag",
  "meta": "VGVzdA==",
  "audience": [
    {
      "criteria": {
        "and": [{ "operator": "EQ", "attr": "COUNTRY", "category": "default", "ruleId": 1, "val": "US" }]
      }
    }
  ],
  "variations": [{ "variantPercentage": 100, "variantName": "Variation 1" }],
  "params": { "label": "My New Feature", "tags": [] }
}
```

## Atualizar sinalizador de recurso {#update-feature}

Atualiza um sinalizador de recurso existente. Passe o [objeto FeatureDTO](#featuredto-object) completo, incluindo o campo `id`.

| | |
|---|---|
| **Ponto de extremidade** | `PUT /m/api/v1/mgmt/feature` |
| **Método** | PUT |

### Resposta {#update-response}

| Status | Descrição |
|---|---|
| `200` | Sucesso. O corpo da resposta é o objeto FeatureDTO atualizado. |
| `400` | Conteúdo inválido. |
| `403` | Permissões insuficientes. |
| `417` | Conflito de atualização simultânea. Busque o recurso atual primeiro e tente novamente com o valor `version` mais recente de `params`. |

## Excluir sinalizador de recurso {#delete-feature}

Exclui um sinalizador de recurso por sua ID numérica.

| | |
|---|---|
| **Ponto de extremidade** | `DELETE /m/api/v1/mgmt/feature/{featureId}` |
| **Método** | DELETE |

### Resposta {#delete-response}

| Status | Descrição |
|---|---|
| `204` | Sucesso. Nenhum corpo de resposta. |
| `403` | Permissões insuficientes. |

## Referência de objeto FeatureDTO {#featuredto-object}

| Campo | Tipo | Descrição | Obrigatório |
|---|---|---|---|
| `id` | Número inteiro | ID do sinalizador de recurso. Necessário somente para chamadas de atualização. | Condicional |
| `name` | String | Chave do sinalizador de recurso (retornada nas respostas da API). Máximo de 50 caracteres. Padrão: `^[a-zA-Z0-9_.-]*$` | Sim (criar) |
| `clientId` | Número inteiro | ID numérica do aplicativo. | Sim |
| `state` | String | `"enabled"` ou `"disabled"` | Sim |
| `meta` | String | Metadados codificados na Base64 retornados com o recurso nas respostas da API. Máximo de 1024 caracteres. | Não |
| `description` | String | Exibir descrição. Máximo de 225 caracteres. | Não |
| `audience` | Matriz | Lista de regras de público. Consulte [objeto FeatureRule](#featurerule-object). Use [Obter os critérios de público-alvo desejados](get-audience-criteria.md) para gerar isso. | Não |
| `variations` | Matriz | Lista de variantes. Máx 3. Consulte [objeto FeatureVariation](#featurevariation-object). | Não |
| `params` | Objeto | Metadados adicionais. Chaves com suporte: `label` (nome de exibição na interface), `tags` (matriz de cadeia de caracteres). | Não |
| `release` | Objeto | Associação de liberação/grupo. `null` se o sinalizador não estiver em um grupo. Somente leitura. | Não |

### Objeto FeatureVariation {#featurevariation-object}

| Campo | Tipo | Descrição | Obrigatório |
|---|---|---|---|
| `id` | Número inteiro | ID da variação. Necessário somente para chamadas de atualização. | Condicional |
| `variantName` | String | Nome da variante. Valores fixos: `"Variation 1"`, `"Variation 2"`, `"Variation 3"`. | Sim |
| `variantPercentage` | Decimal | Porcentagem do público-alvo que recebe essa variante. Deve ser superior a 0 e não superior a 100, com até 2 casas decimais. | Sim |

### Objeto FeatureRule {#featurerule-object}

| Campo | Tipo | Descrição | Obrigatório |
|---|---|---|---|
| `id` | Número inteiro | ID da regra. Necessário somente para chamadas de atualização. Defina como `null` ao adicionar uma nova regra. | Condicional |
| `criteria` | Objeto | Objeto de condição que define a regra de público. Consulte [Objeto de condição](#condition-object). | Sim |

### Objeto de condição {#condition-object}

| Campo | Tipo | Descrição |
|---|---|---|
| `and` | Matriz\&lt;Condição\> | Todas as condições devem ser verdadeiras. |
| `or` | Matriz\&lt;Condição\> | Pelo menos uma condição deve ser verdadeira. |
| `not` | Condição | Esta condição deve ser falsa. |
| `attr` | String | O atributo de usuário a ser avaliado (por exemplo, `COUNTRY`, `LOCALE`). |
| `operator` | String | Operador de comparação (por exemplo, `EQ`, `IN`, `LT`). |
| `val` | String | O valor a ser comparado. |
| `meta` | Objeto | Metadados de condição opcionais. `desc` define o rótulo de exibição na interface. |

`and`, `or` ou `not`, ou uma combinação de `attr`, `operator` e `val` devem ser fornecidos em cada Condição.

## Consulte também {#see-also}

* [Visão geral das APIs de gerenciamento de recursos](feature-management-apis-overview.md)
* [API de patch de gerenciamento](management-patch-api.md)
* [Obter a ID do cliente para um aplicativo](get-client-id.md)
* [Obtenha os critérios de público desejados](get-audience-criteria.md)
