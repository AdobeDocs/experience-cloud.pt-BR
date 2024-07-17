---
title: Relatório de notificação por push
description: Com o relatório pronto para uso de Notificações por push, saiba mais sobre o sucesso das notificações por push.
level: Intermediate
audience: end-user
badge: label="DISPONIBILIDADE LIMITADA" type="Informative" url="../campaign-standard-migration-home.md" tooltip="Restrito a usuários migrados do Campaign Standard"
source-git-commit: 3f4400f24b75e8e435610afbe49e9d9444dbf563
workflow-type: tm+mt
source-wordcount: '394'
ht-degree: 1%

---

# Relatório de notificação por push{#push-notification-report}

>[!CAUTION]
>
>Observe que você deve arrastar e soltar as métricas de **[!UICONTROL Tipo de mensagem]** para suas tabelas a fim de dividir seus dados, dependendo de seus tipos de entrega; neste caso, entregas de notificação por push.

O relatório **Notificação por push** fornece detalhes sobre o desempenho de marketing das notificações por push no Adobe Campaign. Esse relatório pronto para uso ajuda você a entender como os usuários interagem com notificações por push, aplicativos móveis e deliveries.

![](assets/dynamic_report_push.png)

Cada tabela é representada por números de resumo e gráficos. É possível alterar como os detalhes são mostrados nas respectivas configurações de visualização.

A primeira tabela **Resumo de Envolvimento de notificação por push** está dividida em três categorias: por dia, por aplicativo móvel e por entrega. Ele contém os dados disponíveis para a reatividade do recipient ao delivery:

* **[!UICONTROL Processado/enviado]**: número total de notificações por push enviadas.
* **[!UICONTROL Entregue]**: número de notificações por push enviadas com êxito em relação ao número total de notificações por push enviadas.
* **[!UICONTROL Impressões]**: número de vezes que uma notificação por push foi entregue ao dispositivo e deixada intocada na central de notificações. Na maioria dos casos, o número de impressões deve ser semelhante ao número entregue. Isso garante que o dispositivo recebeu a mensagem e transmitiu essas informações de volta ao servidor.
* **[!UICONTROL Impressões exclusivas]**: número de impressões por destinatário.
* **[!UICONTROL Taxa de cliques]**: porcentagem de usuários que interagiram com a notificação por push.
* **[!UICONTROL Taxa de aberturas]**: porcentagem de notificações por push abertas.

![](assets/dynamic_report_push_2.png)

A segunda tabela **Cliques e aberturas por notificação por push** é dividida em três categorias: por dia, por aplicativo móvel e por entrega. Ele contém os dados disponíveis para o comportamento do recipient por delivery:

* **[!UICONTROL Impressões]**: total de notificações por push vistas pelos destinatários.
* **[!UICONTROL Impressões exclusivas]**: número de impressões por destinatário.
* **[!UICONTROL Clique]**: número de vezes que uma notificação por push foi entregue ao dispositivo e clicada pelo usuário. O usuário queria visualizar a notificação, que será movida para o rastreamento de Abertura por push ou a descartará.
* **[!UICONTROL Cliques únicos]**: número de vezes que um usuário único interage com a notificação por push, por exemplo, cliques na notificação ou botão.
* **[!UICONTROL Abrir]**: número total de notificações por push entregues ao dispositivo e clicadas pelos usuários, que estão abrindo o aplicativo. Isso é semelhante ao clique por push, exceto que uma abertura por push não será acionada se a notificação tiver sido descartada.
* **[!UICONTROL Aberturas Exclusivas]**: Número de destinatários que abriram a entrega.
