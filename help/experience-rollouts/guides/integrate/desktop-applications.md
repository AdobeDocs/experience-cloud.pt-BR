---
title: Aplicativos de desktop
description: Saiba como integrar implantações da Adobe Experience em um aplicativo de desktop usando a API de recurso V2.
source-git-commit: b82520eebe0070b5f76e0f7daeb2bb79a4bccca0
workflow-type: tm+mt
source-wordcount: '183'
ht-degree: 1%

---


# Aplicativos de desktop {#desktop-applications}

Os aplicativos de desktop se integram às Implantações de experiência fazendo chamadas diretas à API REST. Use a **API de Recurso V2** para clientes de desktop.

Consulte **API de Recursos do GET V2** na seção API de Recursos deste guia para obter a referência completa da API.

## Requisitos de integração {#requirements}

Os clientes de desktop devem:

* **Respeite o valor TTL** retornado na resposta da API. O TTL define por quanto tempo o cliente deve armazenar em cache os dados do sinalizador de recurso antes de chamar a API novamente. Implemente um caso de teste que valide esse comportamento para garantir que as versões mais antigas do aplicativo entrem na hibernação corretamente quando nenhum sinalizador de recurso estiver sendo disponibilizado.
* **Lidar com cenários de erro HTTP normalmente**. Crie um conjunto de recursos de fallback para que o aplicativo permaneça funcional se a API estiver temporariamente indisponível.
* **Manter um plano de teste de integração detalhado** que cubra os requisitos de tratamento de erros e TTL acima.

## ID do aplicativo {#app-id}

Os clientes de desktop podem usar um **código de produto e uma versão de produto** como o identificador de aplicativo ao chamar a API, em vez de uma ID de cliente padrão.

## Consulte também {#see-also}

* [Etapas de integração](integration-steps.md)
* [Guia de inicialização](startup-guide.md)
