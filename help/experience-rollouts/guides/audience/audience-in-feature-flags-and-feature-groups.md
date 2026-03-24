---
title: Público-alvo em sinalizadores e grupos de recursos
description: Saiba como definir critérios de público-alvo para sinalizadores de recursos e grupos de recursos em implantações do Adobe Experience usando atributos de perfil, segmentos e a calculadora de público-alvo.
source-git-commit: 3f3f7145b3c58dc721cbeb850e9e8571e3255bb1
workflow-type: tm+mt
source-wordcount: '342'
ht-degree: 0%

---


# Público-alvo em sinalizadores e grupos de recursos {#audience-overview}

As Implantações de experiência fornecem direcionamento de público-alvo avançado para sinalizadores de recursos e grupos de recursos. Você pode combinar atributos de perfil, variáveis de contexto e segmentos de público-alvo para controlar com precisão quais usuários recebem um recurso.

## Regras de perfil {#profile-rules}

As regras de perfil permitem direcionar os usuários com base em atributos como país, domínio de email, tipo de conta, ID de usuário e muito mais. Você pode combinar vários atributos usando operadores AND/OR e criar uma lógica aninhada para cenários complexos de direcionamento.

Para adicionar regras de perfil, vá para a guia **Público-alvo** de um sinalizador ou grupo de recursos e adicione condições em **Perfil**.

Você pode salvar um conjunto de regras de público-alvo como um **Público-alvo** reutilizável para uso em vários sinalizadores e grupos.

Para direcionamento baseado em contexto (por exemplo, direcionamento pelo idioma ativo do usuário ou tipo de cliente), consulte [Usar contexto nas regras de público-alvo](using-context-in-audience-rules.md).

## Segmentos {#segments}

Sinalizadores de recursos e grupos de recursos são compatíveis com segmentos de público-alvo. Os segmentos permitem:

* Usar uma única definição de público-alvo predefinida em vários sinalizadores e grupos de recursos
* Inclua **critérios baseados em eventos** no direcionamento de público-alvo — algo não possível somente com as regras de perfil

Para usar um segmento, vá para a guia **Público-alvo** e selecione um ou mais segmentos da lista. É possível combinar vários segmentos usando operadores AND/OR e adicionar filtros de perfil ou contexto ao lado deles.

>[!NOTE]
>
>Você precisa da função de **Gerente de teste** ou superior para criar segmentos de público-alvo.

## Calculadora de público-alvo {#audience-calculator}

Depois de definir seus critérios de público, selecione **Calcular** na barra inferior para obter uma contagem estimada de usuários que se qualificam. Isso ajuda a validar o alcance do direcionamento antes de ativar o recurso.

>[!NOTE]
>
>A calculadora de público-alvo não retorna um valor quando as variáveis de contexto são incluídas nos critérios, pois os valores de contexto são determinados no tempo de execução e não podem ser previstos antecipadamente.

## Consulte também {#see-also}

* [Usar contexto nas regras de público](using-context-in-audience-rules.md)
* [Adicionar regras de porcentagem aos critérios de público](adding-percentage-rules.md)
* [Regras complexas de público](complex-rules.md)
* [Criar o primeiro sinalizador de recurso](../feature-flags/create-your-first-feature-flag.md)
