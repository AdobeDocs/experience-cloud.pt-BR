---
title: SDKs
description: Saiba mais sobre a arquitetura do SDK em implantações da Adobe Experience e os SDKs disponíveis para Java e Node.js.
exl-id: 110a440d-b52a-4e1e-a94f-86f9741a223a
source-git-commit: 2a946868f58e25f8aafbf3ccfcf6571e7d0d8d20
workflow-type: tm+mt
source-wordcount: '312'
ht-degree: 2%

---

# SDKs {#sdks}

As Implantações da Experience fornecem SDKs do lado do servidor para integração de serviços de back-end. Esta página descreve a arquitetura do SDK e as opções disponíveis.

## Arquitetura do SDK {#architecture}

Todos os SDKs de Implantações de experiência compartilham a mesma arquitetura principal:

* **Inicialização** — O SDK é configurado por meio de uma chamada `createInstance()` que retorna um objeto singleton.
* **Recuperação de recurso** — O método `getFeatures()` recupera dados de sinalizador de recurso da SDK.
* **Armazenamento em cache** — As respostas dos caches do SDK do serviço de Implantações de Experiência. Um Gerenciador de Cache atualiza o cache em um intervalo de polling configurável (TTL).
* **Tratamento de erros** — Se o serviço retornar um 503, o Gerenciador de Cache manterá os dados em cache existentes e continuará atendendo às avaliações do sinalizador de recursos. Se os dados não foram alterados desde a última chamada (304), o cache não é atualizado.

## Pré-requisitos {#prerequisites}

Antes de integrar uma SDK, verifique o seguinte:

1. **ID do Aplicativo** — A ID do cliente para cada aplicativo integrado no console de Implantações de Experiência.
2. **Token de serviço** — usado pela SDK para chamar as APIs de Implantações de Experiência em segundo plano.
3. **Chave de API** — Usada com o token de serviço para autenticação de API.

## SDKs disponíveis {#available-sdks}

### SDK do Java {#java-sdk}

O Java SDK é distribuído via Maven. Adicione a dependência ao `pom.xml` do seu projeto para integrar. Para aplicativos baseados em Spring, a dependência Maven configura automaticamente o cache do SDK antes que seu aplicativo seja totalmente carregado.

Principais especificações do Java SDK:

* **JDK com suporte:** JDK 8 e posterior
* **Clientes não armazenáveis em cache:** com suporte do SDK versão 0.8 em diante. Para clientes que não podem ser armazenados em cache, `getFeature()` faz uma chamada de API em tempo real em vez de ler do cache. O SDK continua a pesquisa em segundo plano e alterna para o serviço baseado em cache se o cliente se tornar armazenável em cache.

Consulte o [guia de integração do Java SDK](../sdk-releases/java/java-sdk-integration-guide.md) para obter instruções de configuração.

### SDK Node.js {#nodejs-sdk}

O SDK do Node.js é distribuído via npm.

Consulte o [guia de integração do Node.js com o SDK](../sdk-releases/nodejs/nodejs-sdk-integration-guide.md) para obter instruções de configuração.

## Consulte também {#see-also}

* [Serviços da web](web-services.md)
* [Etapas de integração](integration-steps.md)
* [Guia de integração do Java SDK](../sdk-releases/java/java-sdk-integration-guide.md)
* [Guia de integração do SDK Node.js](../sdk-releases/nodejs/nodejs-sdk-integration-guide.md)
