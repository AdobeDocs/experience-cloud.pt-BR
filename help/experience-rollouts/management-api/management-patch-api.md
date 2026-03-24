---
title: API de patch de gerenciamento
description: Use a API do PATCH de implantações de experiência para atualizar campos individuais de um sinalizador de recurso, grupo de recursos ou grupo de recursos entre equipes sem passar o objeto completo.
source-git-commit: 6ecedbfc6c7de392f214f3f8f2e71aa18e1bacb9
workflow-type: tm+mt
source-wordcount: '301'
ht-degree: 3%

---


# API de patch de gerenciamento {#management-patch-api}

A API do PATCH permite atualizar campos específicos de um sinalizador de recurso, grupo de recursos ou grupo de recursos entre equipes sem enviar o objeto completo no corpo da solicitação. Isso é útil para atualizações direcionadas, como alterar uma regra de público-alvo, alternar o estado ou ajustar uma porcentagem de variação.

## Sinalizador de recurso PATCH {#feature-flag-patch}

Atualiza um ou mais campos de um sinalizador de recurso.

| | |
|---|---|
| **Ponto de extremidade** | `PATCH /m/api/v1/mgmt/feature/{featureFlagId}` |
| **Método** | PATCH |

### Cabeçalhos de solicitação {#ff-request-headers}

Todas as solicitações exigem os cabeçalhos descritos nos [requisitos comuns](feature-management-apis-overview.md#common-requirements).

### Parâmetro de caminho {#ff-path-param}

| Parâmetro | Tipo | Descrição | Obrigatório |
|---|---|---|---|
| `featureFlagId` | Número inteiro | A ID numérica do sinalizador de recurso a ser atualizado. | Sim |

### Corpo da solicitação {#ff-request-body}

Passe somente os campos que deseja atualizar. A resposta sempre retorna o objeto completo do sinalizador de recurso atualizado.

**Exemplo — atualizar apenas a descrição:**

```json
{
  "description": "Updated description"
}
```

**Exemplo — remover público existente:**

```json
{
  "audience": null
}
```

**Exemplo — adicione um novo público-alvo quando não houver nenhum:**

```json
{
  "audience": [
    {
      "criteria": {
        "and": [
          { "operator": "EQ", "attr": "sandboxType", "val": "DEVELOPMENT", "ruleId": 1, "category": "contextual" }
        ]
      }
    }
  ]
}
```

**Exemplo — atualizar uma regra de público-alvo existente:**

```json
{
  "audience": [
    {
      "id": 10020035,
      "criteria": {
        "and": [
          { "operator": "EQ", "attr": "sandboxType", "val": "PRODUCTION", "ruleId": 1, "category": "contextual" }
        ]
      }
    }
  ]
}
```

**Exemplo — alterar o estado e a porcentagem de variação:**

```json
{
  "state": "disabled",
  "variations": [
    {
      "id": 10017188,
      "variantName": "Variation 1",
      "variantPercentage": 80.0
    }
  ]
}
```

>[!NOTE]
>
>Ao atualizar uma regra de público-alvo existente, inclua o `id` da regra (disponível na resposta do recurso GET) para atualizá-la no local. Ao atualizar variações, inclua a `id` da variação para evitar a criação de uma duplicata.

### Resposta {#ff-response}

| Status | Descrição |
|---|---|
| `200` | Sucesso. O corpo da resposta é o objeto completo do sinalizador de recurso atualizado. |
| `400` | Conteúdo inválido. |
| `403` | Permissões insuficientes. |
| `417` | Conflito de atualização simultânea. Busque o recurso atual e tente novamente. |

## Grupo de recursos PATCH {#feature-group-patch}

Atualiza um ou mais campos de um grupo de recursos. A estrutura de solicitação e resposta é a mesma do sinalizador de recurso PATCH — somente o endpoint é diferente.

| | |
|---|---|
| **Ponto de extremidade** | `PATCH /m/api/v1/mgmt/group/{featureGroupId}` |
| **Método** | PATCH |

## PATCH do grupo de recursos entre equipes {#ctfg-patch}

Atualiza um ou mais campos de um grupo de recursos entre equipes. Usa o ponto de acesso da versão v2.

| | |
|---|---|
| **Ponto de extremidade** | `PATCH /m/api/v2/mgmt/release/{CTFGId}` |
| **Método** | PATCH |

## Consulte também {#see-also}

* [API de gerenciamento de sinalizadores de recursos](feature-flags-management-api.md)
* [API de gerenciamento de grupos de recursos](feature-group-management-api.md)
* [APIs de gerenciamento de versão](release-management-apis.md)
* [Visão geral das APIs de gerenciamento de recursos](feature-management-apis-overview.md)
