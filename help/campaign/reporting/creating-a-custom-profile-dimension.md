---
title: Criação de uma dimensão de perfil personalizada
description: Saiba como criar uma dimensão de perfil personalizada com base nos dados de perfil personalizados.
audience: reporting
content-type: reference
level: Intermediate
source-git-commit: 5a7337c44d6ca5ee4403d9fe0b65246b629afacd
workflow-type: tm+mt
source-wordcount: '457'
ht-degree: 3%

---

# Criação de uma dimensão de perfil personalizada{#creating-a-custom-profile-dimension}

Os relatórios também podem ser criados e gerenciados com base nos dados de perfil personalizados criados durante a extensão de schema do recipient.

* [Etapa 1: estender o esquema do recipient](##extend-schema)
* [Etapa 2: vincular o novo campo personalizado](#link-custom)
* [Etapa 3: criar um relatório dinâmico para filtrar recipients com a dimensão de perfil personalizada](#create-report)

## Etapa 1: estender o esquema do recipient {#extend-schema}

Para adicionar um novo campo de perfil, é necessário estender o esquema, siga as etapas abaixo:

1. Navegue até a **[!UICONTROL Administração]** > **[!UICONTROL Configuração]** > **[!UICONTROL Esquemas de dados]** no Explorer.

   ![](assets/custom_field_1.png)

1. Identifique o esquema de recipient personalizado e selecione-o. Se você ainda não tiver estendido o schema nms:recipient incorporado, consulte [este procedimento](https://experienceleague.adobe.com/en/docs/campaign/campaign-v8/developer/shemas-forms/extend-schema).

1. Adicione o campo personalizado ao editor de esquemas.

   Por exemplo, para adicionar um campo personalizado de Fidelidade no esquema do destinatário:

   ```
   <attribute label="Loyalty" name="loyalty" type="string"/>
   ```

   ![](assets/custom_field_2.png)

1. Clique em **[!UICONTROL Salvar]**.

1. Em seguida, identifique o esquema broadLogRcp personalizado e selecione-o. Se você ainda não tiver estendido o esquema incorporado Log de entrega, consulte [este procedimento](https://experienceleague.adobe.com/en/docs/campaign/campaign-v8/developer/shemas-forms/extend-schema).

1. Adicione o mesmo campo personalizado do esquema do Recipient ao editor de esquemas.

   ![](assets/custom_field_3.png)

1. Clique em **[!UICONTROL Salvar]**.

1. Para aplicar as modificações feitas nos esquemas, inicie o assistente de atualização do banco de dados via **[!UICONTROL Ferramentas]** > **[!UICONTROL Avançado]** > **[!UICONTROL Atualizar estrutura do banco de dados]** e execute o comando Update the database structure. [Saiba mais](https://experienceleague.adobe.com/en/docs/campaign/campaign-v8/developer/shemas-forms/update-database-structure)

   ![](assets/custom_field_4.png)

O novo campo de perfil agora está pronto para ser usado e selecionado pelos recipients.

## Etapa 2: vincular o novo campo personalizado {#link-custom}

>[!NOTE]
>
> Você só pode adicionar até 20 campos personalizados ao relatório Dinâmico.

Agora que o campo de perfil foi criado, precisamos vinculá-lo à dimensão de relatórios dinâmicos correspondente.

1. Navegue até a **[!UICONTROL Administração]** > **[!UICONTROL Configuração]** > **[!UICONTROL Esquemas de dados]** > **[!UICONTROL Campo de relatório adicional]** no Explorer.

   ![](assets/custom_field_5.png)

1. Clique em **[!UICONTROL Novo]** para criar a dimensão correspondente do Dynamic Reporting.

1. Selecionar **[!UICONTROL Editar expressão]** e navegue pelo esquema Recipient para encontrar o campo de perfil personalizado criado anteriormente.

   ![](assets/custom_field_6.png)

1. Clique em **[!UICONTROL Concluir]**.

1. Digite sua dimensão **[!UICONTROL Rótulo]**, visível nos Relatórios dinâmicos e clique em **[!UICONTROL Salvar]**.

   ![](assets/custom_field_7.png)

O campo de perfil personalizado agora está disponível como uma dimensão de perfil personalizada em seus relatórios. Para excluir a dimensão de perfil personalizada, selecione-a e clique no link **[!UICONTROL Excluir]** ícone.

Agora que o esquema de recipient foi estendido com esse campo de perfil e sua dimensão personalizada criada, você pode começar a direcionar recipients em deliveries.

## Etapa 3: criar um relatório dinâmico para filtrar recipients com a dimensão de perfil personalizada {#create-report}

Após enviar a entrega, você pode detalhar os relatórios usando a dimensão de perfil personalizada.

1. No **[!UICONTROL Relatórios]** selecione um relatório pronto para uso ou clique no botão **[!UICONTROL Criar]** botão para iniciar um do zero.

   ![](assets/custom_field_8.png)

1. No **[!UICONTROL Dimension]** categoria, clique em **[!UICONTROL Perfil]** em seguida, arraste e solte sua dimensão de perfil personalizada na tabela de forma livre.

   ![](assets/custom_field_9.png)

1. Arraste e solte quaisquer métricas para começar a filtrar seus dados.

1. Arraste e solte uma visualização no seu espaço de trabalho se necessário.
