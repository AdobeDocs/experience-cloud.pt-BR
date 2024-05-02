---
title: Marca
description: Saiba como configurar sua marca
audience: administration
context-tags: branding,overview;branding,main
role: Admin
level: Experienced
badge: label="DISPONIBILIDADE LIMITADA" type="Informative" url="../campaign-standard-migration-home.md" tooltip="Restrito a usuários migrados do Campaign Standard"
source-git-commit: 56f2d2ff4b2ba4184629615a14724e6640df6961
workflow-type: tm+mt
source-wordcount: '277'
ht-degree: 57%

---

# Configurar marcas {#branding-configure}

>[!IMPORTANT]
>
>As marcas não podem ser criadas ou modificadas pelos usuários finais: essas operações têm de ser efetuadas pelo administrador técnico do Adobe Campaign. Para receber qualquer solicitação, entre em contato com o Atendimento ao cliente da Adobe.

No Adobe Campaign V8, as marcas podem ser encontradas na **[!UICONTROL Administração > Plataforma > Marca]** menu.

Uma **[!UICONTROL Marca]** é definida pelas seguintes características:

* Uma **[!UICONTROL identidade]** que define e personaliza sua marca. Esta seção contém os seguintes campos:

   * **[!UICONTROL Rótulo]** visível na interface
   * **[!UICONTROL ID]**
   * **[!UICONTROL Nome da marca]**
   * **[!UICONTROL URL do site]** e **[!UICONTROL Rótulo do site]** da marca
   * **[!UICONTROL Logotipo da marca]**

  ![](assets/branding_1.png)

* **[!UICONTROL Parâmetros de cabeçalho de emails enviados]** que personaliza o que os recipients das campanhas verão. Esta seção contém os seguintes campos:

   * **[!UICONTROL Remetente (endereço de email)]** com o endereço de email da marca.
   * **[!UICONTROL Remetente (nome)]** com o nome da marca.
   * **[!UICONTROL Responder a (endereço de email)]** com o endereço de email ao qual o cliente pode responder.
   * **[!UICONTROL Responder a (nome)]** com o nome da marca.
   * **[!UICONTROL Erro (endereço de email)]** com o endereço de email que será usado em caso de erro.

  >[!IMPORTANT]
  >
  >Após atualizar os parâmetros de cabeçalho dos emails, caso o nome e o endereço de email do remetente não tiverem sido alterados no email criado a partir do modelo, verifique as configurações avançadas do modelo.

  ![](assets/branding_2.png)

* **[!UICONTROL Configurações da marca]** define os servidores usados para rastreamento também para acesso à página de aterrissagem. Esta seção contém os seguintes campos:

   * **[!UICONTROL Subdomínio da marca]** refere-se ao URL do subdomínio designado específico para essa marca, solicitado para delegação do Adobe.

  Observe que a configuração para rastreamento, espelhamento e servidores de aplicativos é armazenada em contas externas separadas associadas ao roteamento. Essas configurações são aplicadas durante o provisionamento e não devem ser modificadas. Para exibir URLs, acesse o **[!UICONTROL Prefixos de marca]** da conta externa.

  ![](assets/branding_3.png)

<!--![](assets/branding_05.png)-->

<!--
* **[!UICONTROL Tracking URL configs]**, which defines the configuration of the URLs tracking for your brand.

  The additional parameters that allow the links to be tracked on external systems such as Web Analytics tools like Adobe Analytics or Google Analytics are defined here.
-->
