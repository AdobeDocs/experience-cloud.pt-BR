---
title: Detalhamento por domínios
description: Com o relatório Detalhamento por domínios pronto para uso, saiba mais sobre os dados de desempenho de seus deliveries dependendo do domínio de cada cliente.
level: Intermediate
audience: end-user
badge: label="DISPONIBILIDADE LIMITADA" type="Informative" url="../campaign-standard-migration-home.md" tooltip="Restrito a usuários migrados do Campaign Standard"
source-git-commit: 3f4400f24b75e8e435610afbe49e9d9444dbf563
workflow-type: tm+mt
source-wordcount: '242'
ht-degree: 2%

---

# Detalhamento por domínios{#breakdown-by-domains}

Este relatório contém os dados de desempenho de cada domínio representado no público-alvo de uma entrega de email. Se for um relatório de campanha ou de programa, os dados de desempenho estão disponíveis para vários públicos-alvo. Esses dados permitem analisar o comportamento de cada domínio em reação a eventos específicos. Por exemplo, exibição de link, URL de inclui na lista de bloqueios etc.

![](assets/delivery_reports_6.png)

A tabela **Estatísticas de transmissão** contém os dados disponíveis para possíveis erros encontrados com cada domínio, como:

* **Processado/enviado**: o número de emails enviados.
* **Entregue**: o número de emails entregues.
* **Devoluções + Erros**: o número de mensagens que não puderam ser entregues.
* **Rejeição permanente**: o número total de erros permanentes, como um endereço de email incorreto.
* **Rejeição leve**: o número total de erros temporários, como uma caixa de entrada cheia.

A segunda tabela, **Estatísticas de rastreamento**, contém os dados disponíveis para a reatividade do recipient ao delivery, como:

* **Entregue**: o número de emails entregues
* **Abertura**: o número de vezes que uma mensagem foi aberta em um delivery.
* **Clique em**: O número de vezes que o conteúdo foi clicado em um delivery.
* **Assinatura cancelada**: O número de cliques no link de subscrição.
* **Mirror Page**: o número de cliques no link da mirror page.
* **Na inclui na lista de bloqueios**: o número de recipients que declararam um email como spam ou lixo eletrônico.
