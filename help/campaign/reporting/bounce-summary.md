---
title: Resumo da rejeição
description: Com o relatório Pronto para uso do resumo de rejeição, saiba mais sobre o status das campanhas enviadas e os erros que elas podem ter encontrado.
audience: end-user
level: Intermediate
badge: label="DISPONIBILIDADE LIMITADA" type="Informative" url="../campaign-standard-migration-home.md" tooltip="Restrito a usuários migrados do Campaign Standard"
source-git-commit: 3f4400f24b75e8e435610afbe49e9d9444dbf563
workflow-type: tm+mt
source-wordcount: '295'
ht-degree: 1%

---

# Resumo da rejeição{#bounce-summary}

Esse relatório detalha os erros gerais de hardware e software encontrados durante os deliveries, bem como o processamento automático de rejeições.

![](assets/campaign_reports_bounces.png)

Cada tabela é representada por números de resumo e gráficos. É possível alterar como os detalhes são mostrados nas respectivas configurações de visualização.

**Repartição Flop 5** lista os cinco deliveries com o maior número de quarentenas:

A variável **Motivos de rejeição** A tabela contém os dados disponíveis para os tipos de erros que causaram rejeições para cada delivery:

* **[!UICONTROL Usuário desconhecido]**: o tipo de erro gerado quando um delivery é enviado para um endereço de email inválido.
* **[!UICONTROL Domínio inválido]**: o tipo de erro gerado quando um delivery é enviado para um endereço de email cujo domínio está errado ou não existe mais.
* **[!UICONTROL Inacessível]**: o tipo de erro encontrado na cadeia de caracteres de entrega de mensagens, como domínio temporariamente inacessível.
* **[!UICONTROL Conta desabilitada]**: o tipo de erro gerado quando um delivery é enviado para um endereço de email que não existe mais.
* **[!UICONTROL Caixa de entrada cheia]**: o tipo de erro gerado quando a caixa de entrada do recipient está cheia. Há cinco tentativas de entregar a mensagem antes que esse erro seja gerado.
* **[!UICONTROL Não conectado]**: o tipo de erro gerado quando o celular do recipient está desligado ou não está conectado a uma rede no momento em que a mensagem é enviada.

  >[!NOTE]
  >
  >Esse tipo de erro só afeta deliveries em canais móveis.

* **[!UICONTROL Recusado]**: o tipo de erro gerado quando um endereço é recusado pelo provedor de serviços de Internet (ISP). Por exemplo, quando uma regra de segurança tiver sido aplicada por um software antisspam.

A variável **Repartição de domínio** A tabela exibe os problemas gerais encontrados durante os deliveries de acordo com o domínio do recipient.
