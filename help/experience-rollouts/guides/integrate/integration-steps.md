---
title: Etapas de integração
description: Siga as etapas de integração do seu tipo de aplicativo para conectar as implantações de experiência do Adobe ao seu serviço da Web, aplicativo da Web ou móvel ou aplicativo de desktop.
source-git-commit: b82520eebe0070b5f76e0f7daeb2bb79a4bccca0
workflow-type: tm+mt
source-wordcount: '220'
ht-degree: 3%

---


# Etapas de integração {#integration-steps}

Escolha o caminho de integração que corresponde ao seu tipo de aplicativo.

## Serviços da web {#web-services}

Os serviços de back-end se integram usando uma SDK do lado do servidor. Escolha o SDK para sua pilha de tecnologia.

**Java**

Siga o [guia de integração do Java SDK](../sdk-releases/java/java-sdk-integration-guide.md) para instalação, configuração de dependência e inicialização.

**Node.js**

Siga o [guia de integração do Node.js com o SDK](../sdk-releases/nodejs/nodejs-sdk-integration-guide.md) para instalação e inicialização.

**Outros idiomas**

Se sua pilha não estiver listada acima, integre-a diretamente à **API de Recurso V3** (consulte a seção API de Recurso deste guia). Entre em contato com o suporte de Implantações da experiência se precisar de orientação.

## Aplicativos da Web e móveis {#web-mobile}

Os aplicativos Web e móveis chamam a **API de Recurso V3** para recuperar sinalizadores de recursos para o usuário atual e aplicar a lógica condicional no aplicativo.

Consulte **API de Recurso do GET V3** na seção API de Recurso deste guia para obter a referência completa da API.

## Aplicativos de desktop {#desktop}

Os aplicativos de área de trabalho chamam a **API de Recurso V2** para recuperar sinalizadores de recursos.

Consulte **API de Recursos do GET V2** na seção API de Recursos deste guia para obter a referência completa da API.

>[!IMPORTANT]
>
>Os clientes de desktop devem respeitar o valor TTL na resposta da API e implementar uma manipulação de erros adequada para a indisponibilidade da API. Consulte [Aplicativos da área de trabalho](desktop-applications.md) para obter os requisitos.

## Consulte também {#see-also}

* [Guia de inicialização](startup-guide.md)
* [SDKs](sdks.md)
* [Serviços da web](web-services.md)
* [Aplicativos de desktop](desktop-applications.md)
