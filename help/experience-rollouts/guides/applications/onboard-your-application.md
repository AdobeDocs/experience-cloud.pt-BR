---
title: Integrar seu aplicativo
description: Saiba como integrar um novo aplicativo às implantações de experiência do Adobe para que sua equipe possa começar a criar e gerenciar sinalizadores de recursos.
source-git-commit: 9bfe0e55e89c1d7fbd77cde63831a6a186820e24
workflow-type: tm+mt
source-wordcount: '225'
ht-degree: 1%

---


# Integrar seu aplicativo {#onboard-your-application}

Você deve ter a função de **Administrador** para adicionar um novo aplicativo. Consulte [Funções do usuário](../teams/user-roles.md) se precisar verificar sua função ou solicitá-la ao administrador de equipe.

## Adicionar um novo aplicativo {#add-application}

1. Faça logon no console Implantações de Experiência e navegue até **Administrador > Aplicativos**.

   >[!NOTE]
   >
   >Se o botão **Novo Aplicativo** não estiver visível, verifique se você está na equipe correta e se tem a função de **Administrador**.

2. Selecione **Novo Aplicativo**.

3. Selecione o **canal** que corresponde ao seu tipo de aplicativo (Web, móvel, desktop ou serviço).

4. Forneça as seguintes informações:

   | Campo | Descrição |
   |---|---|
   | **ID do aplicativo** | Um identificador exclusivo usado ao chamar Implantações de experiência do seu código. Use a ID de cliente do aplicativo. |
   | **TTL** | O intervalo de pesquisa (em segundos) para atualizar o cache por aplicativo. Aplicável somente aos SDKs do lado do servidor. |
   | **Equipe** | A equipe que será proprietária e gerenciará este aplicativo. Somente membros desta equipe podem criar e editar sinalizadores de recursos para ela. |

5. Selecione **Adicionar**. Seu aplicativo agora está registrado e pronto para a configuração do sinalizador de recurso.

## O que vem a seguir {#next-steps}

Depois que o aplicativo for integrado, a equipe poderá começar a criar sinalizadores de recursos:

* [Criar o primeiro sinalizador de recurso](../feature-flags/create-your-first-feature-flag.md)
* [Integrar implantações de experiência no seu aplicativo](../integrate/integrating-in-your-app.md)

## Consulte também {#see-also}

* [Gerenciar aplicativos](manage-applications.md)
* [Funções do usuário](../teams/user-roles.md)
* [Fazer logon no console](../console/log-in-to-the-console.md)
