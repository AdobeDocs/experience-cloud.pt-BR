---
title: Definir um grupo de recursos para implantação gradual
description: Saiba como configurar uma implantação gradual com base em porcentagem para um grupo de recursos em implantações de experiência do Adobe.
source-git-commit: 9bfe0e55e89c1d7fbd77cde63831a6a186820e24
workflow-type: tm+mt
source-wordcount: '166'
ht-degree: 3%

---


# Definir um grupo de recursos para implantação gradual {#gradual-rollout-feature-group}

A porcentagem de implantação de um grupo de recursos está configurada na guia **Detalhes Básicos**. Você pode ajustar esse valor para cima ou para baixo a qualquer momento, conforme o progresso da implantação.

## Como funciona {#how-it-works}

Ao definir uma porcentagem de implantação — por exemplo, 60% — essa porcentagem do público-alvo definido é exposta ao grupo de recursos. Os 40% restantes são colocados no **grupo de controle**, que recebe o comportamento padrão.

Se você tiver configurado várias variantes (para testes A/B), a porcentagem de exposição será distribuída igualmente entre as variantes. Por exemplo, 60% de exposição com três variantes resulta em 20% por variante, com 40% no grupo de controle.

É possível aumentar ou diminuir a porcentagem a qualquer momento para expandir, reduzir ou pausar a implantação.

## Consulte também {#see-also}

* [Criar um grupo de recursos](create-a-feature-group.md)
* [Teste A/B com sinalizadores de recursos](a-b-testing.md)
* [Implantação gradual](../../concepts/gradual-rollout.md)
