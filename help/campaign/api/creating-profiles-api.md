---
title: Criação de perfis com APIs
description: Saiba como criar perfis com APIs.
audience: developing
content-type: reference
topic-tags: campaign-standard-apis
role: Data Engineer
level: Experienced
badge: label="DISPONIBILIDADE LIMITADA" type="Informative" url="../campaign-standard-migration-home.md" tooltip="Restrito a usuários migrados do Campaign Standard"
source-git-commit: 84b72258789ba61016deb813e93bdca0ea142712
workflow-type: tm+mt
source-wordcount: '110'
ht-degree: 0%

---

# Criação de perfis com APIs {#creating-profiles-api}

A criação de perfis é executada com um **POST** no recurso de perfil.

>[!CAUTION]
>
>Se quiser associar um <b>orgUnit</b> para o perfil criado, é necessário estender o recurso de perfil com esse campo e, após a publicação da extensão, executar uma solicitação de POST no <b>ProfileAndServicesExt</b> terminal.
>
>Para obter mais informações sobre a extensão de recursos do perfil, consulte <a href="https://helpx.adobe.com/campaign/standard/administration/using/organizational-units.html#partitioning-profiles">Documentação da campanha</a>.

<br/>

***Exemplo de solicitação***

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
