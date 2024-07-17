---
title: Resumo da rejeição
description: Com o relatório Pronto para uso do resumo de rejeição, saiba mais sobre o status das campanhas enviadas e os erros que elas podem ter encontrado.
audience: end-user
level: Intermediate
badge: label="DISPONIBILIDADE LIMITADA" type="Informative" url="../campaign-standard-migration-home.md" tooltip="Restrito a usuários migrados do Campaign Standard"
exl-id: b341edad-aa82-43d8-a5a1-b33a19973a1a
source-git-commit: 34c6f8a137a9085b26c0ea8f78930cff6192cfc9
workflow-type: tm+mt
source-wordcount: '295'
ht-degree: 1%

---

# Resumo da rejeição{#bounce-summary}

Esse relatório detalha os erros gerais de hardware e software encontrados durante os deliveries, bem como o processamento automático de rejeições.

![](assets/campaign_reports_bounces.png)

Cada tabela é representada por números de resumo e gráficos. É possível alterar como os detalhes são mostrados nas respectivas configurações de visualização.

A **repartição de Flop 5** lista as cinco entregas com o maior número de quarentenas:

A tabela **Motivos da rejeição** contém os dados disponíveis para os tipos de erros que causaram rejeições para cada entrega:

* **[!UICONTROL Usuário desconhecido]**: o tipo de erro gerado quando uma entrega é enviada para um endereço de email inválido.
* **[!UICONTROL Domínio inválido]**: o tipo de erro gerado quando uma entrega é enviada para um endereço de email cujo domínio está errado ou não existe mais.
* **[!UICONTROL Inacessível]**: o tipo de erro encontrado na cadeia de caracteres de entrega de mensagens, como domínio temporariamente inacessível.
* **[!UICONTROL Conta desabilitada]**: o tipo de erro gerado quando uma entrega é enviada para um endereço de email que não existe mais.
* **[!UICONTROL Caixa de entrada cheia]**: o tipo de erro gerado quando a caixa de entrada do destinatário está cheia. Há cinco tentativas de entregar a mensagem antes que esse erro seja gerado.
* **[!UICONTROL Não conectado]**: o tipo de erro gerado quando o celular do destinatário está desligado ou não está conectado a uma rede no momento em que a mensagem é enviada.

  >[!NOTE]
  >
  >Esse tipo de erro só afeta deliveries em canais móveis.

* **[!UICONTROL Recusado]**: o tipo de erro gerado quando um endereço é recusado pelo provedor de serviços de Internet. Por exemplo, quando uma regra de segurança tiver sido aplicada por um software antisspam.

A tabela **Repartição de domínio** exibe os problemas gerais encontrados durante as entregas de acordo com o domínio do destinatário.
