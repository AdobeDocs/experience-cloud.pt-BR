---
title: API de gerenciamento de grupos de recursos
description: Referência de API para a API de gerenciamento de grupo de recursos de Implantações de Experiência, incluindo endpoints para obter, criar, atualizar, excluir e controlar planos de implantação para grupos de recursos.
source-git-commit: 8a92b7a3e8c52da8bb2474f52c831e159420b878
workflow-type: tm+mt
source-wordcount: '614'
ht-degree: 14%

---


# API de gerenciamento de grupos de recursos {#feature-group-management-api}

A API de gerenciamento do grupo de recursos permite criar, ler, atualizar e excluir de forma programática grupos de recursos em implantações de experiência, incluindo planos de implantação automatizados e de testes A/B.

**Caminho base:** `/m/api/v1/mgmt/group`

Todas as solicitações exigem os cabeçalhos descritos nos [requisitos comuns](feature-management-apis-overview.md#common-requirements).

## Obter todos os grupos de recursos {#get-all-groups}

Recupera todos os grupos de recursos da sua organização.

| | |
|---|---|
| **Ponto de extremidade** | `GET /m/api/v1/mgmt/group` |
| **Método** | GET |

### Parâmetros de consulta {#get-all-query-params}

| Parâmetro | Tipo | Descrição | Obrigatório |
|---|---|---|---|
| `myOrg` | Booleano | Defina como `true` para incluir informações da organização. | Sim |
| `includeClientInfo` | Booleano | Defina como `true` para incluir informações de aplicativo para cada grupo. | Sim |

### Resposta {#get-all-response}

| Status | Descrição |
|---|---|
| `200` | Sucesso. O corpo da resposta é uma matriz de objetos do grupo de recursos. |

## Obter grupo de recursos por ID {#get-group-by-id}

Recupera um único grupo de recursos por sua ID numérica.

| | |
|---|---|
| **Ponto de extremidade** | `GET /m/api/v1/mgmt/group/{groupId}` |
| **Método** | GET |
| **Parâmetro de consulta** | `includeAnalyzeInfo=true` (opcional — adiciona dados de análise à resposta) |

### Resposta {#get-by-id-response}

| Status | Descrição |
|---|---|
| `200` | Sucesso. O corpo da resposta é um objeto do grupo de recursos. |
| `400` | ID do grupo de recursos inválida. |

## Criar grupo de recursos {#create-group}

Cria um novo grupo de recursos com um tipo de implantação manual, automatizada ou de teste A/B.

| | |
|---|---|
| **Ponto de extremidade** | `POST /m/api/v1/mgmt/group` |
| **Método** | POST |

### Corpo da solicitação {#create-request-body}

O corpo da solicitação usa o [objeto do grupo de recursos](#feature-group-object). O `rolloutType` dentro de `params` é obrigatório e determina a estrutura da carga.

**Amostra — implantação manual:**

```json
{
  "params": {
    "rolloutType": "manual",
    "label": "my-feature-group",
    "tags": [],
    "canContextOverridePUP": false
  },
  "status": "SAVED",
  "type": "group",
  "name": "my.feature.group",
  "description": "A manual feature group",
  "variations": [{ "variantPercentage": 100, "variantName": "Variant 1", "features": [] }],
  "audience": [{ "criteria": { "and": [{ "operator": "EQ", "attr": "COUNTRY", "val": "US", "ruleId": 1, "category": "default" }] } }],
  "clients": [],
  "org": { "id": 95 }
}
```

**Amostra — implantação automatizada:**

```json
{
  "params": { "rolloutType": "automated", "label": "my-automated-group", "tags": [] },
  "status": "SAVED",
  "type": "group",
  "name": "my.automated.group",
  "variations": [{ "variantPercentage": 100, "variantName": "Variant 1", "features": [] }],
  "phaseRollOutPlan": {
    "phaseRollOutBlocks": [
      { "isPhaseBlock": true, "phaseRule": { "audience": [] }, "waitRule": null, "blockId": 1, "blockName": "", "isBlockActivated": false },
      { "isPhaseBlock": false, "phaseRule": null, "waitRule": { "waitDuration": { "val": "2", "unit": "HOURS" } }, "blockId": 2, "blockName": "", "isBlockActivated": false },
      { "isPhaseBlock": true, "phaseRule": { "audience": [] }, "waitRule": null, "blockId": 3, "blockName": "", "isBlockActivated": false }
    ],
    "rollOutPlanState": "DRAFT"
  },
  "clients": [],
  "org": { "id": 95 }
}
```

### Resposta {#create-response}

| Status | Descrição |
|---|---|
| `200` | Sucesso. O corpo da resposta é o objeto do grupo de recursos criado. |
| `400` | Conteúdo inválido — consulte [mensagens de erro](#error-messages) para obter detalhes. |
| `403` | Permissões insuficientes. |

## Atualizar grupo de recursos {#update-group}

Atualiza um grupo de recursos existente. Passe a mesma estrutura do corpo da solicitação de criação, incluindo o campo `id`.

| | |
|---|---|
| **Ponto de extremidade** | `PUT /m/api/v1/mgmt/group` |
| **Método** | PUT |

### Resposta {#update-response}

| Status | Descrição |
|---|---|
| `200` | Sucesso. O corpo da resposta é o objeto do grupo de recursos atualizado. |
| `400` | Conteúdo inválido. |
| `403` | Permissões insuficientes. |

## Pausar, retomar ou suspender um plano de implantação {#pause-resume-abort}

Controla a execução de um plano de implantação de teste A/B ou automatizado em andamento.

| Ação | Endpoint |
|---|---|
| **Retomar** | `POST /m/api/v1/mgmt/phaserollout/resume` |
| **Pause** | `POST /m/api/v1/mgmt/phaserollout/pause` |
| **Anular** | `POST /m/api/v1/mgmt/phaserollout/abort` |

### Corpo da solicitação {#control-request-body}

```json
{
  "entityId": 10282,
  "fgEntityType": "GROUP"
}
```

### Resposta {#control-response}

Retorna `true` em caso de sucesso.

## Excluir grupo de recursos {#delete-group}

Exclui um grupo de recursos por sua ID numérica.

| | |
|---|---|
| **Ponto de extremidade** | `DELETE /m/api/v1/mgmt/group/{groupId}` |
| **Método** | DELETE |

### Resposta {#delete-response}

| Status | Descrição |
|---|---|
| `204` | Sucesso. Nenhum corpo de resposta. |
| `403` | Permissões insuficientes. |

## Referência de objeto do grupo de recursos {#feature-group-object}

| Campo | Tipo | Descrição | Obrigatório |
|---|---|---|---|
| `id` | Número inteiro | ID do grupo de recursos. Necessário somente para chamadas de atualização. | Condicional |
| `name` | String | Chave do grupo de recursos. Máximo de 50 caracteres. Padrão: `^[a-zA-Z0-9_.-]*$` | Sim (criar) |
| `clients` | Matriz | Aplicativos associados ao grupo. Cada entrada deve incluir `id` e `imsClientId`. | Sim |
| `status` | String | `"SAVED"` ou `"PUBLISHED"` | Sim |
| `type` | String | Sempre `"group"` para grupos de recursos. | Sim |
| `org` | Objeto | Detalhes da organização. Deve incluir `id`. | Sim |
| `params` | Objeto | Parâmetros de grupo. `rolloutType` é obrigatório (`"manual"`, `"automated"` ou `"ab-testing"`). Também suporta `label` e `tags`. | Sim |
| `audience` | Matriz | Regras de público-alvo para tipos de implantação manual. | Não |
| `variations` | Matriz | Lista de variantes. Consulte [objeto FeatureGroupVariation](#featuregroupvariation-object). | Não |
| `phaseRollOutPlan` | Objeto | Plano de implementação da fase. Necessário para tipos de teste A/B e automatizados. Consulte o [objeto PhaseRollOutPlan](#phaserolloutplan-object). | Condicional |
| `description` | String | Descrição de exibição opcional. Máximo de 225 caracteres. | Não |

### Objeto FeatureGroupVariation {#featuregroupvariation-object}

| Campo | Tipo | Descrição | Obrigatório |
|---|---|---|---|
| `id` | Número inteiro | ID da variação. Necessário somente para chamadas de atualização. | Condicional |
| `variantName` | String | Nome da variante. Codificado para `"Variant 1"`. | Sim |
| `variantPercentage` | Decimal | Porcentagem do público-alvo que recebe essa variante. Deve ser maior que 0 e menor ou igual a 100. | Sim |

### Objeto PhaseRollOutPlan {#phaserolloutplan-object}

| Campo | Tipo | Descrição | Obrigatório |
|---|---|---|---|
| `phaseRollOutBlocks` | Matriz | Lista ordenada de blocos de fase e blocos de espera. O último bloco deve ser um bloco de fase. | Sim |
| `rollOutPlanState` | String | `"DRAFT"`, `"RUNNING"`, `"PAUSED"` ou `"ABORTED"` | Sim |

Cada bloco em `phaseRollOutBlocks` é um **bloco de fase** (`isPhaseBlock: true`) contendo um `phaseRule` com critérios de público-alvo ou um **bloco de espera** (`isPhaseBlock: false`) contendo um `waitRule` com um `waitDuration` (relativo) ou `executionDate` (carimbo de data/hora fixo).

## Mensagens de erro {#error-messages}

| Condição | Status | Mensagem de erro |
|---|---|---|
| Nome inválido ou vazio | 400 | `Error: Invalid value for release name.` |
| Critérios de público-alvo vazios | 400 | `Error: Release is not valid` |
| Várias variações para o tipo automatizado | 400 | `Error: Feature variation is not valid. Variation name should be unique across variations` |
| Grupo publicado sem clientes | 400 | `Error: At least one client must be associated with enabled feature group.` |
| O último bloco no plano não é um bloco de fase | 400 | `Error: The last block in the Phase Rollout plan should be phase block` |
| Tempos do bloco de espera fora de ordem | 400 | `Error: Wait block timings are not in order in the phase rollout plan` |
| Tipos de bloco de espera inconsistentes | 400 | `Error: Wait block should be of same type.` |
| Edição de um bloco de fase ativado | 400 | `Error: Activated phase block should not be changed` |
| Tipo de implantação vazio | 400 | `Error: Rollout type cannot be empty while feature group creation` |
| Plano de fase aprovado com tipo manual | 400 | `Error: PhaseRollOutPlan can't be added with manual rollout type while feature group creation` |
| Agendamento aprovado com status PUBLICADO | 400 | `Error: Schedule can't be added in published state while release/group creation` |

## Consulte também {#see-also}

* [Visão geral das APIs de gerenciamento de recursos](feature-management-apis-overview.md)
* [API de gerenciamento de sinalizadores de recursos](feature-flags-management-api.md)
* [API de patch de gerenciamento](management-patch-api.md)
* [Criar uma implantação automatizada](../guides/automated-rollouts/create-automated-rollout.md)
