---
title: Implementação das integrações da Experience Cloud com o Launch
description: Saiba como validar as integrações de Públicos-alvo, A4T e Atributos do cliente na implementação da Adobe Experience Cloud. Esta lição é parte do tutorial Implementação da Experience Cloud em sites com lançamento.
seo-description: null
seo-title: Implementação das integrações da Experience Cloud com o Launch
solution: Experience Cloud
translation-type: tm+mt
source-git-commit: e9dee6d0aa3b775d0ce617e2b2c57b56de491b8d

---


# Integrações da Experience Cloud

Nesta lição, você verificará as principais integrações entre as soluções que acabou de implementar. A boa notícia é que, ao completar as primeiras lições, já implementou os códigos das integrações! Você não precisa fazer nenhum trabalho adicional nesta lição além de ler e validar.

## Objetivos de aprendizagem

No final desta lição, você poderá:

1. Explicar os casos de uso básicos para as integrações de Compartilhamento de público-alvo, Analytics para Target (A4T) e Atributos do cliente
1. Validar os aspectos básicos de implementação do lado do cliente nessas integrações

## Pré-requisitos

Você deve concluir todas as lições anteriores neste tutorial antes de seguir as instruções desta lição.

>[!NOTE] Muitos requisitos de permissões de usuário, configurações de conta e etapas de provisionamento que estão além do escopo deste tutorial são necessários para usar essas integrações. Se você ainda não estiver usando essas integrações na implementação atual da Experience Cloud, considere o seguinte:
>
> * Analise todos os requisitos das [integrações dos serviços principais](https://docs.adobe.com/content/help/en/core-services/interface/about-core-services/core-services.html)
> * Analise os requisitos completos da [integração do Analytics for Target](https://docs.adobe.com/content/help/en/target/using/integrate/a4t/before-implement.html)
> * Have an Administrator of your Experience Cloud Organization [request provisioning of these integrations](https://www.adobe.com/go/audiences)


## Audiences

[Os públicos-alvo](https://docs.adobe.com/content/help/en/core-services/interface/audiences/audience-library.htm) fazem parte do serviço principal de pessoas e permitem que você compartilhe públicos-alvo entre soluções. Por exemplo, você pode criar um público-alvo no Audience Manager e usá-lo para fornecer conteúdo personalizado com o Target.

Os principais requisitos para implementar o A4T—que você já fez—são:

1. Implementação do Adobe Experience Platform Identity Service
1. Implementar o Audience Manager
1. Implemente outras soluções que você gostaria de receber ou criar públicos-alvo, como Target e Analytics

### Validar a integração de Públicos-alvo

A melhor maneira de validar a integração do Audiences é criar um público-alvo, compartilhá-lo em outra solução e usá-lo totalmente na outra solução (por exemplo, confirme se um visitante que se qualifica para um segmento do AAM pode se qualificar para uma atividade do Target direcionada a esse segmento). No entanto, isso está fora do escopo deste tutorial.

Essas etapas de validação se concentrarão na parte crítica visível na implementação do cliente — a ID do visitante.

1. Open the [Luma site](https://luma.enablementadobe.com/content/luma/us/en.html)

1. Make sure the Debugger is mapping the Launch property to *your* Development environment, as described in the [earlier lesson](launch-switch-environments.md)

   ![Seu ambiente de desenvolvimento do Launch mostrado no Debugger](images/switchEnvironments-debuggerOnWeRetail.png)

1. Vá para a guia Rede do Depurador

1. Clique em **[!UICONTROL Limpar todas as solicitações]** apenas para limpar as coisas

1. Recarregue a página Luma, certificando-se de visualizar as solicitações do Target e do Analytics no Depurador

1. Recarregue a página Luma novamente

1. Agora você deve ver quatro solicitações na guia Rede do Depurador — duas para Target e duas para Analytics

1. Examine a linha denominada "ID de visitante da Experience Cloud". As IDs em cada solicitação de cada solução devem ser sempre as mesmas.

   ![Confirmar os SDIDs correspondentes](images/integrations-matchingECIDs.png)

1. As IDs são exclusivas por visitante, o que você pode confirmar solicitando que um parceiro repita essas etapas.

## Analytics for Target (A4T)

The [Analytics for Target (A4T)](https://docs.adobe.com/content/help/en/target/using/integrate/a4t/a4t.html) integration allows you to leverage your Analytics data as the source for reporting metrics in Target.

Os principais requisitos para implementar o A4T—que você já fez—são:

1. Implementação do Adobe Experience Platform Identity Service
1. Disparar a solicitação de carregamento da página do Target antes do beacon de exibição da página do Analytics

O A4T funciona unindo uma solicitação do lado do servidor do Target ao Analytics com o beacon de exibição de página do Analytics, que chamamos de "agrupamento de ocorrência".  A identificação de ocorrências requer que a solicitação do Target que fornece a atividade (ou incrementa uma métrica de objetivo baseada no Target) tenha um parâmetro que corresponda a um parâmetro no beacon de exibição de página do Analytics. Esse parâmetro é chamado de ID de dados complementares (SDIDs).

### Validar a implementação do A4T

A melhor maneira de validar a integração do A4T é criar uma atividade do Target usando o A4T e validar os dados do relatório, no entanto, isso está além do escopo deste tutorial. Este tutorial mostrará como confirmar se as ids de dados complementares correspondem entre as chamadas da solução.

**Para validar os SDIDs**

1. Open the [Luma site](https://luma.enablementadobe.com/content/luma/us/en.html)

1. Make sure the Debugger is mapping the Launch property to *your* Development environment, as described in the [earlier lesson](launch-switch-environments.md)

   ![Seu ambiente de desenvolvimento do Launch mostrado no Debugger](images/switchEnvironments-debuggerOnWeRetail.png)

1. Vá para a guia Rede do Depurador

1. Clique em **[!UICONTROL Limpar todas as solicitações]** apenas para limpar as coisas

1. Recarregue a página Luma, certificando-se de visualizar as solicitações do Target e do Analytics no Depurador

1. Recarregue a página Luma novamente

1. Agora você deve ver quatro solicitações na guia Rede do Depurador — duas para Target e duas para Analytics

1. Dê uma olhada na linha denominada "ID de dados complementares". As IDs do primeiro carregamento de página devem corresponder entre o Target e o Analytics. As IDs do segundo carregamento da página também devem corresponder, mas serem diferentes das IDs do primeiro carregamento da página.

   ![Confirmar os SDIDs correspondentes](images/integrations-matchingSDIDs.png)

Se você fizer solicitações adicionais do Target no escopo de um carregamento de página (não incluindo aplicativos de página única) que fazem parte das atividades do A4T, é bom fornecer nomes exclusivos (não mbox-global-target) para que eles continuem tendo os mesmos SDIDs das solicitações iniciais do Target e Analytics.

## Atributos do cliente

[Atributos](https://docs.adobe.com/content/help/en/core-services/interface/customer-attributes/attributes.html) do cliente é uma parte do serviço principal de pessoas que permite carregar dados do banco de dados do gerenciamento de relacionamento com o cliente (CRM) e aproveitá-los no Adobe Analytics e no Adobe Target.

Os principais requisitos para implementar os Atributos do cliente, que você já fez, são:

1. Implementação do Adobe Experience Platform Identity Service
1. Set Customer Ids via the Id Service *before* Target and Analytics fire their requests (which you accomplished using the rule ordering feature in Launch)

### Validar a implementação dos atributos do cliente

Você já validou que as IDs do cliente são passadas para o Serviço de identidade e para o Target em lições anteriores. Também é possível validar a ID do cliente na ocorrência do Analytics.
No momento, a ID do cliente é um dos poucos parâmetros que não aparecem no Depurador da Experience Cloud, portanto, você usará o JavaScript Console do navegador para exibi-lo.

1. Abra o site Luma
1. Abra as Ferramentas do desenvolvedor do seu navegador
1. Vá até a guia Rede
1. No campo de filtro, digite `b/ss` o que limitará o que você vê às solicitações do Adobe Analytics

   ![Abra as Ferramentas do desenvolvedor e filtre a guia Rede para mostrar somente as solicitações do Analytics](images/aam-openTheJSConsole.png)

1. Clique no link **[!UICONTROL LOGIN]** no canto superior direito do site

   ![Clique em Login no menu de navegação superior](images/idservice-loginNav.png)

1. Digite `test@adobe.com` como nome de usuário
1. Digite `test` como senha
1. Clique no botão **[!UICONTROL LOGIN (LOGIN)]**

   ![Digite as credenciais e clique em logon](images/idservice-login.png)

1. Ele deve retornar à página inicial, que também acionará um sinal que você pode ver nas Ferramentas do desenvolvedor. Se você for levado para a página de informações da conta, clique no logotipo WE.RETAIL para retornar à página inicial.
1. Clique na solicitação e selecione a guia Cabeçalhos
1. Role para baixo até ver alguns parâmetros aninhados
   1. cid - este é o delimitador padrão para a parte ID do cliente da solicitação
   1. crm_id - Este é o código de integração personalizado, que você especificou na lição Serviço de identidade
   1. id - O valor da ID do cliente proveniente do seu elemento `Email (Hashed)` de dados
   1. as - O Estado de autenticação, com "1" que significa conectado
   ![Validação da ID do cliente do Analytics](images/integrations-analyticsCustomerIDValidation.png)

[Próximo "Publique sua propriedade" &gt;](publish.md)