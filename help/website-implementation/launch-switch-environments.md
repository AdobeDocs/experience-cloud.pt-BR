---
title: Alternar os ambientes de inicialização com o Adobe Experience Cloud Debugger
description: Saiba como usar o Experience Cloud Debugger para carregar códigos incorporados do Launch diferentes. Esta lição é parte do tutorial Implementação da Experience Cloud em sites com lançamento.
seo-description: null
seo-title: Alternar os ambientes de inicialização com o Adobe Experience Cloud Debugger
solution: Experience Cloud
translation-type: tm+mt
source-git-commit: 79d5274d09d66b80a49aba5db3e0a997d0f0ff61

---


# Alternar ambientes de inicialização com o Experience Cloud Debugger

In this lesson you will use the [Adobe Experience Cloud Debugger extension](https://chrome.google.com/webstore/detail/adobe-experience-cloud-de/ocdmogmohccmeicdhlhhgepeaijenapj) to replace the Launch property hardcoded on the [Luma demo site](https://luma.enablementadobe.com/content/luma/us/en.html) with your own property.

Essa técnica é chamada de ambiente switching e será útil mais tarde, quando você trabalhar com o Launch em seu próprio site. Você poderá carregar seu site de produção em seu navegador, mas com seu ambiente de *desenvolvimento* Launch. Isso permite que você faça e valide com confiança as alterações do Launch, independentemente das versões regulares do código.  Afinal, essa separação das versões de tag de marketing das versões regulares de código é um dos principais motivos pelos quais os clientes usam o Launch em primeiro lugar!

## Objetivos de aprendizagem

No final desta lição, você poderá:

* Use o Depurador para carregar um ambiente alternativo de inicialização
* Use o Depurador para validar se você carregou um ambiente alternativo de inicialização

## Obtenha o URL de seu ambiente de desenvolvimento

1. In your Launch property, open the `Environments` page

1. In the **[!UICONTROL Development]** row, click the Install icon ![Install icon](images/launch-installIcon.png) to open the modal

1. Clique no ícone Copiar ícone ![Copiar ícone](images/launch-copyIcon.png) para copiar o código incorporado para a área de transferência

1. Click **[!UICONTROL Close]** to close the modal

   ![Ícone Instalar](images/launch-copyInstallCode.png)

## Substitua o URL de inicialização no site de demonstração de luma

1. Open the [Luma demo site](https://luma.enablementadobe.com/content/luma/us/en.html) in your Chrome browser

1. Abra a extensão [do](https://chrome.google.com/webstore/detail/adobe-experience-cloud-de/ocdmogmohccmeicdhlhhgepeaijenapj) Experience Cloud Debugger clicando no ícone ![Depurador](images/icon-debugger.png)

   ![Clique no ícone do Depurador](images/switchEnvironments-openDebugger.png)

1. Observe que a propriedade Launch implementada atualmente é mostrada na guia Resumo

   ![Ambiente de inicialização mostrado no Debugger](images/switchEnvironments-debuggerOnWeRetail-prod.png)

1. Vá para a guia Ferramentas

1. Role até a seção **[!UICONTROL Substituir código incorporado de inicialização]**

1. Verifique se a guia Chrome com o site Luma está em foco atrás do Depurador (não a guia com este tutorial ou a guia com a interface de inicialização).  Cole o código incorporado que está na área de transferência no campo de entrada

1. Alterne para o recurso "Aplicar em luma.ativlementadobe.com" para que todas as páginas do site Luma mapeiem para a propriedade Iniciar

1. Clique no botão **[!UICONTROL Salvar]**

   ![Ambiente de inicialização mostrado no Debugger](images/switchEnvironments-debugger-save.png)

1. Recarregue o site Luma e verifique a guia Summary (Resumo) do Depurador. Na seção Launch (Inicialização), agora você deve ver que sua propriedade de desenvolvimento está sendo usada. Confirme se o Nome da propriedade corresponde ao seu e se o Ambiente indica "desenvolvimento".

   ![Ambiente de inicialização mostrado no Debugger](images/switchEnvironments-debuggerOnWeRetail.png)

>[!NOTE] O Depurador salvará essa configuração e substituirá os códigos incorporados do Launch sempre que você voltar ao site Luma. Isso não afetará outros sites visitados em outras guias abertas. To stop the Debugger from replacing the embed code, click the **[!UICONTROL Remove]** button next to the embed code in the Tools tab of the Debugger.

À medida que você continua o tutorial, usará essa técnica de mapear o site Luma para sua própria propriedade Launch para validar sua implementação do Launch. Ao começar a usar o Launch no site de produção, você pode usar essa mesma técnica para validar as alterações.

[Próximo "Adicionar o Adobe Experience Platform Identity Service" &gt;](id-service.md)