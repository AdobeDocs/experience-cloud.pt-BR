---
title: Criação de perfis com APIs
description: Saiba como criar perfis com APIs.
audience: developing
content-type: reference
topic-tags: campaign-standard-apis
role: Data Engineer
level: Experienced
badge: label="DISPONIBILIDADE LIMITADA" type="Informative" url="../campaign-standard-migration-home.md" tooltip="Restrito a usuários migrados do Campaign Standard"
exl-id: 69e8d034-6bdd-4b82-bcd7-1ef4be0a59b3
source-git-commit: 14d8cf78192bcad7b89cc70827f5672bd6e07f4a
workflow-type: tm+mt
source-wordcount: '110'
ht-degree: 0%

---

# Criação de perfis com APIs {#creating-profiles-api}

A criação de perfis é executada com uma solicitação **POST** no recurso de perfil.

>[!CAUTION]
>
>Para associar uma <b>orgUnit</b> ao perfil criado, é necessário estender o recurso de perfil com esse campo e, após a publicação da extensão, executar uma solicitação de POST no ponto de extremidade <b>ProfileAndServicesExt</b>.
>
>Para obter mais informações sobre a extensão de recursos do perfil, consulte a <a href="https://helpx.adobe.com/br/campaign/standard/administration/using/organizational-units.html#partitioning-profiles">documentação do Campaign</a>.

<br/>

***Solicitação de exemplo***

Exemplo de solicitação de POST para criar um perfil com o email &quot;john.doe@mail.com&quot;.

```
-X POST https://mc.adobe.io/<ORGANIZATION>/campaign/profileAndServices/profile \
-H 'Content-Type: application/json' \
-H 'Authorization: Bearer <ACCESS_TOKEN>' \
-H 'Cache-Control: no-cache' \
-H 'X-Api-Key: <API_KEY>' \
-i
-d '{"email":"john.doe@mail.com"}'
```

Ele retorna o perfil recém-criado, com o endereço de email &quot;john.doe@mail.com&quot;.

```
{
    "PKey": "<PKEY>",
    "firstName": "John",
    "lastName":"Doe",
    "birthDate": "1980-10-24",
    "email": "john.doe@mail.com",
    ...
}
```
