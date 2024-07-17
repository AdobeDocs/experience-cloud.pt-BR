---
title: Classificação
description: Saiba como executar operações de classificação
audience: developing
content-type: reference
topic-tags: campaign-standard-apis
role: Data Engineer
level: Experienced
badge: label="DISPONIBILIDADE LIMITADA" type="Informative" url="../campaign-standard-migration-home.md" tooltip="Restrito a usuários migrados do Campaign Standard"
exl-id: 7db25b8d-a6f1-4151-bf37-c47e9991ae48
source-git-commit: 14d8cf78192bcad7b89cc70827f5672bd6e07f4a
workflow-type: tm+mt
source-wordcount: '98'
ht-degree: 10%

---

# Classificação

A classificação está disponível por padrão em ordem crescente. Para classificar em ordem decrescente, anexe **%20desc** ao valor do parâmetro **_order**.

Para saber se um campo pode ser classificado, verifique o parâmetro &quot;classitable&quot; nos metadados do recurso. Para obter mais informações, consulte [esta seção](metadata-mechanism.md).

<br/>

***Solicitações de exemplo***

* Exemplo de solicitação do GET para recuperar emails no banco de dados em ordem alfabética.

  ```
  -X GET https://mc.adobe.io/<ORGANIZATION>/campaign/profileAndServices/profile/email?_order=email \
  -H 'Content-Type: application/json' \
  -H 'Authorization: Bearer <ACCESS_TOKEN>' \
  -H 'Cache-Control: no-cache' \
  -H 'X-Api-Key: <API_KEY>'
  ```

  Resposta à solicitação.

  ```
  {
  "content": [
      "adam@email.com",
      "allison.durance@example.com",
      "amy.dakota@mail.com",
      "andrea.johnson@mail.com",
      ...
  ]
  ...
  }
  ```

* Exemplo de solicitação do GET para recuperar o email no banco de dados em ordem alfabética decrescente.

  ```
  -X GET https://mc.adobe.io/<ORGANIZATION>/campaign/profileAndServices/profile/email?_order=email%20desc \
  -H 'Content-Type: application/json' \
  -H 'Authorization: Bearer <ACCESS_TOKEN>' \
  -H 'Cache-Control: no-cache' \
  -H 'X-Api-Key: <API_KEY>'
  ```

  Resposta à solicitação.

  ```
  {
  "content": [
      "tombinder@example.com",
      "tombinder@example.com",
      "timross@example.com",
      "john.smith@example.com",
      ...
  ]
  }
  ```
