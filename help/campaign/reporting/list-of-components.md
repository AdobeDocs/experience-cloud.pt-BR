---
title: Lista de componentes
description: Encontre aqui a lista de todos os componentes disponíveis em Relatórios dinâmicos, bem como suas definições.
level: Beginner
audience: end-user
badge: label="DISPONIBILIDADE LIMITADA" type="Informative" url="../campaign-standard-migration-home.md" tooltip="Restrito a usuários migrados do Campaign Standard"
source-git-commit: b11d696767209145511b38735f22275a38676ade
workflow-type: tm+mt
source-wordcount: '770'
ht-degree: 2%

---

# Lista de componentes {#list-of-components}

Observe que, se dois componentes não forem compatíveis, a célula exibirá o valor **Nenhum**.

## Dimensões {#dimensions}

A tabela abaixo fornece a lista de dimensões usadas em relatórios e suas definições.

<table> 
 <thead> 
  <tr> 
   <th> Dimension<br/> </th> 
   <th> Definição<br/> </th> 
  </tr> 
 </thead> 
 <tbody> 
  <tr> 
   <td> Navegador<br/> </td> 
   <td> Navegador no qual a mensagem foi aberta ou clicada.<br/> </td> 
  </tr> 
  <tr> 
   <td> Campanha<br/> </td> 
   <td> Rótulo e ID da sua campanha.<br/> </td> 
  </tr> 
  <tr> 
   <td> Entrega<br/> </td> 
   <td> Etiqueta e ID da entrega.<br/> </td> 
  </tr> 
  <tr> 
   <td> Dispositivo<br/> </td> 
   <td> Dispositivo no qual o email/SMS/notificação por push foi aberto/exibido/clicado.<br/> </td> 
  </tr> 
  <tr> 
   <td> Motivo da falha<br/> </td> 
   <td> Tipos de erros que causaram rejeições para cada delivery, por exemplo, usuário desconhecido, domínio inválido ou caixa de correio cheia.<br/> </td> 
  </tr> 
  <tr> 
   <td> Nome do aplicativo móvel<br/> </td> 
   <td> Nome do aplicativo móvel<br/> </td> 
  </tr>
  <tr> 
   <td> Platform<br/> </td> 
   <td> Plataforma do dispositivo do qual a mensagem foi aberta/exibida/clicada.<br/> </td> 
  </tr> 
  <tr> 
   <td> Perfil<br/> </td> 
   <td> Reagrupa campos de perfil prontos para uso e personalizados criados durante a extensão de recurso de perfil.<br/> </td> 
  </tr> 
  <tr> 
   <td> Domínio do destinatário<br/> </td> 
   <td> Domínio usado para abrir o email.<br/> </td> 
  </tr> 
  <tr> 
   <td> Entrega recorrente<br/> </td> 
   <td> Rótulo e ID da entrega recorrente.<br/> </td> 
  </tr> 
  <tr> 
   <td> Domínio do remetente<br/> </td> 
   <td> Domínio usado para enviar o email.<br/> </td> 
  </tr> 
  <tr> 
   <td> IP do remetente<br/> </td> 
   <td> IP usado para enviar o email.<br/> </td> 
  </tr> 
  <tr> 
   <td> URL de rastreamento<br/> </td> 
   <td> URL no qual o usuário clicou a partir da mensagem.<br/> </td> 
  </tr> 
  <tr> 
   <td> Categoria de URL de rastreamento<br/> </td> 
   <td> Categoria atribuída ao URL de rastreamento.<br/> </td> 
  </tr> 
  <tr> 
   <td> Rótulo do URL de rastreamento<br/> </td> 
   <td> Rótulo fornecido ao URL, como mirror page, entre em contato conosco ou abra.<br/> </td> 
  </tr> 
  <tr> 
   <td> Entrega transacional<br/> </td> 
   <td> Rótulo e ID da entrega transacional.<br/> </td> 
  </tr> 
  <tr> 
   <td> Variante<br/> </td> 
   <td> Variante do email em caso de teste A/B.<br/> </td> 
  </tr> 
 </tbody> 
</table>

## Métricas {#metrics}

As tabelas abaixo fornecem a lista de métricas usadas em relatórios e suas definições, dependendo do tipo de delivery.

### Métricas de email {#email-and-sms-metrics}

<table> 
 <thead> 
  <tr> 
   <th> Métrica<br/> </th> 
   <th> Definição<br/> </th> 
  </tr> 
 </thead> 
 <tbody> 
  <tr> 
   <td> Na inclui na lista de bloqueios<br/> </td> 
   <td> Número de destinatários que declararam um email como spam ou lixo eletrônico.<br/> </td> 
  </tr> 
  <tr> 
   <td> taxa de Inclui na lista de bloqueios<br/> </td> 
   <td> Porcentagem de entregas marcadas na inclui na lista de bloqueios.<br/> </td> 
  </tr> 
  <tr> 
   <td> Devoluções + Erros<br/> </td> 
   <td> Total de erros acumulados durante o processamento de delivery e retorno automático em relação ao número total de mensagens enviadas.<br/> </td> 
  </tr> 
  <tr> 
   <td> Rejeição + taxa de erro<br/> </td> 
   <td> Porcentagem de emails enviados em comparação ao email enviado.<br/> </td> 
  </tr> 
  <tr> 
   <td> Clique em<br/> </td> 
   <td> Número de vezes que um conteúdo foi clicado em um delivery.<br/> </td> 
  </tr> 
  <tr> 
   <td> Taxa de cliques<br/> </td> 
   <td> Porcentagem de cliques em uma entrega.<br/> </td> 
  </tr> 
  <tr> 
   <td> Entregue<br/> </td> 
   <td> Número de mensagens enviadas com êxito em relação ao número total de mensagens enviadas.<br/> </td> 
  </tr> 
  <tr> 
   <td> Taxa de entregas<br/> </td> 
   <td> Porcentagem de mensagens enviadas com êxito.<br/> </td> 
  </tr> 
  <tr> 
   <td> Rejeição permanente<br/> </td> 
   <td> Número total de erros permanentes, como um endereço de email incorreto.<br/> </td> 
  </tr> 
  <tr> 
   <td> Taxa de rejeição permanente<br/> </td> 
   <td> Porcentagem de entregas que falharam devido a erros permanentes.<br/> </td> 
  </tr> 
  <tr> 
   <td> Mirror page<br/> </td> 
   <td> Número de destinatários que clicaram no link da mirror page.<br/> </td> 
  </tr> 
  <tr> 
   <td> Taxa de mirror pages<br/> </td> 
   <td> Porcentagem de cliques no link da mirror page em comparação ao total de mensagens de delivery.<br/> </td> 
  </tr> 
  <tr> 
   <td> Cliques de oferta<br/> </td> 
   <td> Número de vezes que uma oferta foi clicada em um delivery.<br/> </td> 
  </tr> 
  <tr> 
   <td> Taxa de cliques da oferta<br/> </td> 
   <td> Porcentagem de cliques em uma oferta.<br/> </td> 
  </tr> 
  <tr> 
   <td> Abertura<br/> </td> 
   <td> Número de vezes que uma mensagem foi aberta em um delivery.<br/> </td> 
  </tr> 
  <tr> 
   <td> Taxa de aberturas<br/> </td> 
   <td> Porcentagem de mensagens abertas.<br/> </td> 
  </tr> 
  <tr> 
   <td> Processado/enviado<br/> </td> 
   <td> Número total de envios para a entrega.<br/> </td> 
  </tr> 
  <tr> 
   <td> Quarentena<br/> </td> 
   <td> Número de mensagens que foram rejeitadas e resultaram na quarentena do endereço.<br/> </td> 
  </tr> 
  <tr> 
   <td> Taxa de quarentena<br/> </td> 
   <td> Porcentagem de quarentenas em comparação às mensagens enviadas.<br/> </td> 
  </tr> 
  <tr> 
   <td> Rejeitada<br/> </td> 
   <td> Número de mensagens classificadas como spam pelos servidores SMTP.<br/> </td> 
  </tr> 
  <tr> 
   <td> Taxa de rejeições<br/> </td> 
   <td> Porcentagem de mensagens marcadas como rejeitadas.<br/> </td> 
  </tr> 
  <tr> 
   <td> Rejeição leve<br/> </td> 
   <td> Número total de erros temporários, como uma caixa de entrada cheia.<br/> </td> 
  </tr> 
  <tr> 
   <td> Taxa de rejeição temporária<br/> </td> 
   <td> Porcentagem de entregas que falharam devido a um motivo temporário.<br/> </td> 
  </tr> 
  <tr> 
   <td> Cliques únicos<br/> </td> 
   <td> Número de recipients que clicaram em um conteúdo em um delivery.<br/> </td> 
  </tr> 
  <tr> 
   <td> Aberturas únicas<br/> </td> 
   <td> Número de destinatários que abriram o delivery.<br/> </td> 
  </tr> 
  <tr> 
   <td> Assinatura única cancelada<br/> </td> 
   <td> Número de recipients que clicaram no link unsubscription.<br/> </td> 
  </tr> 
  <tr> 
   <td> Taxa de cancelamento de inscrição<br/> </td> 
   <td> Número de cancelamentos de subscrição exclusivos em comparação às mensagens entregues.<br/> </td> 
  </tr> 
  <tr> 
   <td> Assinatura cancelada<br/> </td> 
   <td> Número de cliques no link unsubscription.<br/> </td> 
  </tr> 
 </tbody> 
</table>

<!--
### Push notification metrics {#push-notification-metrics}

<table> 
 <thead> 
  <tr> 
   <th> Metric<br/> </th> 
   <th> Definition<br/> </th> 
  </tr> 
 </thead> 
 <tbody> 
  <tr> 
   <td> Bounces + Errors<br/> </td> 
   <td> Total of errors cumulated during delivery in relation to the total number of sent messages, e.g. errors from MCPNS or provider.<br/> </td> 
  </tr> 
  <tr> 
   <td> Bounce + Error rate<br/> </td> 
   <td> Percentage of push notifications that bounced compared to push notifications sent.<br/> </td> 
  </tr> 
  <tr> 
   <td> Click<br/> </td> 
   <td> Number of times a push notification has been delivered to the device and clicked on by the user. The user either wanted to view the notification, which will then be moved to Push Open tracking, or dismiss it.<br/> </td> 
  </tr> 
  <tr> 
   <td> Click through rate<br/> </td> 
   <td> Percentage of users who interacted with the push notification.<br/> </td> 
  </tr> 
  <tr> 
   <td> Delivered<br/> </td> 
   <td> Number of push notifications successfully sent, in relation to the total number of sent push notifications.<br/> </td> 
  </tr> 
  <tr> 
   <td> Delivered rate<br/> </td> 
   <td> Percentage of push notifications successfully sent.<br/> </td> 
  </tr> 
  <tr> 
   <td> Impressions<br/> </td> 
   <td> Number of times a push notification has been delivered to the device and left untouched in the notification center. In most cases, impressions number should be similar to the delivered number. This ensures that the device got the message and relayed that information back to the server.<br/> </td> 
  </tr> 
  <tr> 
   <td> Processed/sent<br/> </td> 
   <td> Total number of push notifications sent.<br/> </td> 
  </tr> 
  <tr> 
   <td> Open<br/> </td> 
   <td> Total number of push notifications delivered to the device and clicked on by users thus opening the app. This is similar to the Push Click except a Push Open will not be triggered if the notification was dismissed.<br/> </td> 
  </tr> 
  <tr> 
   <td> Open rate<br/> </td> 
   <td> Percentage of opened push notifications.<br/> </td> 
  </tr> 
  <tr> 
   <td> Unique clicks<br/> </td> 
   <td> Number of times a unique user interacts with the push notification, e.g. clicks on the notification or button.<br/> </td> 
  </tr> 
  <tr> 
   <td> Unique impressions<br/> </td> 
   <td> Number of impressions by recipient.<br/> </td> 
  </tr> 
  <tr> 
   <td> Unique Opens<br/> </td> 
   <td> Number of recipients who opened the delivery.<br/> </td> 
  </tr> 
 </tbody> 
</table>

### In-App metrics {#in-app-metrics}

<table> 
 <thead> 
  <tr> 
   <th> Metric<br/> </th> 
   <th> Definition<br/> </th> 
  </tr> 
 </thead> 
 <tbody> 
  <tr> 
   <td> Delivered<br/> </td> 
   <td> Total number of In-App messages delivered to the device by the service provider.<br/> </td> 
  </tr> 
  <tr> 
   <td> Impressions<br/> </td> 
   <td> Total of In-App messages seen by recipients depending on whether trigger criterion was met.<br/> </td> 
  </tr> 
  <tr> 
   <td> In-App clicks <br/> </td> 
   <td> Total number of recipients who clicked on Button 1 or Button 2.<br/> </td> 
  </tr> 
  <tr> 
   <td> In-App click through rate<br/> </td> 
   <td> Percentage of users who clicked on Button 1 or Button 2 compared to users who saw the message.<br/> </td> 
  </tr> 
  <tr> 
   <td> In-App dismissal<br/> </td> 
   <td> Total number of messages that recipients dismissed either by clicking the close button or auto-dismiss.<br/> </td> 
  </tr> 
  <tr> 
   <td> In-App dismissal rate<br/> </td> 
   <td> Percentage of In-App messages that recipients dismissed.<br/> </td> 
  </tr> 
  <tr> 
   <td> Processed/sent<br/> </td> 
   <td> Total number of In-App messages sent from Adobe Campaign as part of the delivery sent process.<br/> </td> 
  </tr> 
  <tr> 
   <td> Unique impressions<br/> </td> 
   <td> Number of impressions by a unique recipient.<br/> </td> 
  </tr> 
  <tr> 
   <td> Unique In-App clicks<br/> </td> 
   <td> Number of times recipients clicked on Button 1 or Button 2.<br/> </td> 
  </tr> 
  <tr> 
   <td> Unique In-App dismissals<br/> </td> 
   <td> Number of time recipients dismissed an In-App message.<br/> </td> 
  </tr> 
 </tbody> 
</table>
-->

## Segmentos {#segments}

A tabela abaixo fornece a lista de segmentos usados em relatórios e suas definições.

<table> 
 <thead> 
  <tr> 
   <th> Segmento<br/> </th> 
   <th> Definição<br/> </th> 
  </tr> 
 </thead> 
 <tbody> 
  <tr> 
   <td> Idade: Boomers 1<br/> </td> 
   <td> Recipients nascidos de 1946 a 1954.<br/> </td> 
  </tr> 
  <tr> 
   <td> Idade: Boomers 2<br/> </td> 
   <td> Recipients nascidos de 1955 a 1965.<br/> </td> 
  </tr> 
  <tr> 
   <td> Idade: de 18 a 25<br/> </td> 
   <td> Recipients de 18 a 25 anos.<br/> </td> 
  </tr> 
  <tr> 
   <td> Idade: de 26 a 30<br/> </td> 
   <td> Recipients de 26 a 30 anos.<br/> </td> 
  </tr> 
  <tr> 
   <td> Idade: de 31 a 40<br/> </td> 
   <td> Recipients de 31 a 40 anos.<br/> </td> 
  </tr> 
  <tr> 
   <td> Idade: de 41 a 50<br/> </td> 
   <td> Recipients de 41 a 50 anos.<br/> </td> 
  </tr> 
  <tr> 
   <td> Idade: Geração X<br/> </td> 
   <td> Recipients nascidos de 1966 a 1976.<br/> </td> 
  </tr> 
  <tr> 
   <td> Idade: geração Y (Millennials)<br/> </td> 
   <td> Recipients nascidos de 1977 a 1994.<br/> </td> 
  </tr> 
  <tr> 
   <td> Idade: geração Z<br/> </td> 
   <td> Recipients nascidos de 1995 a hoje.<br/> </td> 
  </tr> 
  <tr> 
   <td> Idade: maior que 50<br/> </td> 
   <td> Recipients com idade superior a 50 anos.<br/> </td> 
  </tr> 
  <tr> 
   <td> Idade: menos de 25<br/> </td> 
   <td> Recipients com menos de 25 anos.<br/> </td> 
  </tr> 
  <tr> 
   <td> Idade: menos de 30<br/> </td> 
   <td> Recipients com menos de 30 anos.<br/> </td> 
  </tr> 
  <tr> 
   <td> Idade: menos de 40<br/> </td> 
   <td> Recipients com menos de 40 anos.<br/> </td> 
  </tr> 
  <tr> 
   <td> Idade: menos de 50<br/> </td> 
   <td> Recipients com menos de 50 anos.<br/> </td> 
  </tr> 
  <tr> 
   <td> Idade: geração silenciosa<br/> </td> 
   <td> Recipients nascidos em 1945 ou antes.<br/> </td> 
  </tr> 
  <tr> 
   <td> Todas as visitas<br/> </td> 
   <td> Todos os recipients<br/> </td> 
  </tr>
 </tbody> 
</table>
