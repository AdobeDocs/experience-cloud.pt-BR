---
title: Implementação da Experience Cloud em aplicativos iOS Objetive-C móveis
description: A implementação da Experience Cloud em aplicativos iOS Objetive-C móveis é o ponto de partida perfeito para desenvolvedores de aplicativos móveis que desejam aprender como implementar as soluções da Adobe Experience Cloud em seus aplicativos iOS Objetive-C móveis.
seo-description: null
seo-title: 'Implementação da Experience Cloud em aplicativos iOS Objetive-C móveis '
solution: Experience Cloud
translation-type: tm+mt
source-git-commit: 7166d2933cc99bcbbd4713fba8f87fb0826b711e

---


# Visão geral

_A implementação da Experience Cloud em aplicativos_ iOS Objetive-C móveis é o ponto de partida perfeito para desenvolvedores de aplicativos móveis que desejam aprender como implementar as soluções da Adobe Experience Cloud em seus aplicativos iOS Objetive-C.

Cada lição contém exercícios práticos e informações básicas para ajudá-lo a implementar a Experience Cloud e entender seu valor.  Um aplicativo de demonstração Objetive-C é fornecido para você concluir o tutorial, para que você possa aprender as técnicas subjacentes em um ambiente seguro. Após concluir este tutorial, você deve estar pronto para começar a implementar todas as soluções da Experience Cloud em seu próprio aplicativo iOS Objetive-C!

Após concluir este tutorial, você poderá:

* Criar uma propriedade do Mobile Launch

* Instalar uma propriedade Launch em um aplicativo Objetive-C

* Implemente as seguintes soluções da Adobe Experience Cloud:
   * **[Adobe Experience Platform Identity Service](id-service.md)**
   * **[Adobe Target](target-vec.md)**
   * **[Adobe Analytics](analytics.md)**
   * **[Adobe Audience Manager](audience-manager.md)**

* Publicar alterações no Launch por meio de ambientes de desenvolvimento, armazenamento temporário e produção

>[!NOTE] Tutoriais de várias soluções semelhantes também estão disponíveis para as seguintes plataformas:
>
> * [Implementação da Experience Cloud em aplicativos Mobile iOS Swift™](/help/mobile-ios-swift-implementation/index.md)
* [Implementação da Experience Cloud em aplicativos Mobile Android™](/help/mobile-android-implementation/index.md)
* [Implementação da Experience Cloud em sites com o Launch](/help/website-implementation/index.md)


## Pré-requisitos

Nessas lições, presume-se que você tenha uma Adobe Id e as permissões necessárias para concluir os exercícios. Caso contrário, talvez seja necessário entrar em contato com o administrador da Experience Cloud para solicitar acesso.

* Para o Launch, você deve ter permissão para Desenvolver, Aprovar, Publicar, Gerenciar extensões e Gerenciar ambientes. For more information on Launch permissions, see [the documentation](https://docs.adobe.com/content/help/en/launch/using/reference/admin/user-permissions.html).
* Para o Target, você deve ter acesso de nível de aprovador à interface do Adobe Target
* Para o Adobe Analytics, você deve saber seu servidor de rastreamento e quais conjuntos de relatórios você usará para concluir este tutorial

Além disso, presume-se que você esteja familiarizado com o desenvolvimento do iOS no Objetivo C. Você não precisa ser um mestre do Objetivo C para concluir as lições, mas você terá mais deles se puder ler e entender o código confortavelmente.

## Sobre as lições

Nessas lições, você implementará a Adobe Experience Cloud em um aplicativo de demonstração chamado "Registro[de](https://github.com/Adobe-Marketing-Cloud/busbooking-mobileapps)barramento" usando sua própria organização da Experience Cloud. O aplicativo tem alguns recursos simples que permitirão concluir uma implementação básica da Experience Cloud para dispositivos móveis antes de você fazer isso em seu próprio aplicativo.

[![Aplicativo de reserva de barramento](images/mobile-busBookingApp.png)](https://github.com/Adobe-Marketing-Cloud/busbooking-mobileapps)

## Obter as ferramentas

1. Você deve usar um Mac® para concluir este tutorial
1. Baixar [Xcode](https://developer.apple.com/xcode/)
1. Baixe o aplicativo [Bus Books](https://github.com/Adobe-Marketing-Cloud/busbooking-mobileapps)
1. Instalar [Cocoapods](https://guides.cocoapods.org/using/getting-started.html)

Vamos começar!

[Próximo "Criar uma propriedade de inicialização" &gt;](launch-create-a-property.md)