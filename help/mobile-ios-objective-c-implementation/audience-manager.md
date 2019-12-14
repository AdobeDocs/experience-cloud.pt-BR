---
title: Implementação do Adobe Audience Manager com o Launch
description: Saiba como implementar o Adobe Audience Manager em seu site usando o encaminhamento pelo lado do servidor e o Launch. Esta lição é parte do tutorial Implementação da Experience Cloud em aplicativos iOS Objetive-C móveis.
seo-description: null
seo-title: Implementação do Adobe Audience Manager com o Launch
solution: Experience Cloud
translation-type: tm+mt
source-git-commit: e9dee6d0aa3b775d0ce617e2b2c57b56de491b8d

---


# Adicionar o Adobe Audience Manager

Esta lição guiará você pelas etapas para implementar o Adobe Audience Manager no SDK da Experience Platform Mobile usando o encaminhamento pelo lado do servidor.

[O Adobe Audience Manager](https://docs.adobe.com/content/help/en/audience-manager/user-guide/aam-home.html) (AAM) fornece serviços líderes do setor para o gerenciamento de dados de público-alvo online, fornecendo aos anunciantes e editores digitais as ferramentas necessárias para controlar e aproveitar seus ativos de dados para ajudar a impulsionar o sucesso das vendas.

## Objetivos de aprendizagem

No final desta lição, você poderá:

1. Descrever as duas principais maneiras de implementar o Audience Manager em um aplicativo móvel
1. Adicionar o Audience Manager usando o encaminhamento pelo lado do servidor do beacon do Analytics
1. Validar a implementação do Audience Manager

## Pré-requisitos

Para concluir esta lição, será necessário:

1. Para ter concluído as lições na seção Configuração do lançamento, a saber, [Criar uma propriedade](launch-create-a-property.md)de inicialização, [Adicionar extensões](launch-add-extensions.md), [Criar uma biblioteca](launch-create-a-library.md)e [Instalar o SDK](launch-install-the-mobile-sdk.md)móvel.

1. Acesso do administrador ao Adobe Analytics para que você possa ativar o encaminhamento pelo lado do servidor para o conjunto de relatórios que está usando para este tutorial. Como alternativa, você pode solicitar que um administrador na sua organização faça isso seguindo as instruções abaixo.

Se você ainda não tiver o Audience Manager implementado, siga estas instruções para [obter seu Subdomínio](https://docs.adobe.com/content/help/en/audience-manager-learn/tutorials/web-implementation/how-to-identify-your-partner-id-or-subdomain.html)do Audience Manager.

## Opções de implementação

Há duas maneiras de implementar o Audience Manager em um aplicativo:

* O encaminhamento pelo lado do servidor (SSF) — para clientes com o Adobe Analytics, essa é a maneira mais fácil e recomendada de implementar. O Adobe Analytics encaminha dados para o AAM no back-end da Adobe, para que você não precise fazer solicitações do aplicativo diretamente para o Audience Manager. Isso também habilita os principais recursos de integração e está em conformidade com nossas práticas recomendadas para implementação e implantação do código do Audience Manager.

* DIL do cliente — Essa abordagem é para clientes que não têm o Adobe Analytics. Os métodos do Audience Manager no aplicativo enviam dados diretamente para o Audience Manager. Nesse caso, você usaria a extensão do Audience Manager no Launch ao configurar sua propriedade do Mobile Launch.

Ao configurar a extensão do Analytics na seção [Adicionar extensões](launch-add-extensions.md) deste tutorial, você marcou a caixa para iniciar o encaminhamento de dados pelo lado do servidor do Analytics para o Audience Manager. Isso inserirá dinamicamente o código necessário para lidar com a resposta dos segmentos do Audience Manager de volta ao aplicativo. Não adicionaremos a extensão do Audience Manager neste tutorial, pois novamente, isso se aplica somente ao caso de uso de quando você NÃO tem o Adobe Analytics.

## Ativar encaminhamento pelo lado do servidor

Há duas etapas principais para fazer uma implementação do SSF:

1. Ativar um "switch" no Admin Console do Analytics para encaminhar dados do Analytics para o Audience Manager *por conjunto* de relatórios.
1. Colocar o código do SDK no lugar, o **que você fez** por meio do Launch simplesmente marcando a caixa na extensão do Analytics para encaminhar dados para o AAM.

### Ativar o encaminhamento pelo lado do servidor no Admin Console do Analytics

Uma configuração no Admin Console do Adobe Analytics é necessária para iniciar o encaminhamento de dados do Adobe Analytics para o Adobe Audience Manager. Lembre-se de que o sistema pode levar até quatro horas para iniciar o encaminhamento dos dados, portanto, lembre-se disso ao solucionar problemas de encaminhamento.

#### Para ativar o SSF no Admin Console do Analytics

1. Faça logon no Analytics por meio da interface do usuário da Experience Cloud. Se você não tiver acesso de Administrador ao Analytics, precisará conversar com seu administrador da Experience Cloud ou do Analytics para atribuir acesso ou concluir essas etapas para você.

   ![Fazer logon na interface do usuário do Adobe Analytics](images/mobile-aam-logIntoAnalytics.png)

1. Na navegação superior do Analytics, escolha **[!UICONTROL Admin &gt; Report Suites]** e, na lista, selecione (ou selecione várias vezes) os conjuntos de relatórios que deseja encaminhar para o Audience Manager.

   ![Clique em Admin Console](images/mobile-aam-analyticsAdminConsoleReportSuites.png)

1. Na tela Report Suites e com os report suites selecionados, escolha **[!UICONTROL Editar configurações &gt; Geral &gt; Encaminhamento]** pelo lado do servidor.

   ![Selecione o menu SSF](images/mobile-aam-selectSSFmenu.png)

   >[!WARNING] Conforme dito acima, será necessário ter privilégios de administrador para ver este item de menu.

1. Uma vez na página Encaminhamento pelo lado do servidor, leia as informações e marque a caixa para **[!UICONTROL Ativar o Encaminhamento]** pelo lado do servidor para os conjuntos de relatórios.

1. Clique em **[!UICONTROL Salvar]**

   ![Configuração de SSF completa](images/mobile-aam-enableSSFcomplete.png)

>[!NOTE] Como o SSF precisa ser habilitado por conjunto de relatórios, não se esqueça de repetir essa etapa para seus conjuntos de relatórios reais quando você estiver implantando o SSF no conjunto de relatórios do aplicativo real.
>
>Além disso, se a opção SSF estiver acinzentada, será necessário "mapear os conjuntos de relatórios para sua organização da Experience Cloud para ativar a opção. Isso é explicado [na documentação](https://docs.adobe.com/content/help/en/core-services/interface/about-core-services/report-suite-mapping.html).

Esse switch iniciará o encaminhamento real de dados para o AAM, desde que você tenha o Adobe Experience Platform Identity Service implementado. O restante da implementação do SSF ocorre no código, que foi manipulado em Iniciar quando você marcou a caixa na extensão do Analytics para encaminhar para o AAM.

O código de encaminhamento pelo lado do servidor agora é implementado para seu aplicativo!

### Validar o encaminhamento pelo lado do servidor

A principal maneira de validar se o encaminhamento pelo lado do servidor está ativo e em execução é verificar a resposta a qualquer uma das ocorrências do Adobe Analytics que vêm do aplicativo.

Se você não estiver fazendo o encaminhamento pelo lado do servidor (SSF) de dados do Analytics para o Audience Manager, não haverá resposta ao beacon do Analytics (além de um pixel 2x2). No entanto, depois que ativamos o SSF, há itens que você pode verificar na solicitação e resposta do Analytics que informarão que ele está funcionando corretamente.

Como o console Xcode não mostra a resposta aos beacons, você deve usar outro depurador/sniffer de pacote que mostra a resposta, como Charles Proxy, por exemplo (que é o que mostrarei na captura de tela abaixo).

1. Abra o depurador e o filtro para `b/ss`, o que limitará o que você vê às solicitações do Adobe Analytics
1. Criar e executar seu aplicativo de amostra dos exercícios anteriores
1. Para qualquer solicitação do Analytics, verifique a resposta. Ele deve conter um `dcs_region` parâmetro, um `uuid` parâmetro e também deve ter um objeto "stuff". Esse objeto é o local para onde as IDs de segmento do AAM serão enviadas de volta ao navegador (para quaisquer segmentos aos quais o usuário pertence, que são atribuídos no AAM a um destino de cookie). Se você tiver o objeto "stuff", o SSF está funcionando!

   ![Resposta AA - objeto stuff](images/mobile-aam-AAresponseCharles.png)

>[!WARNING] Cuidado com o falso "sucesso" - se houver uma resposta, e tudo parece estar funcionando, **certifique** -se de que você tenha esse objeto "coisa". Caso contrário, você poderá ver uma mensagem na resposta que diz "status": "SUCESSO". Por mais louco que isso pareça, isso é prova de que **NÃO** está funcionando corretamente. Caso veja isso, significa que você concluiu a etapa em Iniciar para encaminhar para o AAM, mas o encaminhamento no Admin Console do Analytics ainda não foi concluído. Nesse caso, é necessário verificar se o SSF foi ativado no Admin Console do Analytics. Se você tem, e ainda não passaram 4 horas, seja paciente.

![Resposta AA - falso sucesso](images/mobile-aam-unsuccessful-SSF.png)

[Próximo "Publique sua propriedade" &gt;](publish.md)