---
title: Mecanismo de metadados
description: Saiba mais sobre o mecanismo de metadados.
audience: developing
content-type: reference
topic-tags: campaign-standard-apis
role: Data Engineer
level: Experienced
badge: label="DISPONIBILIDADE LIMITADA" type="Informative" url="../campaign-standard-migration-home.md" tooltip="Restrito a usuários migrados do Campaign Standard"
source-git-commit: 84b72258789ba61016deb813e93bdca0ea142712
workflow-type: tm+mt
source-wordcount: '236'
ht-degree: 1%

---

# Mecanismo de metadados {#metadata-mechanism}

É possível recuperar os metadados de recursos usando **resourceType** em uma solicitação GET:

`GET /profileAndServices/resourceType/<resourceName>`

A resposta retorna os principais metadados do recurso (todos os outros campos são descritivos ou internos):

* A variável **Conteúdo** retorna os campos do recurso. Para cada campo no **conteúdo** podemos encontrar os seguintes campos:

   * &quot;apiName&quot;: nome do atributo usado nas APIs.
   * &quot;type&quot;: esta é a definição de tipo de alto nível (sequência, número, link, coleção, enumeração...).
   * &quot;dataPolicy&quot;: o valor do campo deve seguir as regras de política fornecidas. Por exemplo, se a regra dataPolicy estiver definida como &quot;email&quot;, o valor deverá ser um email válido. Durante um PATCH ou POST, o dataPolicy pode verificar o valor ou modificar o valor para transformar (smartCase, por exemplo).
   * &quot;category&quot;: fornece a categoria do campo no editor de consultas.
   * &quot;resType&quot;: é o tipo técnico.

     Se &quot;type&quot; for concluído com o valor &quot;link&quot; ou &quot;collection&quot;, o valor resTarget será o nome do recurso direcionado pelo link.
Se &quot;type&quot; for preenchido com o valor &quot;enumeration&quot;, um campo &quot;values&quot; será adicionado e cada valor de enumeração será detalhado no **valores** nó.

* A variável **Filtros** O nó retorna o URL para recuperar os filtros associados. Para obter mais informações sobre filtros, consulte [nesta seção](filtering.md) seção.

<!-- créer une section au même niveau sur les liens -->
<!-- dans l'exemple: birthdate, email +  mettre 2 liens : un de type 1-1 , 1-N
si on prend l'exemple de l'org unit, on aura un bon exemple lien -->
<!-- plus reparler du node Data -->

<br/>

***Exemplo de solicitação***

Execute uma solicitação GET no recurso.

```
-X GET https://mc.adobe.io/<ORGANIZATION>/campaign/profileAndServices/resourceType/profile \
-H 'Content-Type: application/json' \
-H 'Authorization: Bearer <ACCESS_TOKEN>' \
-H 'Cache-Control: no-cache' \
-H 'X-Api-Key: <API_KEY>'
```

Retorna a descrição completa do recurso de perfil.

```
{
...
"content": {
  "email": {...},
    ...
    },
"data": "/profileAndServices/profile/",
"filters": {
        "href": "https://mc.adobe.io/<ORGANIZATION>/campaign/profileAndServices/resourceType/<PKEY>"
    },
"help": "Identified profiles",
"href": "https://mc.adobe.io/<ORGANIZATION>/campaign/profileAndServices/profile/metadata",
"label": "Profiles",
"mandatory": false,
"name": "profile",
"pkgStatus": "never",
"readOnly": false,
"schema": "nms:recipient",
"type": "item"
}
```
