---
title: Guia da extensão de implantação da experiência para integração com o Android
description: Saiba como integrar a extensão de Implantação de experiência com o Adobe Experience Platform Mobile SDK no Android.
source-git-commit: fcb1d36fc92b3954a902d818a98f579672c577e9
workflow-type: tm+mt
source-wordcount: '934'
ht-degree: 7%

---


# Extensão de implantação da experiência para o Android {#android-extension-integration-guide}

Este guia descreve como integrar a extensão de Implantação de experiência com o Adobe Experience Platform Mobile SDK no Android.

## Pré-requisitos {#prerequisites}

Antes de implementar a extensão de Implantação de experiência, verifique se você tem:

* Uma propriedade móvel configurada em [Adobe Experience Platform Data Collection](https://experience.adobe.com/#/data-collection)
* A extensão de Implantação da experiência instalada e configurada em sua propriedade móvel
* Uma Adobe Experience Cloud Organization ID
* SDK mínimo: API 21 (Android 5.0 Lollipop)

## Dependências de extensão {#extension-dependencies}

A extensão da Implantação de experiência exige as seguintes extensões do Adobe Experience Platform:

| Extensão | Descrição | Obrigatório |
|---|---|---|
| Mobile Core | Fornece funcionalidade principal incluindo configuração e processamento de eventos | Sim |
| Ciclo de vida | Coleta dados do ciclo de vida e da sessão do aplicativo para o Mobile SDK | Sim |
| Edge Network | Permite a comunicação com o Adobe Experience Platform Edge Network | Sim |
| Identidade do Edge | Gerencia a identidade do usuário para o Edge Network | Sim |

Verifique se essas extensões estão instaladas na propriedade móvel da Coleção de dados e incluídas nas dependências do aplicativo.

## Configurar a extensão de Implantação de experiência na Coleção de dados {#configure}

### Instalar a extensão {#install-extension}

1. Faça logon em [Adobe Experience Platform Data Collection](https://experience.adobe.com/#/data-collection).
1. Selecione a guia **Tags** e escolha sua propriedade móvel.
1. Navegue até **Extensões** > **Catálogo**.
1. Pesquise por **Extensão de implantação da experiência** e selecione **Instalar**.
1. Defina as configurações de extensão:

   | Configuração | Descrição |
   |---|---|
   | Sandbox | A sandbox do Adobe Experience Platform que contém a configuração de Implantação da experiência |
   | ID do aplicativo | Um identificador exclusivo para seu aplicativo na Implantação da experiência |
   | ID do conjunto de dados | A ID do conjunto de dados do Adobe Experience Platform para os dados de evento de análise |

1. Selecione **Salvar**.
1. Siga o [processo de publicação](https://experienceleague.adobe.com/pt-br/docs/experience-platform/tags/publish/overview) para atualizar sua configuração.

### Obter a ID do arquivo de ambiente {#environment-file-id}

1. Na propriedade do seu dispositivo móvel, navegue até **Ambientes**.
1. Selecione o ícone de caixa sob a coluna **Instalar** para o seu ambiente.
1. Na caixa de diálogo **Instruções de Instalação do Mobile**, copie a **ID do Arquivo de Ambiente**.

## Adicionar a extensão de Implantação de experiência ao seu aplicativo {#add-to-app}

### Adicionar dependências {#add-dependencies}

Adicione as dependências do Mobile SDK ao seu projeto. A extensão de Implantação de experiência exige o Mobile Core e as extensões relacionadas ao Edge listadas abaixo.

#### Usando Gradle com BOM (Recomendado) {#gradle-bom}

Adicione as seguintes dependências ao arquivo `build.gradle.kts` do seu aplicativo:

```kotlin
dependencies {
    // Adobe Experience Platform Mobile SDK BOM
    implementation(platform("com.adobe.marketing.mobile:sdk-bom:3.+"))

    // Required extensions
    implementation("com.adobe.marketing.mobile:core")
    implementation("com.adobe.marketing.mobile:lifecycle")
    implementation("com.adobe.marketing.mobile:edge")
    implementation("com.adobe.marketing.mobile:edgeidentity")

    // Experience Rollout extension
    implementation("com.adobe.marketing.mobile:rollout")
}
```

#### Uso de Gradle (Groovy) {#gradle-groovy}

```groovy
dependencies {
    // Adobe Experience Platform Mobile SDK BOM
    implementation platform('com.adobe.marketing.mobile:sdk-bom:3.+')

    // Required extensions
    implementation 'com.adobe.marketing.mobile:core'
    implementation 'com.adobe.marketing.mobile:lifecycle'
    implementation 'com.adobe.marketing.mobile:edge'
    implementation 'com.adobe.marketing.mobile:edgeidentity'

    // Experience Rollout extension
    implementation 'com.adobe.marketing.mobile:rollout'
}
```

>[!IMPORTANT]
>
>Para aplicativos de produção, a Adobe recomenda usar números de versão explícitos em vez de versões dinâmicas. Consulte [Gerenciando dependências Gradle](https://docs.gradle.org/current/userguide/dependency_management.html) para obter mais informações.

### Adicionar permissões {#add-permissions}

Adicione as seguintes permissões ao arquivo `AndroidManifest.xml`:

```xml
<uses-permission android:name="android.permission.INTERNET" />
<uses-permission android:name="android.permission.ACCESS_NETWORK_STATE" />
```

### Inicializar o SDK {#initialize-sdk}

Inicialize o Mobile SDK na classe `Application` antes de chamar qualquer API de extensão de Implantação de Experiência. Use a ID de Arquivo de Ambiente da sua propriedade móvel com o `MobileCore.initialize` para que o aplicativo escolha as configurações de implantação publicadas na Coleção de dados.

#### Uso do MobileCore.initialize {#mobile-core-initialize}

Disponível a partir do Android BOM versão 3.8.0, essa API registra extensões automaticamente e ativa o rastreamento de ciclo de vida.

>[!IMPORTANT]
>
>Para aplicativos de produção, use somente `LoggingMode.ERROR`. Não use `DEBUG` ou `VERBOSE` em compilações de versão.

**Kotlin**

```kotlin
import android.app.Application
import com.adobe.marketing.mobile.LoggingMode
import com.adobe.marketing.mobile.MobileCore

class MainApplication : Application() {

    override fun onCreate() {
        super.onCreate()

        MobileCore.setLogLevel(LoggingMode.ERROR)

        // Initialize with your Environment File ID from Data Collection
        MobileCore.initialize(this, "YOUR_ENVIRONMENT_FILE_ID")
    }
}
```

**Java**

```java
import android.app.Application;
import com.adobe.marketing.mobile.LoggingMode;
import com.adobe.marketing.mobile.MobileCore;

public class MainApplication extends Application {

    @Override
    public void onCreate() {
        super.onCreate();

        MobileCore.setLogLevel(LoggingMode.ERROR);

        // Initialize with your Environment File ID from Data Collection
        MobileCore.initialize(this, "YOUR_ENVIRONMENT_FILE_ID", null);
    }
}
```

### Registrar a classe Application {#register-application}

Registre sua classe `Application` em `AndroidManifest.xml`:

```xml
<application
    android:name=".MainApplication"
    ... >
</application>
```

## Contexto de avaliação {#evaluation-context}

`FeatureEvaluationContext` inclui atributos de direcionamento (usados para correspondência da regra de implantação) e identidade opcional (usada para análise).

| Método | Obrigatório | Descrição |
|---|---|---|
| `withIdentity(namespace, id)` | Não | Primeiro argumento: namespace de identidade (consulte [namespaces de identidade da Adobe](https://experienceleague.adobe.com/pt-br/docs/experience-platform/identity/features/namespaces)). Segundo argumento: valor de identidade. Inclua isso quando quiser que o namespace e a ID sejam representados no Analytics para essa avaliação. Se não for fornecido, o Analytics usará a ECID por padrão. Isso não é usado para orientar decisões de ativação de recursos. |
| `withAttributes(map)` | Não | `Map<String, List<String>>`. Chave é o nome do atributo de contexto usado pelas suas regras de implantação (por exemplo `locale`, `platform`, `appVersion`, `deviceType`). Valor é a lista de valores de atributos candidatos para essa chave para o usuário/sessão atual (por exemplo, `["en_US"]` ou `["phone"]`). |

**Kotlin**

```kotlin
import com.adobe.marketing.mobile.rollout.FeatureEvaluationContext

val attrs = mapOf(
    "locale" to listOf("en_US"),
    "platform" to listOf("ANDROID"),
    "appVersion" to listOf("3.0.0")
)

val ctx = FeatureEvaluationContext.builder()
    .withIdentity("Email", "customer@example.com")
    .withAttributes(attrs)
    .build()
```

**Java**

```java
import com.adobe.marketing.mobile.rollout.FeatureEvaluationContext;
import java.util.Arrays;
import java.util.HashMap;
import java.util.List;
import java.util.Map;

Map<String, List<String>> attrs = new HashMap<>();
attrs.put("locale", Arrays.asList("en_US"));
attrs.put("platform", Arrays.asList("ANDROID"));
attrs.put("appVersion", Arrays.asList("3.0.0"));

FeatureEvaluationContext ctx = FeatureEvaluationContext.builder()
        .withIdentity("Email", "customer@example.com")
        .withAttributes(attrs)
        .build();
```

### Amostra de atributos de direcionamento {#sample-attributes}

| Atributo | Descrição | Valores de exemplo |
|---|---|---|
| `locale` | Local/idioma do usuário | `["en_US"]`, `["fr_FR"]` |
| `platform` | Identificador da plataforma | `["ANDROID"]` |
| `appVersion` | Versão do aplicativo | `["3.0.0"]` |
| `deviceType` | Tipo de dispositivo | `["phone"]`, `["tablet"]` |

## Referência da API {#api-reference}

### isFeatureEnabled {#is-feature-enabled}

`isFeatureEnabled` retorna se um recurso de Implantação de Experiência está ativado ou desativado para o contexto fornecido. Envie `featureKey`, um `FeatureEvaluationContext` (atributos de direcionamento opcionais e identidade opcional para análise) e um retorno de chamada. Consulte [Contexto de avaliação](#evaluation-context).

**Assinatura**

*Kotlin*

```kotlin
Rollout.isFeatureEnabled(
    featureKey: String,
    evaluationContext: FeatureEvaluationContext,
    callback: AdobeCallback<Boolean>
)
```

*Java*

```java
Rollout.isFeatureEnabled(
    String featureKey,
    FeatureEvaluationContext evaluationContext,
    AdobeCallback<Boolean> callback);
```

**Parâmetros**

| Parâmetro | Tipo | Descrição |
|---|---|---|
| `featureKey` | String | Chave de recurso para avaliar na implantação da experiência |
| `evaluationContext` | ContextoDeAvaliaçãoDoRecurso | Inclua atributos de direcionamento e identidade opcional para análise conforme necessário; use `FeatureEvaluationContext.builder().build()` para um contexto vazio. Consulte [Contexto de avaliação](#evaluation-context). |
| `callback` | AdobeCallback&lt;Booleano> | Invocado com `true` se o recurso estiver habilitado; caso contrário, `false`. Você também pode passar `AdobeCallbackWithError<Boolean>` para manipular `fail(...)`. |

**Exemplos**

*Kotlin*

```kotlin
import com.adobe.marketing.mobile.AdobeCallback
import com.adobe.marketing.mobile.rollout.Rollout

Rollout.isFeatureEnabled(
    "new-checkout-experience",
    ctx,
    object : AdobeCallback<Boolean> {
        override fun call(isEnabled: Boolean?) {
            if (isEnabled == true) {
                showNewCheckout()
            } else {
                showDefaultCheckout()
            }
        }
    }
)
```

*Java*

```java
import com.adobe.marketing.mobile.AdobeCallback;
import com.adobe.marketing.mobile.rollout.Rollout;

Rollout.isFeatureEnabled(
    "new-checkout-experience",
    ctx,
    new AdobeCallback<Boolean>() {
        @Override
        public void call(Boolean isEnabled) {
            if (Boolean.TRUE.equals(isEnabled)) {
                showNewCheckout();
            } else {
                showDefaultCheckout();
            }
        }
    }
);
```

### getFeature {#get-feature}

`getFeature` retorna a carga do recurso avaliado para o contexto fornecido. Use essa API quando precisar de mais do que habilitado/desabilitado e quiser metadados ou valores de recursos.

**Assinatura**

*Kotlin*

```kotlin
Rollout.getFeature(
    featureKey: String,
    evaluationContext: FeatureEvaluationContext,
    callback: AdobeCallback<FeatureEvaluationResult>
)
```

*Java*

```java
Rollout.getFeature(
    String featureKey,
    FeatureEvaluationContext evaluationContext,
    AdobeCallback<FeatureEvaluationResult> callback);
```

**Parâmetros**

| Parâmetro | Tipo | Descrição |
|---|---|---|
| `featureKey` | String | Chave de recurso para avaliar na implantação da experiência |
| `evaluationContext` | ContextoDeAvaliaçãoDoRecurso | Inclua atributos de direcionamento e identidade opcional para análise conforme necessário; use `FeatureEvaluationContext.builder().build()` para um contexto vazio. Consulte [Contexto de avaliação](#evaluation-context). |
| `callback` | AdobeCallback&lt;ResultadoDaAvaliaçãoDoRecurso> | Invocado com a carga do recurso avaliado; pode ser `null` quando o recurso não é encontrado. Você também pode passar `AdobeCallbackWithError<FeatureEvaluationResult>` para manipular `fail(...)`. |

**Resposta**

*FeatureEvaluationResult*

| Campo | Tipo | Descrição |
|---|---|---|
| `id` | Int | Identificador numérico do recurso |
| `key` | String | Chave do recurso |
| `releaseKey` | String? | Chave de versão para este recurso quando disponível |
| `meta` | String? | Metadados de recurso como uma sequência de caracteres JSON quando disponíveis |
| `analyticsParam` | AnalyticsParam? | Detalhes do Analytics para o recurso avaliado |

*AnalyticsParam*

| Campo | Tipo | Descrição |
|---|---|---|
| `releaseId` | Int | Identificador numérico da versão |
| `featureId` | Int | Identificador numérico do recurso |
| `variantId` | String? | Identificador da variante |

**Exemplos**

*Kotlin*

```kotlin
import com.adobe.marketing.mobile.AdobeCallback
import com.adobe.marketing.mobile.rollout.FeatureEvaluationResult
import com.adobe.marketing.mobile.rollout.Rollout

Rollout.getFeature(
    "new-checkout-experience",
    ctx,
    object : AdobeCallback<FeatureEvaluationResult> {
        override fun call(feature: FeatureEvaluationResult?) {
            val meta = feature?.meta
            if (!meta.isNullOrEmpty()) {
                applyMetaDrivenExperience(meta)
            } else {
                showFallbackExperience()
            }
        }
    }
)
```

*Java*

```java
import com.adobe.marketing.mobile.AdobeCallback;
import com.adobe.marketing.mobile.rollout.FeatureEvaluationResult;
import com.adobe.marketing.mobile.rollout.Rollout;

Rollout.getFeature(
    "new-checkout-experience",
    ctx,
    new AdobeCallback<FeatureEvaluationResult>() {
        @Override
        public void call(FeatureEvaluationResult feature) {
            String meta = feature != null ? feature.getMeta() : null;
            if (meta != null && !meta.isEmpty()) {
                applyMetaDrivenExperience(meta);
            } else {
                showFallbackExperience();
            }
        }
    }
);
```

### refreshCache {#refresh-cache}

Por padrão, a extensão Implantação de experiência sincroniza regularmente as regras e os recursos de implantação mais recentes do servidor, de acordo com um agendamento que você pode configurar. Se você precisar de uma atualização antes da próxima sincronização agendada, chame `refreshCache` para forçar uma atualização. Os casos típicos incluem após o logon ou quando o estado do aplicativo é alterado de uma forma que deve afetar o direcionamento.

**Sintaxe**

*Kotlin*

```kotlin
Rollout.refreshCache()
```

*Java*

```java
Rollout.refreshCache();
```

### extensionVersion {#extension-version}

Retorna a cadeia de caracteres da versão da extensão de Implantação de experiência.

**Sintaxe**

```kotlin
Rollout.extensionVersion(): String
```

**Exemplo**

*Kotlin*

```kotlin
val version = Rollout.extensionVersion()
```

*Java*

```java
String version = Rollout.extensionVersion();
```

## Resumo da API {#api-summary}

| API | Devoluções |
|---|---|
| `isFeatureEnabled(featureKey, evaluationContext, callback)`. `FeatureEvaluationContext` possui atributos de direcionamento para regras e identidade opcional para análise. Consulte [Avaliação de recursos](#is-feature-enabled). | Booleano via retorno de chamada |
| `getFeature(featureKey, evaluationContext, callback)`. Retorna a carga do recurso avaliado para o contexto especificado. Consulte [getFeature](#get-feature). | FeatureEvaluationResult via retorno de chamada |
| `refreshCache()` | void |
| `extensionVersion()` | String |

## Consulte também {#see-also}

* [Aplicativos móveis](../../integrate/mobile-applications.md)
* [Etapas de integração](../../integrate/integration-steps.md)
* [SDKs](../../integrate/sdks.md)
