---
title: Implementação do Adobe Experience Platform Identity Service com o Launch
description: Saiba como adicionar a extensão do Adobe Experience Platform Identity Service e usar a ação Definir IDs do cliente para coletar IDs do cliente. Esta lição é parte do tutorial Implementação da Experience Cloud em aplicativos Swift para iOS móveis.
seo-description: null
seo-title: Implementação do Adobe Experience Platform Identity Service com o Launch
solution: Experience Cloud
translation-type: tm+mt
source-git-commit: e9dee6d0aa3b775d0ce617e2b2c57b56de491b8d

---


# Adicionar o Adobe Experience Platform Identity Service

O Serviço [de identidade da plataforma](https://docs.adobe.com/content/help/en/id-service/using/home.html) Adobe Experience define uma ID de visitante comum em todas as soluções da Adobe para potencializar os recursos da Experience Cloud, como o compartilhamento de público-alvo entre as soluções.  Você também pode enviar suas próprias IDs de cliente ao Serviço para permitir a definição de metas e integrações entre dispositivos com seu sistema de Gerenciamento de Relacionamento com o Cliente (CRM).

O Serviço de identidade faz parte da extensão Mobile Core, ***portanto você já a implementou quando instalou o SDK*** móvel! Atualmente, este tutorial não inclui instruções para a configuração de IDs de cliente. Consulte a documentação para obter detalhes sobre [como definir as IDs](https://aep-sdks.gitbook.io/docs/using-mobile-extensions/mobile-core/identity/identity-api-reference)do cliente.

## Etapas de validação

Para validar as chamadas para o Serviço de identidade, execute o aplicativo de amostra no Xcode ou no Developer Studio, abra o Console de depuração e procure a solicitação e a resposta:

1. **Solicitação ao Serviço** de identidade (filtrar o console para `demdex.net`) Neste exemplo, a ID (`d_mid`)já foi definida e está sendo reportada novamente)

   ```swift
   2019-01-15 12:11:45.164590-0500 BusDemoSwift[52399:5056322] [AMSDK DEBUG <com.adobe.module.identity>]: Sending request (https://dpm.demdex.net/id?d_rtbd=json&d_ver=2&d_orgid=7ABB3E6A5A7491460A495D61@AdobeOrg&d_mid=17179986463578698626041670574784107777&d_blob=j8Odv6LonN4r3an7LhD3WZrU1bUpAkFkkiY1ncBR96t2PTI&dcs_region=9)
   ```

1. **Resposta do Serviço** de identidade (filtre seu console para `ID Service`). Observe como o `mid` valor corresponde ao `d_mid` valor na solicitação acima:

   ```swift
   2019-01-15 12:11:45.681821-0500 BusDemoSwift[52399:5056322] [AMSDK DEBUG <com.adobe.module.identity>]: ID Service - Got ID Response (mid: 17179986463578698626041670574784107777, blob: j8Odv6LonN4r3an7LhD3WZrU1bUpAkFkkiY1ncBR96t2PTI, hint: 9, ttl: "604800000 ms")
   
[Próximo "Adicionar suporte ao Adobe Target VEC" &gt;](target-vec.md)
