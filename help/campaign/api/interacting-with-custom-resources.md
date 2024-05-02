---
title: Interação com recursos personalizados
description: Saiba mais sobre o gerenciamento de recursos personalizados com APIs/
audience: developing
content-type: reference
topic-tags: campaign-standard-apis
role: Data Engineer
level: Experienced
badge: label="DISPONIBILIDADE LIMITADA" type="Informative" url="../campaign-standard-migration-home.md" tooltip="Restrito a usuários migrados do Campaign Standard"
exl-id: 19bfeecb-da60-479c-a929-0cfb72ef59e3
source-git-commit: 3f4400f24b75e8e435610afbe49e9d9444dbf563
workflow-type: tm+mt
source-wordcount: '155'
ht-degree: 0%

---

# Interação com recursos personalizados {#interacting-with-custom-resources}

A variável **/customResources** O endpoint permite expor os recursos personalizados do Campaign em REST. Com base nessa API, uma integração entre entidades personalizadas e endpoints externos está disponível.

O ponto de extremidade /customResources tem exatamente o mesmo comportamento que o ponto de extremidade /profileAndServices.

Os recursos personalizados expostos nessa API são:

* todas as entidades que não estão expostas em /profileAndServicesExt
* todas as entidades que não estão vinculadas ao perfil e, para essas entidades, seus filhos e netos.
* por padrão, todas as entidades que não estão vinculadas a nada, e seus filhos e netos.

>[!NOTE]
>Os recursos personalizados disponíveis em /profileAndServicesExt não são expostos na API /customResources.


Este é um exemplo para recuperar os metadados de um recurso personalizado:

```
GET /customResources/resourceType/<customResourceName>
```

Para criar, atualizar ou excluir um, o GET, POST, PATCH, DELETE são usados.

```
POST /customResources/<customResourceName>
```
