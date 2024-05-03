---
title: Recursos personalizados
description: Saiba mais sobre o gerenciamento de recursos personalizados com APIs/
audience: developing
content-type: reference
topic-tags: campaign-standard-apis
role: Data Engineer
level: Experienced
badge: label="DISPONIBILIDADE LIMITADA" type="Informative" url="../campaign-standard-migration-home.md" tooltip="Restrito a usuários migrados do Campaign Standard"
source-git-commit: 84b72258789ba61016deb813e93bdca0ea142712
workflow-type: tm+mt
source-wordcount: '182'
ht-degree: 2%

---

# Recursos personalizados {#custom-resources}

O Adobe Campaign vem com um modelo de dados predefinidos por meio de diferentes recursos. Você pode aprimorar o modelo de dados fornecido estendendo os recursos para adicionar seus próprios campos personalizados ou tabelas personalizadas, como tabelas de produtos ou de compras.

Os recursos personalizados podem ser acessados por meio de APIs usando o **/profileAndServicesExt** e o nome do recurso personalizado.

`https://mc.adobe.io/<ORGANIZATION>/campaign/profileAndServicesExt/<resourceName>/`

>[!NOTE]
>
>Para recursos que não estão prontos para uso, sempre use o <b>&quot;cus&quot;</b> prefixo antes do nome do recurso.

Você pode executar qualquer operação com recursos personalizados, desde que eles estejam vinculados à tabela Perfil. Por exemplo, considere a estrutura das tabelas abaixo:

![texto alternativo](assets/cusresources.png)

Nesse caso, todos os recursos do **Transação**, **Detalhes da transação** e **Produto** As tabelas estão disponíveis desde que estejam vinculadas à variável **Perfil** tabela.

<br/>

***Exemplo de solicitação***

Exemplo de solicitação do GET para acessar o recurso profileAndServicesExt estendido.

```
-X GET https://mc.adobe.io/<ORGANIZATION>/campaign/profileAndServicesExt/\
-H 'Content-Type: application/json' \
-H 'Authorization: Bearer <ACCESS_TOKEN>' \
-H 'Cache-Control: no-cache' \
-H 'X-Api-Key: <API_KEY>' \
```

Retorna a lista de todos os recursos personalizados vinculados. Em seguida, você pode usar os URLs de recursos para executar qualquer tarefa de API descrita nesta documentação.

```
{
"apiName": "resourceType",
"cusProduct": {
        "content": ...,
        "data": "/profileAndServicesExt/cusProduct/",
        "help": "Product",
        "href": "https://mc.adobe.io/<ORGANIZATION>/campaign/profileAndServicesExt/cusProduct/metadata",
        "name": "cusProduct",
        "type": "collection"
    },
"cusTransaction": {
        "content": ...,
        "data": "/profileAndServicesExt/cusTransaction/",
        "help": "Product",
        "href": "https://mc.adobe.io/<ORGANIZATION>/campaign/profileAndServicesExt/cusTransaction/metadata",
        "name": "cusProduct",
        "type": "collection"
    },
    ...
}
```
