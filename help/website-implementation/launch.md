---
title: Criar uma propriedade de inicialização
description: Saiba como fazer logon na interface do Launch e criar uma propriedade do Launch. Esta lição é parte do tutorial Implementação da Experience Cloud em sites com lançamento.
seo-description: null
seo-title: Criar uma propriedade de inicialização
solution: Experience Cloud
translation-type: tm+mt
source-git-commit: 7166d2933cc99bcbbd4713fba8f87fb0826b711e

---


# Criar uma propriedade de inicialização

Nesta lição, você criará sua primeira propriedade Launch.

Basicamente, uma propriedade é basicamente um container que você preenche com extensões, regras, elementos de dados e bibliotecas à medida que implanta tags no site.

## Pré-requisitos

Para concluir as próximas lições, é necessário ter permissão para Desenvolver, Aprovar, Publicar, Gerenciar extensões e Gerenciar ambientes no Launch. Se você não conseguir concluir nenhuma dessas etapas porque as opções da interface do usuário não estão disponíveis para você, entre em contato com o administrador da Experience Cloud para solicitar acesso. For more information on Launch permissions, see [the documentation](https://docs.adobe.com/content/help/en/launch/using/reference/admin/user-permissions.html).

## Objetivos de aprendizagem

No final desta lição, você poderá:

* Faça logon na interface do usuário do Launch
* Criar uma nova propriedade Launch
* Configurar uma propriedade Launch

## Ir para o Launch

**Para acessar o Launch**

1. Faça logon na [Adobe Experience Cloud](https://experiencecloud.adobe.com)

1. Clique no ícone do ícone ![Solution Switcher](images/launch-solutionSwitcher.png) para abrir o alternador de soluções

1. Selecione **[!UICONTROL Iniciar]** no menu ![Abra o alternador de soluções usando o ícone e clique em Ativação](images/launch-solutionSwitcherActivation.png)

1. Em **[!UICONTROL Adobe Experience Cloud Launch]**, clique no botão **[!UICONTROL Ir para inicialização]**

   ![Clique no botão Iniciar](images/launch-goToLaunch.png)

You should now see the `Properties` screen (if no properties have ever been created in the account, this screen might be empty):

![Tela Propriedades](images/launch-propertiesScreen.png)

Se você usar o Launch com frequência, também poderá marcar o seguinte URL e fazer logon diretamente em [https://launch.adobe.com](https://launch.adobe.com)

## Criar uma propriedade

Basicamente, uma propriedade é basicamente um container que você preenche com extensões, regras, elementos de dados e bibliotecas à medida que implanta tags no site. Uma propriedade pode ser qualquer agrupamento de um ou mais domínios e subdomínios. É possível gerenciar e rastrear esses ativos da mesma maneira. Por exemplo, suponhamos que você tenha vários sites baseados em um só modelo e queira rastrear os mesmos recursos em todos. É possível aplicar uma propriedade a vários domínios. Para obter mais informações sobre como criar propriedades, consulte ["Empresas e propriedades"](https://docs.adobe.com/content/help/en/launch/using/reference/admin/companies-and-properties.html) na documentação do produto.

**Para criar uma propriedade**

1. Clique no botão **[!UICONTROL Nova propriedade]** :

   ![Clique em Nova propriedade](images/launch-addNewProperty.png)

1. Nomear sua propriedade (por exemplo, `Launch Tutorial` ou `Daniel's Launch Tutorial`)
1. Como o domínio, insira, `enablementadobe.com` pois este é o domínio onde o site de demonstração Luma está hospedado. Embora o campo "Domínio" seja obrigatório, a propriedade Launch funcionará em qualquer domínio em que for implementada. A principal finalidade desse campo é preencher previamente as opções de menu no Construtor de regras.
1. Clique no botão **[!UICONTROL Salvar]**

   ![Criar uma nova propriedade](images/launch-newProperty.png)

Sua nova propriedade deve ser exibida na página Propriedades. Note that if you check the box next to the property name, options to **[!UICONTROL Configure]** or **[!UICONTROL Delete]** the property appear above the property list. Clique no nome da sua propriedade (por exemplo, `Launch Tutorial`) para abrir a `Overview` tela.
![Clique no nome da propriedade para abri-la](images/launch-openProperty.png)

[Próximo "Adicionar o código de inserção para inicialização" &gt;](launch-add-embed.md)
