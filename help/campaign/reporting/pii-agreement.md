---
title: Introdução aos relatórios dinâmicos
description: WLaiba mais sobre o contrato de uso de Relatórios dinâmicos
level: Beginner
badge: label="DISPONIBILIDADE LIMITADA" type="Informative" url="../campaign-standard-migration-home.md" tooltip="Restrito a usuários migrados do Campaign Standard"
audience: end-user
exl-id: 9fcef466-f306-480e-b42e-d18daa8bcf06
TQID: https://experienceleague.adobe.com/AGXqq-XOQU8SmHobDIA-nZqw3eNSa2THnw2jQQP54YA
product_v2:
  - id: d0a3eab4-7b10-4d96-a71e-6c0f8e7b7c87
feature_v2:
  - id: fdbb8fc9-ffa3-4b86-88fe-aa4c5a3e1bc6
role_v2:
  - id: b69b2659-1057-424e-8fc5-ed9e016dc554
level_v2:
  - id: e8ccd51f-da0d-4e3b-939b-e30d5ebb1ea5
topic_v2:
  - id: aa2f3246-cb95-4b30-8899-fdf7d73550cc
  - id: eddd9b14-83bd-4ff4-9072-54a4a484abb7
source-git-commit: ad84694f2f6f45e4ee30fc51379106835ac302be
workflow-type: tm+mt
source-wordcount: 549
ht-degree: 3%

---

# Contrato de uso de relatórios dinâmicos {#pii-agreement}

O objetivo do contrato de uso dos Relatórios dinâmicos é funcionar como um consentimento pop-up para o processamento de dados. Por padrão, o contrato só é visível e só pode ser aceito ou recusado por usuários com direitos administrativos.

Para acessar o contrato de uso de Relatórios dinâmicos, selecione **[!UICONTROL Ferramentas]** > **[!UICONTROL Avançado]** > **[!UICONTROL Assistente de implantação]**.

![](assets/pii-agreement.png)

Três opções estão disponíveis:

* **[!UICONTROL Pergunte-me mais tarde]**: até que você aceite ou recuse o contrato, as dimensões do perfil não aparecerão em seus relatórios e as informações de identificação pessoal de seus clientes não serão coletadas ou enviadas.
* **[!UICONTROL Aceitar]**: ao aceitar este contrato, você autoriza a Adobe Campaign a coletar as informações de identificação pessoal de seus clientes e a transferi-las para o data center ou para os relatórios.
* **[!UICONTROL Recusar]**: ao recusar o contrato, as dimensões do perfil não aparecerão em seus relatórios e as informações de identificação Pessoal de seus clientes não serão coletadas ou enviadas. Observe que, nesse caso, a externalID ainda será coletada e usada para identificar os usuários finais.

A tabela abaixo exibe o que acontece após aceitar este contrato, dependendo da sua região.

|  | Relatórios dinâmicos | Conector Microsoft Dynamics 365 |
|---|---|---|
| Américas e APAC (Ásia-Pacífico) | **Recurso disponível**. <br>Todas as informações prontas para uso (ou seja, cidade, país/região, estado, gênero e segmentos com base na idade) e perfis personalizados enviadas para o centro de relatórios dos EUA. | **Recurso disponível**. <br>Todos os campos de perfis prontos para uso e personalizados e de eventos do Adobe Campaign são processados no data center dos EUA. |
| EMEA (Europa, Oriente Médio e África) | **Recurso disponível**. <br>Todas as informações prontas para uso (isto é, cidade, país/região, estado, gênero e segmentos com base na idade) e perfis personalizados são enviadas para o centro de relatórios do EMEA. | **Recurso disponível.** <br>Todos os campos de perfis prontos para uso e personalizados e campos de eventos do Adobe Campaign processados no data center do EMEA. <br>**[!UICONTROL Dados de controle &#x200B;]**, que contêm dados de registro da Adobe I/O e IDs de eventos de usuários finais de clientes enviados e armazenados no data center dos EUA. |

A tabela abaixo exibe o que acontece após a recusa deste contrato, dependendo da sua região. Observe que mesmo que você recuse este contrato, os relatórios sobre deliveries e a integração com o Microsoft Dynamics 365 ainda estarão disponíveis.

| Região | Relatórios dinâmicos | Conector Microsoft Dynamics 365 |
|---|---|---|
| Américas e APAC (Ásia-Pacífico) | **Recurso disponível**. <br> Nenhuma informação de perfil pronta para uso e personalizada enviada para o centro de relatórios dos EUA, com exceção da ExternalID. | **Recurso disponível**. <br>Nenhum campo de perfil pronto para uso ou personalizado enviado para o data center dos EUA, com exceção da ID externa e da ID do destinatário. <br>Todos os campos de eventos do Adobe Campaign processados no data center dos EUA, com exceção da ID da mirror page. |
| EMEA (Europa, Oriente Médio e África) | **Recurso disponível**. <br>Nenhuma informação de perfil pronta para uso e personalizada enviada para a central de relatórios do EMEA, com exceção da ExternalID. | **Recurso disponível.** <br>Nenhum campo de perfil pronto para uso ou personalizado enviado para o data center do EMEA, com exceção da ID externa e da ID do destinatário. <br>Todos os campos de eventos do Adobe Campaign processados no data center do EMEA, com exceção da ID da mirror page. |

Esta opção não é definitiva, você sempre pode alterá-la selecionando a opção **[!UICONTROL realtimeReporting_collectPII]** em **[!UICONTROL Administration]** > **[!UICONTROL Platform]** > **[!UICONTROL Options]**.

O valor pode ser alterado a qualquer momento. O valor 1 corresponde a **[!UICONTROL Pergunte-me mais tarde]**, 2 **[!UICONTROL Recusar]** e 3 **[!UICONTROL Aceitar]**.
