---
title: Criação de uma dimensão de perfil
description: Saiba como criar uma dimensão de perfil com base nos dados do perfil.
audience: reporting
content-type: reference
level: Intermediate
exl-id: a12dc772-13c7-45ff-9fbf-3dfdd3801eae
TQID: https://experienceleague.adobe.com/eru99ME-JlrcRl074heBXwVhBLgeQJaQdiJkM-QT2SY
product_v2: id: d0a3eab4-7b10-4d96-a71e-6c0f8e7b7c87
feature_v2: id: fdbb8fc9-ffa3-4b86-88fe-aa4c5a3e1bc6
role_v2: id: b69b2659-1057-424e-8fc5-ed9e016dc554
level_v2: id: b5a62a22-46f7-4f0d-b151-3fc640bef588
topic_v2: id: aa2f3246-cb95-4b30-8899-fdf7d73550ccid: eddd9b14-83bd-4ff4-9072-54a4a484abb7
source-git-commit: ad84694f2f6f45e4ee30fc51379106835ac302be
workflow-type: tm+mt
source-wordcount: 517
ht-degree: 3%

---

# Criação de uma dimensão de perfil{#creating-a-custom-profile-dimension}

Os relatórios também podem ser criados e gerenciados com base nos dados do perfil criados durante a extensão do schema do recipient.

* [Etapa 1: estender o esquema do recipient](##extend-schema)
* [Etapa 2: vincular o novo campo personalizado](#link-custom)
* [Etapa 3: criar um relatório dinâmico para filtrar recipients com a dimensão de perfil](#create-report)

## Etapa 1: estender o esquema do recipient {#extend-schema}

Para adicionar um novo campo de perfil, é necessário estender o esquema, siga as etapas abaixo:

1. Navegue até a pasta **[!UICONTROL Administração]** > **[!UICONTROL Configuração]** > **[!UICONTROL Esquemas de dados]** no Explorer.

   ![](assets/custom_field_1.png)

1. Identifique o esquema de recipient personalizado e selecione-o. Se você ainda não tiver estendido o esquema nms:recipient interno, consulte [este procedimento](https://experienceleague.adobe.com/en/docs/campaign/campaign-v8/developer/shemas-forms/extend-schema).

1. Adicione o campo personalizado ao editor de esquemas.

   Por exemplo, para adicionar um campo personalizado de Fidelidade no esquema do destinatário:

   ```
   <attribute label="Loyalty" name="loyalty" type="string"/>
   ```

   ![](assets/custom_field_2.png)

1. Clique em **[!UICONTROL Salvar]**.

1. Em seguida, identifique o esquema broadLogRcp personalizado e selecione-o. Se você ainda não tiver estendido o esquema interno do Log de entrega, consulte [este procedimento](https://experienceleague.adobe.com/en/docs/campaign/campaign-v8/developer/shemas-forms/extend-schema).

1. Adicione o mesmo campo personalizado do esquema do Recipient ao editor de esquemas.

   ![](assets/custom_field_3.png)

1. Clique em **[!UICONTROL Salvar]**.

1. Para aplicar as modificações feitas aos esquemas, inicie o assistente de Atualização de banco de dados por meio de **[!UICONTROL Ferramentas]** > **[!UICONTROL Avançado]** > **[!UICONTROL Atualizar estrutura de banco de dados]** e execute Atualizar a estrutura do banco de dados. [Saiba mais](https://experienceleague.adobe.com/en/docs/campaign/campaign-v8/developer/shemas-forms/update-database-structure)

   ![](assets/custom_field_4.png)

O novo campo de perfil agora está pronto para ser usado e selecionado pelos recipients.

## Etapa 2: vincular o novo campo personalizado {#link-custom}

>[!NOTE]
>
> Você só pode adicionar até 20 campos personalizados ao relatório Dinâmico.

Agora que o campo de perfil foi criado, precisamos vinculá-lo à dimensão de relatórios dinâmicos correspondente.

Antes de estender o log com nosso campo de perfil, verifique se a janela PII foi aceita para enviar dados PII para o relatório dinâmico. Para obter mais informações, consulte esta [página](pii-agreement.md).

1. Navegue até a pasta **[!UICONTROL Administração]** > **[!UICONTROL Configuração]** > **[!UICONTROL Esquemas de dados]** > **[!UICONTROL Campo de relatórios adicional]** no Explorer.

   ![](assets/custom_field_5.png)

1. Clique em **[!UICONTROL Novo]** para criar a dimensão de relatório Dinâmico correspondente.

1. Selecione **[!UICONTROL Editar expressão]** e navegue pelo esquema de Destinatário para encontrar o campo de perfil criado anteriormente.

   ![](assets/custom_field_6.png)

1. Clique em **[!UICONTROL Concluir]**.

1. Digite sua dimensão **[!UICONTROL Rótulo]**, visível em Relatórios dinâmicos, e clique em **[!UICONTROL Salvar]**.

   ![](assets/custom_field_7.png)

O campo de perfil agora está disponível como uma dimensão de perfil em seus relatórios. Para excluir sua dimensão de perfil, você pode selecioná-la e clicar no ícone **[!UICONTROL Excluir]**.

Agora que o esquema de recipient foi estendido com esse campo de perfil e sua dimensão personalizada criada, você pode começar a direcionar recipients em deliveries.

## Etapa 3: criar um relatório dinâmico para filtrar recipients com a dimensão de perfil {#create-report}

Depois de enviar o delivery, você pode detalhar os relatórios usando a dimensão de perfil.

1. Na guia **[!UICONTROL Relatórios]**, selecione um relatório pronto para uso ou clique no botão **[!UICONTROL Criar]** para iniciar um do zero.

   ![](assets/custom_field_8.png)

1. Na categoria **[!UICONTROL Dimensões]**, clique em **[!UICONTROL Perfil]** e arraste e solte sua dimensão de perfil na tabela de forma livre.

   ![](assets/custom_field_9.png)

1. Arraste e solte quaisquer métricas para começar a filtrar seus dados.

1. Arraste e solte uma visualização no seu espaço de trabalho se necessário.

