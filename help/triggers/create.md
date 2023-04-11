---
title: Criar e gerenciar Triggers da Experience Cloud
description: Descubra a interface dos Triggers da Adobe Experience Cloud
hide: true
hidefromtoc: true
source-git-commit: ce0faf9fab45c931feb666ac0c77f5ab5c231746
workflow-type: tm+mt
source-wordcount: '483'
ht-degree: 25%

---

# Criar um acionador da Experience Cloud {#create-triggers}

>[!NOTE]
>
> A nova interface do usuário para Experience Cloud Triggers oferece uma experiência intuitiva para gerenciar comportamentos do consumidor e personalizar experiências do usuário. Para voltar à interface anterior, clique no botão **[!UICONTROL Ir para o modo clássico]** botão.

Crie um acionador e configure as condições para ele. Por exemplo, você pode especificar o critério das regras para um acionador durante uma visita. Alguns exemplos são métricas, como Abandono de carrinho, ou dimensões, como o nome do produto. O disparador é executado quando as regras são cumpridas.

1. No Experience Cloud, selecione o menu avançado e, em seguida, Triggers.

   ![](assets/triggers_7.png)

1. Na página inicial do Trigger, clique em **[!UICONTROL Criar acionador]**, em seguida, especifique o tipo de acionador.

   Três tipos de acionadores estão disponíveis:

   * **[!UICONTROL Abandono]**: Você pode criar um acionador para ser disparado quando um visitante visualizar um produto, mas não fizer adições ao carrinho.

   * **[!UICONTROL Ação]**: Você pode criar acionadores, por exemplo, para serem disparados depois de inscrições em newsletters, assinaturas por email ou aplicações para cartões de crédito (confirmações). Se você for um varejista, crie um acionador para um visitante que se inscreve em um programa de fidelidade. Em mídia e entretenimento, crie acionadores para visitantes que assistem a um certo programa que talvez você queira que respondam a uma pesquisa.

   * **[!UICONTROL Início da sessão e término da sessão]**: Crie um acionador para o início da sessão e o término da sessão.

   ![](assets/triggers_1.png)

1. Adicione um **[!UICONTROL Nome]** e **[!UICONTROL Descrição]** ao seu acionador.

1. Selecione o Analytics **[!UICONTROL Conjunto de relatórios]** usado para este acionador. Esta configuração identifica os dados de relatório que serão usados.

   [Saiba mais sobre o Conjunto de relatórios](https://experienceleague.adobe.com/docs/analytics/admin/admin-tools/manage-report-suites/c-new-report-suite/t-create-a-report-suite.html).

1. Escolha a **[!UICONTROL Acionar depois de nenhuma ação para]** período de validade.

1. No **[!UICONTROL A visita deve incluir]** e **[!UICONTROL A visita não deve incluir]** categorias, você pode definir critérios ou comportamentos de visitante que você deseja ou não que ocorram. Você pode especificar **E** ou **Ou** dentro ou entre condições, dependendo dos critérios que você determinar.

   Por exemplo, as regras para o acionador de um simples abandono de carrinho de compras podem ser:

   * **[!UICONTROL A visita deve incluir]**: `Carts (metric) Is greater or equal to 1` para direcionar visitantes com pelo menos um item em seus carrinhos.
   * **[!UICONTROL A visita não deve incluir]**: `Checkout (metric) Exists.` para remover visitantes que compraram os itens em seus carrinhos.

   ![](assets/triggers_2.png)

1. Clique em **[!UICONTROL Contêiner]** para estabelecer e salvar regras, condições ou filtros que definem um acionador. Para que os eventos aconteçam ao mesmo tempo, você deve colocá-los no mesmo contêiner.

   Cada contêiner é processado independentemente no nível da ocorrência, o que significa que se dois contêineres forem unidos com a variável **[!UICONTROL E]** , as regras só serão qualificadas quando duas ocorrências atenderem aos requisitos.

1. No **[!UICONTROL Metadados]** , clique em **[!UICONTROL + Dimension]** para escolher uma dimensão de Campanha específica ou variáveis relevantes para o comportamento de um visitante.

   ![](assets/triggers_3.png)

1. Clique em **[!UICONTROL Salvar]**.

1. Selecione o recém-criado **[!UICONTROL Acionador]** na lista para acessar o relatório detalhado do seu acionador.

   ![](assets/triggers_4.png)

1. Na exibição detalhada do acionador, é possível acessar os relatórios sobre quantos acionadores foram disparados. Se necessário, você pode editar o acionador com o ícone de lápis.

   ![](assets/triggers_5.png)
