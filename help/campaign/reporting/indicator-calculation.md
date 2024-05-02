---
title: Cálculo do indicador
description: Entenda os resultados de seus relatórios com uma lista de todas as fórmulas de métrica.
level: Intermediate
audience: end-user
badge: label="DISPONIBILIDADE LIMITADA" type="Informative" url="../campaign-standard-migration-home.md" tooltip="Restrito a usuários migrados do Campaign Standard"
source-git-commit: 031d5b692d9b9e4420b14ba1ab892fbafed57ec0
workflow-type: tm+mt
source-wordcount: '388'
ht-degree: 7%

---

# Cálculo do indicador{#indicator-calculation}

>[!NOTE]
>
>Para processar e gerenciar melhor grandes volumes e análises em tempo real, os Relatórios dinâmicos usam agregações aproximadas para estimativas de contagem distintas. Agregações aproximadas oferecem uso de memória limitado e geralmente são mais rápidas que cálculos exatos.

As tabelas abaixo fornecem a lista de indicadores usados nos diferentes relatórios e suas fórmulas de cálculo, dependendo do tipo de delivery.

## Entrega por email {#email-delivery}

<table> 
 <thead> 
  <tr> 
   <th> <strong>Label</strong> <br/> </th> 
   <th> <strong>Nome do campo</strong> <br/> </th> 
   <th> <strong>Fórmula do cálculo de indicador</strong> <br/> </th> 
   <th> <strong>Comentários</strong><br/> </th> 
  </tr> 
 </thead> 
 <tbody> 
  <tr> 
   <td> Conta desabilitada<br/> </td> 
   <td> @disabled<br/> </td> 
   <td> count(@failureReason=4)<br/> </td> 
   <td> </td> 
  </tr> 
  <tr> 
   <td> Na inclui na lista de bloqueios<br/> </td> 
   <td> @blacklisted<br/> </td> 
   <td> count(@failureReason=8, @failureType=2)<br/> </td> 
   <td> </td> 
  </tr> 
  <tr> 
   <td> taxa de Inclui na lista de bloqueios<br/> </td> 
   <td> @rateBlacklisted<br/> </td> 
   <td> @blacklisted/@sent<br/> </td> 
   <td> O denominador para cálculo de taxa é baseado na contagem Enviada (Entregue + Rejeições).<br/> </td> 
  </tr> 
  <tr> 
   <td> Devoluções + Erros<br/> </td> 
   <td> @bounces<br/> </td> 
   <td> count(@status=2)<br/> </td> 
   <td> </td> 
  </tr> 
  <tr> 
   <td> Rejeição + taxa de erro<br/> </td> 
   <td> @rateBounces<br/> </td> 
   <td> @bounces/@sent<br/> </td> 
   <td> </td> 
  </tr> 
  <tr> 
   <td> Clique em<br/> </td> 
   <td> @clicks<br/> </td> 
   <td> count(@trackingUrlType=1 ou 10 ou 11)<br/> </td> 
   <td> </td> 
  </tr> 
  <tr> 
   <td> Taxa de cliques<br/> </td> 
   <td> @clickthrough<br/> </td> 
   <td> @uniqueclicks/@delivered<br/> </td> 
   <td> O denominador para o cálculo da taxa baseia-se em Delivered only.<br/> </td> 
  </tr> 
  <tr> 
   <td> Entregue<br/> </td> 
   <td> @delivered<br/> </td> 
   <td> count(@status=1)<br/> </td> 
   <td> </td> 
  </tr> 
  <tr> 
   <td> Taxa de entregas<br/> </td> 
   <td> @rateDelivered<br/> </td> 
   <td> @delivered/@sent<br/> </td> 
   <td> O denominador para cálculo de taxa é baseado na contagem Enviada (Entregue + Rejeições).<br/> </td> 
  </tr> 
  <tr> 
   <td> Devoluções permanentes<br/> </td> 
   <td> @hardBounces<br/> </td> 
   <td> count(@failureType=2 E @failureReason=8)<br/> </td> 
   <td> </td> 
  </tr> 
  <tr> 
   <td> Taxa de devoluções permanentes<br/> </td> 
   <td> @rateHardBounces<br/> </td> 
   <td> @hardBounces/@sent<br/> </td> 
   <td> O denominador para cálculo de taxa é baseado na contagem Enviada (Entregue + Rejeições).<br/> </td> 
  </tr> 
  <tr> 
   <td> Domínio inválido<br/> </td> 
   <td> @invalidDomain<br/> </td> 
   <td> count(@failureReason=2)<br/> </td> 
   <td> </td> 
  </tr> 
  <tr> 
   <td> Caixa de entrada cheia<br/> </td> 
   <td> @mailBoxFull<br/> </td> 
   <td> count(@failureReason=5)<br/> </td> 
   <td> </td> 
  </tr> 
  <tr> 
   <td> Mirror page<br/> </td> 
   <td> @mirrorPage<br/> </td> 
   <td> count(@trackingUrlType=6)<br/> </td> 
   <td> O denominador para o cálculo da taxa baseia-se em Delivered only.<br/> </td> 
  </tr> 
  <tr> 
   <td> Taxa de mirror pages<br/> </td> 
   <td> @rateMirrorPage<br/> </td> 
   <td> @mirrorPage/@delivered<br/> </td> 
   <td> </td> 
  </tr> 
  <tr> 
   <td> Não conectado<br/> </td> 
   <td> @notConnected<br/> </td> 
   <td> count(@failureReason=6)<br/> </td> 
   <td> </td> 
  </tr> 
  <tr> 
   <td> Abertura<br/> </td> 
   <td> @uniqueOpens<br/> </td> 
   <td> count(@trackingUrlType=2 + unique(@trackingUrlType=1,2,3,6,10,11) - unique(@trackingUrlType=2))<br/> </td> 
   <td> </td> 
  </tr> 
  <tr> 
   <td> Taxa de aberturas<br/> </td> 
   <td> @rateOpens<br/> </td> 
   <td> @opens/@delivered<br/> </td> 
   <td> O denominador para o cálculo da taxa baseia-se em Delivered only.<br/> </td> 
  </tr> 
  <tr> 
   <td> Quarentena<br/> </td> 
   <td> @quarantine<br/> </td> 
   <td> isQuarantine=true<br/> </td> 
   <td> </td> 
  </tr> 
  <tr> 
   <td> Taxa de quarentena<br/> </td> 
   <td> @rateQuarantine<br/> </td> 
   <td> @quarantine/@sent<br/> </td> 
   <td> O denominador para cálculo de taxa é baseado na contagem Enviada (Entregue + Rejeições).<br/> </td> 
  </tr>
  <tr> 
   <td> Rejeitada<br/> </td> 
   <td> @rejected<br/> </td> 
   <td> count(@failureReason=20, @failureType=2)<br/> </td> 
   <td> </td> 
  </tr> 
  <tr> 
   <td> Taxa de rejeições<br/> </td> 
   <td> @rateRejected<br/> </td> 
   <td> @rejected/@sent<br/> </td> 
   <td> O denominador para cálculo de taxa é baseado na contagem Enviada (Entregue + Rejeições).<br/> </td> 
  </tr> 
  <tr> 
   <td> Processado/enviado<br/> </td> 
   <td> @sent<br/> </td> 
   <td> @delivered + @bounces<br/> </td> 
   <td> </td> 
  </tr> 
  <tr> 
   <td> Rejeição leve<br/> </td> 
   <td> @softBounces<br/> </td> 
   <td> count(@failureType=1)<br/> </td> 
   <td> </td> 
  </tr> 
  <tr> 
   <td> Taxa de rejeição temporária<br/> </td> 
   <td> @rateSoftBounces<br/> </td> 
   <td> @softBounces/@sent<br/> </td> 
   <td> O denominador para cálculo de taxa é baseado na contagem Enviada (Entregue + Rejeições).<br/> </td> 
  </tr> 
  <tr> 
   <td> Cliques únicos<br/> </td> 
   <td> @uniqueclicks<br/> </td> 
   <td> Cliques únicos são calculados usando conceitos ThetaSketch. </a>.<br/> </td> 
   <td> </td> 
  </tr> 
  <tr> 
   <td> Aberturas únicas<br/> </td> 
   <td> @uniqueopens<br/> </td> 
   <td> unique(@trackingUrlType=1,2,3,6,10,11)<br/> </td> 
   <td> </td> 
  </tr> 
  <tr> 
   <td> Inacessível <br/> </td> 
   <td> @unreachable<br/> </td> 
   <td> count(@failureReason=3)<br/> </td> 
   <td> </td> 
  </tr> 
  <tr> 
   <td> Cancelar inscrição<br/> </td> 
   <td> @unsubscribes<br/> </td> 
   <td> count(@trackingUrlType=3)<br/> </td> 
   <td> </td> 
  </tr> 
  <tr> 
   <td> Taxa de cancelamento de inscrição<br/> </td> 
   <td> @rateUnsubscribes<br/> </td> 
   <td> @unsubscribes/@delivered<br/> </td> 
   <td> O denominador para o cálculo da taxa baseia-se em Delivered only.<br/> </td> 
  </tr> 
  <tr> 
   <td> Usuário desconhecido<br/> </td> 
   <td> @unknownUser<br/> </td> 
   <td> count(@failureReason=1)<br/> </td> 
   <td> </td> 
  </tr> 
 </tbody> 
</table>

<!--
## Push notification delivery {#push-notification-delivery}

<table> 
 <thead> 
  <tr> 
   <th> <strong>Label</strong> <br/> </th> 
   <th> <strong>Field name</strong> <br/> </th> 
   <th> <strong>Indicator calculation formula</strong> <br/> </th> 
  </tr> 
 </thead> 
 <tbody> 
  <tr> 
   <td> Processed/sent<br/> </td> 
   <td> @sent<br/> </td> 
   <td> @count(status=sent)<br/> </td> 
  </tr> 
  <tr> 
   <td> Delivered<br/> </td> 
   <td> @delivered<br/> </td> 
   <td> @count(status=delivered)<br/> </td> 
  </tr> 
  <tr> 
   <td> Delivered rate<br/> </td> 
   <td> @rateDelivered<br/> </td> 
   <td> (@delivered/@sent)*100<br/> </td> 
  </tr> 
  <tr> 
   <td> Bounce + Error rate<br/> </td> 
   <td> @rateBounces<br/> </td> 
   <td> (@delivered/@sent)*100<br/> </td> 
  </tr> 
  <tr> 
   <td> Open<br/> </td> 
   <td> @opens<br/> </td> 
   <td> @count(status=open)<br/> </td> 
  </tr> 
  <tr> 
   <td> Open rate<br/> </td> 
   <td> @rateOpens<br/> </td> 
   <td> (@opens/@delivered)*100<br/> </td> 
  </tr> 
  <tr> 
   <td> Unique opens<br/> </td> 
   <td> @uniqueopens<br/> </td> 
   <td> Unique opens is calculated using ThetaSketch concepts of unique RecipientIds.<br/> </td> 
  </tr> 
  <tr> 
   <td> Impressions<br/> </td> 
   <td> @impressions<br/> </td> 
   <td> @count(status=delivered)<br/> </td> 
  </tr> 
  <tr> 
   <td> Unique impressions<br/> </td> 
   <td> @uniqueimpressions<br/> </td> 
   <td> @unique(@count(status=view))<br/> </td> 
  </tr> 
  <tr> 
   <td> Click<br/> </td> 
   <td> @clicks<br/> </td> 
   <td> @count(status=interact)<br/> </td> 
  </tr> 
  <tr> 
   <td> Unique clicks<br/> </td> 
   <td> @uniqueclicks<br/> </td> 
   <td> Unique clicks is calculated using ThetaSketch concepts.<br/> </td> 
  </tr> 
  <tr> 
   <td> Click through rate<br/> </td> 
   <td> @clickthrough<br/> </td> 
   <td> (@interact/@delivered)*100<br/> </td> 
  </tr> 
 </tbody> 
</table>

## In-App delivery {#in-app-delivery}

<table> 
 <thead> 
  <tr> 
   <th> <strong>Label</strong> <br/> </th> 
   <th> <strong>Field name</strong> <br/> </th> 
   <th> <strong>Indicator calculation formula</strong> <br/> </th> 
   <th> <strong>Comments</strong><br/> </th> 
  </tr> 
 </thead> 
 <tbody> 
  <tr> 
   <td> Processed/sent<br/> </td> 
   <td> @sent<br/> </td> 
   <td> @count(status=sent)<br/> </td> 
   <td> sent=delivered<br/> </td> 
  </tr> 
  <tr> 
   <td> Delivered<br/> </td> 
   <td> @delivered<br/> </td> 
   <td> @count(status=delivered)<br/> </td> 
   <td> delivered=sent<br/> </td> 
  </tr> 
  <tr> 
   <td> Impressions<br/> </td> 
   <td> @impressions<br/> </td> 
   <td> @count(status=view) or @count(status=button 1 click + button 2 click + dismissals)<br/> </td> 
   <td> </td> 
  </tr> 
  <tr> 
   <td> Unique impressions<br/> </td> 
   <td> @uniqueimpressions<br/> </td> 
   <td> @unique(@count(status=view))<br/> </td> 
   <td> For <span class="uicontrol">Target users based on their Campaign profile (inAppProfile)</span> template, user = Recipient Id.<br/> For <span class="uicontrol">Target all users of a Mobile app (inAppBroadcast)</span> and <span class="uicontrol">Target users based on their Mobile profile (inApp)</span> templates, user = MC Id or equivalent that represents a unique combination of user, mobile app and device.<br/> </td> 
  </tr> 
  <tr> 
   <td> In-App clicks <br/> </td> 
   <td> @inappclicks<br/> </td> 
   <td> @count (status=click)<br/> </td> 
   <td> </td> 
  </tr> 
  <tr> 
   <td> Unique In-App clicks<br/> </td> 
   <td> @uniqueinapp<br/> </td> 
   <td> @unique(@count (status=clicks))<br/> </td> 
   <td> For <span class="uicontrol">Target users based on their Campaign profile (inAppProfile)</span> template, user = Recipient Id.<br/> For <span class="uicontrol">Target all users of a Mobile app (inAppBroadcast)</span> and <span class="uicontrol">Target users based on their Mobile profile (inApp)</span> templates, user = MC Id or equivalent that represents a unique combination of user, mobile app and device.<br/> </td> 
  </tr> 
  <tr> 
   <td> In-App click through rate<br/> </td> 
   <td> @inappclickthrough<br/> </td> 
   <td> Total clicks on Button 1 or Button 2/total impressions*100<br/> </td> 
   <td> </td> 
  </tr> 
  <tr> 
   <td> In-App dismissal<br/> </td> 
   <td> @dismissal<br/> </td> 
   <td> @count (status=close)<br/> </td> 
   <td> </td> 
  </tr> 
  <tr> 
   <td> Unique In-App dismissals<br/> </td> 
   <td> @uniquedismissal<br/> </td> 
   <td> @unique(@count (status=close))<br/> </td> 
   <td> For <span class="uicontrol">Target users based on their Campaign profile (inAppProfile)</span> template, user = Recipient Id.<br/> For <span class="uicontrol">Target all users of a Mobile app (inAppBroadcast)</span> and <span class="uicontrol">Target users based on their Mobile profile (inApp)</span> templates, user = MC Id or equivalent that represents a unique combination of user, mobile app and device.<br/> </td> 
  </tr> 
  <tr> 
   <td> In-App dismissal rate<br/> </td> 
   <td> @dismissalrate<br/> </td> 
   <td> Total close/total impressions*100<br/> </td> 
   <td> </td> 
  </tr> 
 </tbody> 
</table>
-->