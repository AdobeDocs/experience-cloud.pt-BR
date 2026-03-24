---
title: Obtenha os critérios de público desejados
description: Saiba como gerar a estrutura JSON de critérios de público-alvo corretos para usar nas APIs de gerenciamento de Implantações de experiência usando o console e a API de recursos do GET.
source-git-commit: 6ecedbfc6c7de392f214f3f8f2e71aa18e1bacb9
workflow-type: tm+mt
source-wordcount: '224'
ht-degree: 1%

---


# Obtenha os critérios de público desejados {#get-audience-criteria}

O campo de critérios de público-alvo nas APIs de gerenciamento usa um formato JSON estruturado que pode ser complexo de escrever manualmente. A abordagem recomendada é criar o público-alvo desejado usando o console e, em seguida, recuperar sua representação JSON por meio da API.

## Etapas {#steps}

Para obter o JSON para um critério de público-alvo desejado, siga estas etapas:

1. No console Implantações de experiência, crie um sinalizador de recurso temporário com os critérios de público-alvo que você deseja usar em sua chamada de API.
2. Depois de salvar, observe a ID do sinalizador de recurso no URL do navegador. A ID aparece no URL após a ID do cliente. Por exemplo, em `.../feature-flags/1191/22080`, a ID do recurso é `22080`.
3. Chame o ponto de extremidade [Obter Recurso por ID](feature-flags-management-api.md#get-feature-by-id) com essa ID de recurso.
4. Na resposta JSON, localize o campo `audience`. Ele contém a estrutura exata de critérios de público-alvo que você precisa.
5. Copie o valor `audience`, removendo o atributo `id` de cada objeto de regra. Use-a na chamada da API de recurso Criar ou Atualizar.

## Exemplo {#example}

Depois de chamar o GET `/m/api/v1/mgmt/feature/22080`, a resposta inclui:

```json
{
  "audience": [
    {
      "id": 10034665,
      "criteria": {
        "and": [
          {
            "operator": "EQ",
            "attr": "LOCALE",
            "val": "EN",
            "ruleId": 1,
            "category": "default"
          }
        ]
      }
    }
  ]
}
```

Para usar isso em uma chamada de recurso Create, remova o campo `id` do objeto audience:

```json
{
  "audience": [
    {
      "criteria": {
        "and": [
          {
            "operator": "EQ",
            "attr": "LOCALE",
            "val": "EN",
            "ruleId": 1,
            "category": "default"
          }
        ]
      }
    }
  ]
}
```

## Consulte também {#see-also}

* [API de gerenciamento de sinalizadores de recursos](feature-flags-management-api.md)
* [Obter a ID do cliente para um aplicativo](get-client-id.md)
* [API de patch de gerenciamento](management-patch-api.md)
