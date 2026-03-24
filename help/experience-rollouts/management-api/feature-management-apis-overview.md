---
title: Visão geral das APIs de gerenciamento de recursos
description: Visão geral das APIs de gerenciamento de Implantações de experiência, que permitem criar, ler, atualizar e excluir sinalizadores de recursos, grupos de recursos e versões de forma programática.
source-git-commit: db719ba7b9db91aea818d8ef216a28fcedc6aa65
workflow-type: tm+mt
source-wordcount: '292'
ht-degree: 0%

---


# Visão geral das APIs de gerenciamento de recursos {#feature-management-apis-overview}

As APIs de gerenciamento de Implantações de experiência permitem gerenciar sinalizadores de recursos, grupos de recursos e versões de forma programática. As equipes que precisam automatizar workflows ou integrar Implantações de experiência em pipelines de implantação existentes podem usar essas APIs em vez do console.

>[!NOTE]
>
>O acesso às APIs de gerenciamento usando um token de serviço é concedido mediante solicitação. Entre em contato com o suporte de Implantações da experiência e forneça uma justificativa comercial para solicitar acesso.

## APIs de gerenciamento disponíveis {#available-apis}

As seguintes APIs de gerenciamento estão disponíveis:

* [API de gerenciamento de sinalizadores de recursos](feature-flags-management-api.md) — Criar, ler, atualizar e excluir sinalizadores de recursos de um aplicativo.
* [API de gerenciamento de grupo de recursos](feature-group-management-api.md) — Criar, ler, atualizar e excluir grupos de recursos.
* [APIs de gerenciamento de versão](release-management-apis.md) — Crie e edite grupos de recursos e versões entre equipes.

## Requisitos comuns {#common-requirements}

Todas as chamadas de API de gerenciamento exigem o seguinte:

* Uma **chave de API** da Adobe Developer Console — consulte [Assinar o aplicativo de API](../guides/integrate/subscribe-to-api-application.md).
* Um **token de acesso do usuário IMS** ou **token de serviço**, passado como `Bearer <token>` no cabeçalho `Authorization`.
* Um cabeçalho `Content-Type: application/json`.

As chaves e os tokens de API devem ser provisionados separadamente para ambientes de Preparo e Produção.

## Guias do assistente {#helper-guides}

Os guias a seguir ajudam na criação de cargas de API corretas:

* [Obter ID de cliente para um aplicativo](get-client-id.md) — Procure a ID de cliente numérica exigida pelos sinalizadores de recursos e pelas APIs de gerenciamento de grupos de recursos.
* [Obtenha os critérios de público-alvo desejados](get-audience-criteria.md) — Use o console e a API do GET para gerar a estrutura JSON correta dos critérios de público-alvo.
* [API de patch de gerenciamento](management-patch-api.md) — Atualize campos individuais de um sinalizador de recurso, grupo de recursos ou grupo de recursos entre equipes sem passar o objeto completo.

## Consulte também {#see-also}

* **API de Recursos do GET V3** e **API de Recursos do GET V2** — consulte a seção API de Recursos deste guia para obter as referências completas.
* [Inscrever-se no aplicativo de API](../guides/integrate/subscribe-to-api-application.md)
