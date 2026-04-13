---
title: SDKs
description: Saiba mais sobre a arquitetura do SDK em implantações da Adobe Experience e a extensão móvel do SDK disponível para o Android.
hide: true
exl-id: 110a440d-b52a-4e1e-a94f-86f9741a223a
source-git-commit: 12032cbed45e694a3f25f16afe80308b3eb82924
workflow-type: tm+mt
source-wordcount: '172'
ht-degree: 3%

---

# SDKs {#sdks}

As Implantações de experiência fornecem SDKs para integrar sinalizadores de recursos aos seus aplicativos. Esta página descreve a arquitetura do SDK e as opções disponíveis.

## Arquitetura do SDK {#architecture}

Todos os SDKs de Implantações de experiência compartilham a mesma arquitetura principal:

* **Inicialização** — A SDK é configurada na inicialização e registra-se no serviço de Implantações de Experiência.
* **Recuperação de recursos** — O SDK recupera dados de sinalizador de recursos e avalia sinalizadores localmente.
* **Armazenamento em cache** — O SDK armazena em cache dados de sinalizador de recurso e os atualiza em um TTL (intervalo de sondagem configurável).
* **Tratamento de erros** — Se o serviço não estiver disponível, a SDK continuará a fornecer avaliações de sinalizador de recursos do cache local.

## SDKs disponíveis {#available-sdks}

### Extensão do Android {#android-extension}

A extensão de Implantação de experiência do Android integra-se ao Adobe Experience Platform Mobile SDK.

Consulte o [guia de integração de extensão do Android](../sdk-releases/android/android-extension-integration-guide.md) para obter instruções de configuração.

>[!NOTE]
>
>Outras opções do SDK para plataformas da Web e outras plataformas móveis estão sendo preparadas e estarão disponíveis em breve. Entre em contato com o representante da Adobe para obter orientação de acesso antecipado.

## Consulte também {#see-also}

* [guia de integração de extensão do Android](../sdk-releases/android/android-extension-integration-guide.md)
* [Serviços da web](web-services.md)
* [Etapas de integração](integration-steps.md)

<!-- -->
