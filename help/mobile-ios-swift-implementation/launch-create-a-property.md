---
title: Criar uma propriedade de inicialização para aplicativos móveis
description: Saiba como fazer logon na interface do Launch e criar uma propriedade do Mobile Launch. Esta lição é parte do tutorial Implementação da Experience Cloud em aplicativos Swift para iOS móveis.
seo-description: null
seo-title: Criar uma propriedade de inicialização para aplicativos móveis
solution: Experience Cloud
translation-type: tm+mt
source-git-commit: 7166d2933cc99bcbbd4713fba8f87fb0826b711e

---


# Criar uma propriedade de inicialização

O Adobe Experience Platform Launch é a próxima geração de recursos móveis de SDK e gerenciamento de tags do site. O Launch oferece aos clientes uma maneira simples de implantar e gerenciar todas as soluções de análise, marketing e publicidade necessárias para potencializar as experiências relevantes dos clientes. Não há nenhum custo adicional para o Launch. Ele está disponível para qualquer cliente da Adobe Experience Cloud.

Nesta lição, você criará uma propriedade Launch para aplicativos móveis.

## Pré-requisitos

Para concluir as próximas lições, é necessário ter permissão para Desenvolver, Aprovar, Publicar, Gerenciar extensões e Gerenciar ambientes no Launch. Se você não conseguir concluir nenhuma dessas etapas porque as opções da interface do usuário não estão disponíveis para você, entre em contato com o administrador da Experience Cloud para solicitar acesso. For more information on Launch permissions, see [the documentation](https://docs.adobe.com/content/help/en/launch/using/reference/admin/user-permissions.html).

## Objetivos de aprendizagem

No final desta lição, você poderá:

* Faça logon na interface do usuário do Launch
* Criar uma nova propriedade do Launch mobile
* Configurar uma propriedade do Launch para dispositivos móveis

## Ir para o Launch

**Para acessar o Launch**

1. Faça logon na [Adobe Experience Cloud](https://experiencecloud.adobe.com)

1. Clique no ícone do ícone ![Solution Switcher](images/mobile-launch-solutionSwitcher.png) para abrir o alternador de soluções

1. Select **[!UICONTROL Launch]** from the menu

   ![Abra o alternador de soluções usando o ícone e clique em Ativação](images/mobile-launch-solutionSwitcherActivation.png)

1. Em **[!UICONTROL Adobe Experience Cloud Launch]**, clique no botão **[!UICONTROL Ir para inicialização]**

   ![Clique no botão Iniciar](images/mobile-launch-goToLaunch.png)

You should now see the `Properties` screen (if no properties have ever been created in the account, this screen might be empty):

![Tela Propriedades](images/mobile-launch-propertiesScreen.png)

Se você usar o Launch com frequência, também poderá marcar o seguinte URL e fazer logon diretamente em [https://launch.adobe.com](https://launch.adobe.com)

## Criar uma propriedade

Uma propriedade é basicamente um contêiner que você preenche com extensões, regras, elementos de dados e bibliotecas à medida que implanta tags no aplicativo. Uma única propriedade móvel pode ser usada em várias plataformas de aplicativo (por exemplo, iOS e Android), desde que os aplicativos tenham funcionalidade semelhante e exijam a implementação das mesmas soluções.  Para obter mais informações sobre como criar propriedades, consulte ["Configurar uma propriedade móvel"](https://aep-sdks.gitbook.io/docs/getting-started/create-a-mobile-property) na documentação do produto.

**Para criar uma propriedade**

1. Clique no botão **[!UICONTROL Nova propriedade]** :

   ![Clique em Nova propriedade](images/mobile-launch-addNewProperty.png)

1. Nomeie sua propriedade (por exemplo, `Mobile Tutorial`)
1. Como a plataforma, clique em **[!UICONTROL Dispositivo móvel]**
1. Clique no botão **[!UICONTROL Salvar]**

   ![Criar uma nova propriedade](images/mobile-launch-newProperty.png)

Sua nova propriedade deve ser exibida na página Propriedades. Note that if you check the box next to the property name, options to **[!UICONTROL Configure]** or **[!UICONTROL Delete]** the property appear above the property list. Clique no nome da sua propriedade (por exemplo, `Mobile Tutorial`) para abrir a `Overview` tela.
![Clique no nome da propriedade para abri-la](images/mobile-launch-openProperty.png)

[Próximo "Adicionar extensões" &gt;](launch-add-extensions.md)
