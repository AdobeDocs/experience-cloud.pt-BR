---
title: Visão geral dos ambientes
description: Saiba mais sobre os ambientes de Preparo e Produção em Implantações de experiência do Adobe e quando usar cada um deles.
source-git-commit: 9bfe0e55e89c1d7fbd77cde63831a6a186820e24
workflow-type: tm+mt
source-wordcount: '204'
ht-degree: 4%

---


# Visão geral dos ambientes {#environments}

As Implantações de experiência fornecem ambientes separados para que você possa validar seus sinalizadores de recursos antes de promover alterações para seus usuários ativos.

## Ambientes disponíveis {#available-environments}

| Ambiente | Finalidade |
|---|---|
| **Estágio** | Teste e validação. Use esse ambiente para configurar e testar sinalizadores de recursos antes de ativá-los na produção. |
| **Produção** | Implantações em tempo real. Sinalizadores de recursos configurados aqui são avaliados em relação à sua base de usuários real. |

>[!IMPORTANT]
>
>As alterações feitas no Preparo não são transferidas automaticamente para a Produção. Sinalizadores de recursos e regras de público-alvo devem ser configurados separadamente em cada ambiente.

## Seleção de um ambiente {#selecting}

Depois de fazer logon no console Implantações de experiência, selecione o ambiente no alternador de ambientes na parte superior da interface. Verifique se você está trabalhando no ambiente correto antes de criar ou modificar sinalizadores de recursos.

## Práticas recomendadas {#best-practices}

Siga estas recomendações para evitar erros de configuração e proteger o público-alvo da produção:

* Sempre crie e teste primeiro os sinalizadores de recursos no **Estágio**.
* Valide as regras de público-alvo, as implantações percentuais e a lógica de direcionamento no Preparo antes de replicar na Produção.
* Use o [fluxo de trabalho entre ambientes](../cross-environment/cross-environment-concept.md) para exibir e gerenciar o status do sinalizador entre ambientes.

## Consulte também {#see-also}

* [Fazer logon no console](log-in-to-the-console.md)
* [Associar ambientes a um aplicativo](../cross-environment/associate-environments.md)
* [Exibir sinalizadores de recursos entre ambientes](../cross-environment/view-feature-flags-across-environments.md)
