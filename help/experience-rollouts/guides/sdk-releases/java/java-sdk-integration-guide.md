---
title: Guia de integração do Java SDK
description: Saiba como integrar o Java SDK de implantações de experiência ao seu serviço de back-end para recuperar e avaliar sinalizadores de recursos.
source-git-commit: 9bfe0e55e89c1d7fbd77cde63831a6a186820e24
workflow-type: tm+mt
source-wordcount: '426'
ht-degree: 1%

---


# Guia de integração do Java SDK {#java-sdk-integration-guide}

A Experience Rollups do Java SDK é uma biblioteca do lado do servidor que armazena dados de sinalizadores de recursos em cache localmente e avalia sinalizadores sem uma chamada de API síncrona em cada solicitação. Este guia aborda a SDK atual (4.x).

## Pré-requisitos {#prerequisites}

Antes de integrar o Java SDK, verifique se você tem:

* JDK 11 ou posterior (necessário a partir do SDK versão 3.0.0; versões anteriores são compatíveis com JDK 8+)
* Um sistema de compilação baseado em Maven
* Uma ID de cliente da **Chave de API** e do **token de serviço** do seu projeto do Adobe Developer Console — consulte [Assinar o aplicativo de API](../../integrate/subscribe-to-api-application.md)
* Suas **IDs de clientes de aplicativos** registradas no console de Implantações de Experiência — consulte [Integrar seu aplicativo](../../applications/onboard-your-application.md)

## Adicionar a dependência do Maven {#maven-dependency}

Adicione a experiência Implantações de Java SDK ao `pom.xml` do seu projeto:

```xml
<dependency>
  <groupId>com.adobe.cloudtech</groupId>
  <artifactId>fg-client-sdk</artifactId>
  <version>4.0.6</version>
</dependency>
```

## Inicializar o SDK {#initialize}

O SDK é inicializado uma vez na inicialização do aplicativo usando `FloodgateClient.createInstance()`. O método pega um objeto `FloodgateConfiguration` que você compila com o construtor de configurações.

### Implementar o retorno de chamada do token de serviço {#service-token-callback}

O SDK usa uma interface de retorno de chamada para recuperar um token de serviço novo no tempo de execução:

```java
private class FgConfigCallBack implements FGConfigBaseCallBack {

  @Override
  public String getIMSServiceToken() {
    // Fetch and return a valid service token
  }

  @Override
  public boolean isAnalyticsEnabled() {
    return false; // Set to true to enable analytics
  }
}
```

### Criar o objeto de configuração {#configuration}

Use o construtor de configurações para configurar o SDK:

```java
FloodgateConfiguration configuration = FloodgateConfiguration.FloodgateConfigurationBuilder
    .aFloodgateConfiguration(
        FgEnv.PRD,                   // Use FgEnv.STG for Stage
        "<YOUR_API_KEY>",
        Set.of("<CLIENT_ID_1>", "<CLIENT_ID_2>"),
        new FgConfigCallBack(),
        CallType.ASYNC
    )
    .withRetryPolicy(retryPolicy)    // Optional: defaults to 5 retries, 10s interval
    .build();
```

Use `FgEnv.STG` para o ambiente de Preparo e `FgEnv.PRD` para Produção.

### Criar a instância do cliente {#client-instance}

```java
FloodgateClient fgClient = FloodgateClient.createInstance(configuration);
```

## Recuperar sinalizadores de recursos {#retrieve-features}

### Usuário autenticado {#authenticated-user}

Usar um token de acesso IMS para recuperar sinalizadores de recursos para o usuário atual:

```java
GetFeatureRequest request = GetFeatureRequestBuilder
    .aGetFeatureRequest("<CLIENT_ID>")
    .withAccessToken("<USER_ACCESS_TOKEN>")
    .withContext(context)
    .build();

FeaturesResponse[] features = fgClient.getFeatures(request);
```

### Usuário anônimo {#anonymous-user}

Para usuários não autenticados, transmita uma ID de visitante e o token de serviço:

```java
GetFeatureRequest request = GetFeatureRequestBuilder
    .aGetFeatureRequest("<CLIENT_ID>")
    .withServiceToken("<SERVICE_TOKEN>")
    .withVisitorId("<VISITOR_ID>")
    .withContext(context)
    .build();

FeaturesResponse[] features = fgClient.getFeatures(request);
```

### Recuperar um sinalizador ou versão de recurso específico {#specific-feature}

Para recuperar um único sinalizador de recurso por chave:

```java
GetFeatureRequest request = GetFeatureRequestBuilder
    .aGetFeatureRequest("<CLIENT_ID>")
    .withAccessToken("<ACCESS_TOKEN>")
    .withFeatureKey("<FEATURE_KEY>")
    .build();
```

Para recuperar por chave de versão, substitua `.withFeatureKey()` por `.withReleaseKey()`.

## Verificar se um recurso está habilitado {#check-feature}

```java
boolean isEnabled = FloodgateClient.isFeatureEnabled(features, "MY_FEATURE_FLAG");

if (isEnabled) {
  // Serve the new experience
} else {
  // Serve the default experience
}
```

Para verificações baseadas em versão:

```java
boolean isEnabled = FloodgateClient.isFeatureEnabled(features, "MY_RELEASE", "MY_FEATURE_FLAG");
```

## Gerenciamento de cache {#cache-management}

O SDK armazena em cache dados de sinalizador de recurso e os atualiza em um intervalo de pesquisa definido por aplicativo no console. Para acionar uma atualização de cache sob demanda:

```java
fgClient.refreshClientCache("<CLIENT_ID>");
```

### Clientes não armazenáveis em cache {#non-cacheable}

Para clientes que não podem ser armazenados em cache, `getFeature()` faz uma chamada de API sempre. O SDK continua com a pesquisa em segundo plano e alterna para o serviço baseado em cache quando o cliente se torna armazenável em cache. Compatível a partir da versão 0.8 do SDK.

## Opções de configuração {#configuration-options}

Os seguintes métodos de configuração opcionais estão disponíveis no construtor:

| Opção | Método | Descrição |
|---|---|---|
| Sempre usar cache | `.alwaysCache()` | Ignora a resposta de cache da API; use para sinalizadores sem regras de público |
| Desativar armazenamento em cache | `.neverCache()` | Desativa o cache padrão; útil para a lógica personalizada de atualização do cache |
| Cliente HTTP personalizado | `.withHttpClient(client)` | Usar seu próprio cliente HTTP |
| Executor personalizado | `.withScheduledExecutorService(executor)` | Usar seu próprio executor agendado para pesquisa em segundo plano |
| Incluir grupo de controle | `.includeControlGroup()` | Retorna dados do grupo de controle na resposta do recurso |

## Manipular erros {#error-handling}

Quebrar `getFeatures()` chamadas para capturar exceções do SDK:

```java
try {
  features = fgClient.getFeatures(request);
} catch (FgClientException e) {
  int statusCode = e.getStatusCode();
  // Handle error and serve default experience
} catch (FgInitException e) {
  e.printStackTrace();
}
```

## Consulte também {#see-also}

* [Notas de versão do Java SDK](java-sdk-release-notes.md)
* [SDKs](../../integrate/sdks.md)
* [Inscrever-se no aplicativo de API](../../integrate/subscribe-to-api-application.md)
* [Etapas de integração](../../integrate/integration-steps.md)
