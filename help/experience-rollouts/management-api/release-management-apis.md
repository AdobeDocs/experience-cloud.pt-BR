---
title: APIs de gerenciamento de versão
description: Referência de API para as APIs de gerenciamento de versões de Implantações de experiência, incluindo endpoints para obter, criar e editar versões e grupos de recursos entre equipes.
exl-id: e8d1d025-0645-4cf2-921f-d94c9f71282d
source-git-commit: 454b5c719a5f8be82d1ed835da58bfca6316def2
workflow-type: tm+mt
source-wordcount: '490'
ht-degree: 13%

---

# APIs de gerenciamento de versão {#release-management-apis}

As APIs de gerenciamento de versão permitem recuperar, criar e editar versões e grupos de recursos entre equipes (CTFG) de forma programática. Essas APIs usam o endpoint de gerenciamento v2.

**Caminho base:** `/m/api/v2/mgmt/release`

Todas as solicitações exigem os cabeçalhos descritos nos [requisitos comuns](feature-management-apis-overview.md#common-requirements), além do cabeçalho adicional listado abaixo.

## Cabeçalho adicional necessário {#additional-header}

| Header | Descrição | Obrigatório |
|---|---|---|
| `x-user-context-org` | A ID numérica da equipe da sua organização. Você pode encontrar esse valor no console Implantações de experiência, em Configurações da equipe. | Sim |

## Obter liberação por ID {#get-release}

Recupera uma única versão ou grupo de recursos entre equipes por sua ID numérica.

| | |
|---|---|
| **Ponto de extremidade** | `GET /m/api/v2/mgmt/release/{id}` |
| **Método** | GET |

### Parâmetros de consulta {#get-query-params}

| Parâmetro | Tipo | Descrição | Padrão |
|---|---|---|---|
| `includePermissions` | Booleano | Inclua permissões para atualizar ou excluir esta versão. | `true` |
| `includeOrg` | Booleano | Incluir informações da organização nesta versão. | `true` |
| `includeAnalyzeInfo` | Booleano | Incluir informações de análise. | `false` |

### Resposta {#get-response}

| Status | Descrição |
|---|---|
| `200` | Sucesso. O corpo da resposta é um objeto de liberação — consulte [Referência do objeto de liberação](#release-object). |
| `400` | ID de versão inválida ou solicitação malformada. |

## Criar versão {#create-release}

Cria uma nova versão ou grupo de recursos entre equipes.

| | |
|---|---|
| **Ponto de extremidade** | `POST /m/api/v2/mgmt/release` |
| **Método** | POST |

### Corpo da solicitação {#create-request-body}

O corpo da solicitação usa o [objeto Release](#release-object). Para criação, `status` deve ser definido como `"SAVED"` para grupos de recursos entre equipes (tipo `CROSS_TEAM_FEATURE_GROUP`) ou `"DRAFT"` para versões padrão (tipo `RELEASE`).

**Amostra — criar grupo de recursos entre equipes:**

```json
{
  "params": {
    "rolloutType": "manual",
    "cohortingType": "guid",
    "tags": [],
    "canContextOverridePUP": false,
    "label": "my-cross-team-group"
  },
  "status": "SAVED",
  "type": "CROSS_TEAM_FEATURE_GROUP",
  "name": "my-cross-team-group",
  "description": null,
  "meta": "",
  "variations": [{ "variantPercentage": 100, "variantName": "Variant 1", "features": [] }],
  "audience": [{}],
  "clients": [],
  "pollInterval": 300,
  "org": { "id": "95" },
  "comment": ""
}
```

### Resposta {#create-response}

| Status | Descrição |
|---|---|
| `200` | Sucesso. O corpo da resposta é o objeto de liberação criado. |
| `400` | Conteúdo inválido. |

## Editar versão {#edit-release}

Atualiza uma versão existente ou um grupo de recursos entre equipes. Passe o objeto de liberação completo, incluindo o campo `id`.

| | |
|---|---|
| **Ponto de extremidade** | `PUT /m/api/v2/mgmt/release/{id}` |
| **Método** | PUT |

### Resposta {#edit-response}

| Status | Descrição |
|---|---|
| `200` | Sucesso. O corpo da resposta é o objeto de lançamento atualizado. |
| `417` | Conflito de atualização simultânea. A versão foi modificada entre suas chamadas do GET e do PUT. Busque a versão atual e tente novamente. |

## Referência do objeto de liberação {#release-object}

| Campo | Tipo | Descrição | Obrigatório |
|---|---|---|---|
| `id` | Número inteiro | ID da versão. Necessário somente para chamadas de atualização. | Condicional |
| `name` | String | Nome da versão. Máximo de 50 caracteres. Padrão: `^[a-zA-Z0-9_ ,.:()-]*$`. Deve ser única. | Sim |
| `description` | String | Descrição opcional. Máximo de 255 caracteres. | Não |
| `type` | String | `"RELEASE"` para versões padrão; `"CROSS_TEAM_FEATURE_GROUP"` para grupos de recursos entre equipes. | Sim |
| `status` | String | Estado da versão. Para IMS: `"DRAFT"` na criação; `"DRAFT"`, `"SAVED"`, `"PUBLISHED"` na atualização. Para CTFG: `"SAVED"` na criação; `"SAVED"`, `"PUBLISHED"` na atualização. | Sim |
| `clients` | Matriz | Aplicativos associados a esta versão. Cada entrada requer `id` (numérico) e `imsClientId` (sequência de caracteres). | Não |
| `audience` | Matriz | Lista de regras de público. Consulte [Objeto de condição](feature-flags-management-api.md#condition-object). | Não |
| `variations` | Matriz | Lista de variações. Somente uma variação é suportada durante o envio. | Obrigatório para envio |
| `params` | Objeto | Liberar parâmetros. Consulte [Campos de parâmetros com suporte](#supported-params). | Obrigatório para envio |
| `org` | Objeto | Objeto da organização. Deve incluir `id`. | Não |

### Campos de parâmetros compatíveis {#supported-params}

| Campo | Tipo | Descrição | Obrigatório |
|---|---|---|---|
| `label` | String | Nome de exibição. Máximo de 50 caracteres. | Sim |
| `tags` | Matriz\&lt;Cadeia de caracteres\> | Tags opcionais. Máximo de 50 caracteres cada. | Não |
| `canContextOverridePUP` | Booleano | Se `true`, as regras de contexto substituem as regras de perfil. Padrão: `false`. | Sim |
| `isBetaRelease` | Booleano | Se `true`, marca esta como uma versão beta. Padrão: `false`. | Não |

### Objeto de variação {#variation-object}

| Campo | Tipo | Descrição | Obrigatório |
|---|---|---|---|
| `id` | Número inteiro | ID da variação. Necessário somente para chamadas de atualização. | Condicional |
| `variantName` | String | Nome da variante. Máximo de 50 caracteres. | Sim |
| `variantPercentage` | Duplo | Porcentagem do público-alvo que recebe essa variante. Intervalo: [0, 100]. | Sim |
| `features` | Matriz | Recursos incluídos nesta variação. Cada entrada deve incluir `id`, `name`, `clientId` e `state`. | Não |

## Consulte também {#see-also}

* [Visão geral das APIs de gerenciamento de recursos](feature-management-apis-overview.md)
* [API de gerenciamento de sinalizadores de recursos](feature-flags-management-api.md)
* [API de gerenciamento de grupos de recursos](feature-group-management-api.md)
