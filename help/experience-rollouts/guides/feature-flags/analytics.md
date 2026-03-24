---
title: Analytics
description: Saiba como ativar e usar o painel de análise integrado em Implantações da Adobe Experience para rastrear o desempenho do sinalizador de recursos e medir o impacto da implantação.
source-git-commit: d311efb995b20ffc17370d68d57dd84a8605896c
workflow-type: tm+mt
source-wordcount: '297'
ht-degree: 1%

---


# Analytics {#analytics}

As Implantações de experiência fornecem análise integrada para sinalizadores de recursos, grupos de recursos, grupos de recursos entre equipes e versões. Use o painel do analytics para entender quantos usuários estão participando da implantação e como a variante e os grupos de controle se comparam.

## Habilitar análise {#enable}

O Analytics deve ser habilitado em dois níveis:

1. **Nível de aplicativo** — Contate o suporte de Implantações de Experiência para habilitar a análise para seu aplicativo.
2. **Nível de sinalizador de recurso** — Depois que a análise estiver habilitada para o seu aplicativo, marque a caixa de seleção **Habilitar análise** na guia **Detalhes Básicos** de cada sinalizador de recurso que você deseja rastrear.

>[!NOTE]
>
>Por padrão, o Analytics pode ser ativado para até 20 sinalizadores de recursos por aplicativo. Entre em contato com o suporte se precisar aumentar esse limite.

## Exibir o painel de análise {#dashboard}

Quando a análise estiver ativada, todos os sinalizadores de recursos, grupos de recursos e versões do aplicativo iniciarão o rastreamento dos dados. Acesse o painel selecionando **Resultados** no sinalizador de recurso, grupo de recursos ou versão que você deseja analisar.

O painel de controle exibe:

* **Participantes** — Número total de usuários qualificados para o recurso (variante + grupo de controle combinado)
* **Grupo de controle** — Número de usuários atribuídos ao grupo de controle (usuários que receberam a experiência padrão)
* **Gráfico de nível de dia** — Gráficos de linha diários que mostram a inscrição na variante e no grupo de controle ao longo do tempo; marcadores indicam quando a configuração do sinalizador de recurso foi atualizada
* **Análise de nível de variante** — Contagem cumulativa de usuários inscritos no grupo de controle e cada variante

Para grupos de recursos e versões, selecione o menu suspenso **Resultados** para escolher um aplicativo e exibir análises para esse aplicativo. O Analytics só está disponível para aplicativos que o habilitam.

## Consulte também {#see-also}

* [Criar o primeiro sinalizador de recurso](create-your-first-feature-flag.md)
* [Teste A/B com sinalizadores de recursos](a-b-testing.md)
* [Criar um grupo de recursos](create-a-feature-group.md)
