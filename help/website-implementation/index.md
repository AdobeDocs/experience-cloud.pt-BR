---
title: Implementação da Adobe Experience Cloud em sites com o Adobe Experience Platform Launch
description: A implementação da Experience Cloud em sites com o Launch é o ponto de partida perfeito para desenvolvedores front-end ou profissionais de marketing técnico que desejam aprender como implementar as soluções da Adobe Experience Cloud em seu site.
seo-description: null
seo-title: Implementação da Adobe Experience Cloud em sites com o Adobe Experience Platform Launch
solution: Experience Cloud
translation-type: tm+mt
source-git-commit: 7166d2933cc99bcbbd4713fba8f87fb0826b711e

---


# Visão geral

_A implementação da Experience Cloud em sites com o Launch_ é o ponto de partida perfeito para desenvolvedores front-end ou profissionais de marketing técnico que desejam aprender como implementar as soluções da Adobe Experience Cloud em seu site.

Cada lição contém exercícios práticos e informações básicas para ajudá-lo a implementar a Experience Cloud e entender seu valor.  Chamadas são fornecidas para destacar informações que podem ser úteis para clientes que migram de nosso gerenciador de tags mais antigo — Gerenciamento dinâmico de tags. Os sites de demonstração são fornecidos para que você complete o tutorial e possa aprender as técnicas subjacentes em um ambiente seguro. Após concluir este tutorial, você deve estar pronto para começar a implementar todas as suas soluções de marketing por meio do Launch em seu próprio site.

Depois de concluir, você poderá:

* Criar uma propriedade de inicialização

* Instalar uma propriedade de inicialização em um site

* Adicione as seguintes soluções da Adobe Experience Cloud:
   * **[Adobe Experience Platform Identity Service](id-service.md)**
   * **[Adobe Target](target.md)**
   * **[Adobe Analytics](analytics.md)**
   * **[Adobe Audience Manager](audience-manager.md)**

* Criar regras e elementos de dados para enviar dados às soluções da Adobe

* Validar a implementação usando o Adobe Experience Cloud Debugger

* Publicar alterações no Launch por meio de ambientes de desenvolvimento, armazenamento temporário e produção

>[!NOTE] Tutoriais de várias soluções semelhantes também estão disponíveis para as seguintes plataformas:
>
> * [Implementação da Experience Cloud em aplicativos Mobile iOS Swift™](/help/mobile-ios-swift-implementation/index.md)
* [Implementação da Experience Cloud em aplicativos iOS Objetive-C móveis](/help/mobile-ios-objective-c-implementation/index.md)
* [Implementação da Experience Cloud em aplicativos Mobile Android](/help/mobile-android-implementation/index.md)


## Pré-requisitos

Nessas lições, presume-se que você tenha uma Adobe Id e as permissões necessárias para concluir os exercícios. Caso contrário, talvez seja necessário entrar em contato com o administrador da Experience Cloud para solicitar acesso.

* Para o Launch, você deve ter permissão para Desenvolver, Aprovar, Publicar, Gerenciar extensões e Gerenciar ambientes. For more information on Launch permissions, see [the documentation](https://docs.adobe.com/content/help/en/launch/using/reference/admin/user-permissions.html).
* Para o Adobe Analytics, você deve saber seu servidor de rastreamento e quais conjuntos de relatórios você usará para concluir este tutorial
* Para o Audience Manager, você deve saber seu Subdomínio do Audience Manager (também conhecido como "Nome do parceiro", "ID do parceiro" ou "Subdomínio do parceiro")

Além disso, pressupõe-se que você esteja familiarizado com linguagens de desenvolvimento front-end como HTML e JavaScript. Não é necessário ser um mestre nessas linguagens para concluir as lições, mas você extrairá mais delas se ler e entender o código confortavelmente.

## Sobre o Launch

O Adobe Experience Platform Launch é a próxima geração de recursos de gerenciamento de tags do site e SDK móvel da Adobe. O Launch oferece aos clientes uma maneira simples de implantar e gerenciar todas as soluções de análise, marketing e publicidade necessárias para potencializar as experiências relevantes dos clientes. Não há nenhum custo adicional para o Launch. Ele está disponível para qualquer cliente da Adobe Experience Cloud.

O Launch for sites permite que você gerencie centralmente todas as soluções JavaScript relacionadas a análises, marketing e publicidade usadas em seu desktop e sites móveis. Por exemplo, se você implantar o Adobe Analytics, o Launch gerenciará a biblioteca JavaScript do AppMeasurement, preencherá variáveis e acionará solicitações.

A tag do contêiner de inicialização é 60% mais leve que o DTM e 40% mais leve que o Google Tag Manager. O conteúdo do contêiner é minimizado, incluindo seu código personalizado. Tudo é modular. Se não precisar de um item, ele não é incluído na biblioteca. O resultado é uma implementação rápida e compacta.

O Launch também é uma plataforma que permite que fornecedores de terceiros criem extensões para facilitar a implantação de suas soluções por meio do Launch. Uma extensão é um pacote de código (JavaScript, HTML e CSS) que estende a interface do usuário do Launch e a funcionalidade do cliente. Pense no Launch como um sistema operacional e nas extensões como os aplicativos usados para realizar as tarefas.

## Sobre as lições

Nessas lições, você implementará a Adobe Experience Cloud em um site de varejo falso chamado Luma. O site [](https://luma.enablementadobe.com/content/luma/us/en.html) Luma tem uma camada de dados avançada e funcionalidade que permitirá a criação de uma implementação realista. Você criará sua própria propriedade do Launch, em sua própria organização da Experience Cloud, e a mapeará para nosso site hospedado do Luma usando o Depurador da Experience Cloud.

[![Site da Luma](images/overview-luma.png)](https://luma.enablementadobe.com/content/luma/us/en.html)

## Obter as ferramentas

1. Como você estará usando algumas extensões específicas do navegador, recomendamos concluir o tutorial usando o [navegador web Chrome](https://www.google.com/chrome/)
1. Add the [Adobe Experience Cloud Debugger](https://chrome.google.com/webstore/detail/adobe-experience-cloud-de/ocdmogmohccmeicdhlhhgepeaijenapj) extension to your Chrome browser
1. Download the [sample html page](https://www.enablementadobe.com/multi/web/basic-sample.html) (right-click on this link and click "Save Link As")
1. Obtenha um editor de texto no qual você pode fazer alterações na página html de amostra. (Se você não tiver um, recomendamos experimentar [Colchetes](http://brackets.io/))
1. Marcar o site [Luma](https://luma.enablementadobe.com/content/luma/us/en.html)

>[!NOTE] Você pode achar mais fácil concluir este tutorial com o site Luma aberto no Chrome, ao ler este tutorial e concluir as etapas da interface do Launch em um navegador diferente.

Vamos começar!

[Próximo "Criar uma propriedade de inicialização" &gt;](launch.md)