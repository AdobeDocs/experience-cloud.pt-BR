---
title: Integrar seu aplicativo
description: Saiba como integrar um novo aplicativo às implantações de experiência do Adobe para começar a criar e gerenciar sinalizadores de recursos.
exl-id: d88c27a5-f490-4504-9764-5e4ce98fdf20
source-git-commit: fcb1d36fc92b3954a902d818a98f579672c577e9
workflow-type: tm+mt
source-wordcount: '185'
ht-degree: 2%

---

# Integrar seu aplicativo {#onboard-your-application}

Você deve ter a função de **Administrador** para adicionar um novo aplicativo. Entre em contato com o administrador se precisar verificar ou atualizar sua função.

## Adicionar um novo aplicativo {#add-application}

1. Faça logon no console Implantações de experiência e navegue até **Implantação de experiência > Aplicativos**.

   >[!NOTE]
   >
   >Se o botão **Novo Aplicativo** não estiver visível, verifique se você tem a função de **Administrador do Floodgate**.

2. Selecione **Novo Aplicativo**.

3. Selecione a **plataforma** que corresponde ao seu tipo de aplicativo (Web ou móvel).

4. Forneça as seguintes informações:

   | Campo | Descrição |
   |---|---|
   | **ID do aplicativo** | Um identificador exclusivo usado ao chamar Implantações de experiência do seu código. Use a ID de cliente do aplicativo. |
   | **TTL** | O intervalo de pesquisa (em segundos) para atualizar o cache por aplicativo. Aplicável somente aos SDKs do lado do servidor. |

5. Selecione **Adicionar**. Seu aplicativo agora está registrado e pronto para a configuração do sinalizador de recurso.

## O que vem a seguir {#next-steps}

Depois que o aplicativo for integrado, você poderá começar a criar sinalizadores de recursos:

* [Criar o primeiro sinalizador de recurso](../feature-flags/create-your-first-feature-flag.md)
* [Integrar implantações de experiência no seu aplicativo](../integrate/integrating-in-your-app.md)

## Consulte também {#see-also}

* [Gerenciar aplicativos](manage-applications.md)
* [Fazer logon no console](../console/log-in-to-the-console.md)
