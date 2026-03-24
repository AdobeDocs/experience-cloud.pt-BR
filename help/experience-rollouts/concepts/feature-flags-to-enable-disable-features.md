---
title: Sinalizadores de recursos para ativar e desativar recursos
description: Saiba como os sinalizadores de recursos nas Implantações de experiência permitem controlar a disponibilidade de recursos, gerenciar dependências e reduzir o risco de implantação.
source-git-commit: 1c8fd9b42d08f657b4e6b16efae86faa04d15565
workflow-type: tm+mt
source-wordcount: '405'
ht-degree: 0%

---


# Sinalizadores de recursos para ativar e desativar recursos {#feature-flags}

Os sinalizadores de recursos permitem ativar ou desativar os recursos do aplicativo no tempo de execução sem reimplantar o código. Eles também separam as implantações de código da disponibilidade de recursos — o novo código pode ser implantado na produção por meio de um sinalizador e ativado somente quando você estiver pronto.

Essa prática reduz significativamente o risco. Os desenvolvedores podem criar com agilidade e confiança, enquanto as equipes de produtos mantêm o controle sobre o tempo e o público-alvo de cada versão de recurso.

## Gerenciar dependências durante o desenvolvimento {#manage-dependencies}

Os sinalizadores de recursos ajudam a gerenciar dependências ao testar ciclos de desenvolvimento rápidos. Os desenvolvedores gastam menos tempo resolvendo conflitos e refatoração de mesclagem e mais tempo fornecendo recursos.

Como a disponibilidade de recursos é controlada fora do código, vários recursos podem ser desenvolvidos em paralelo, sem ramificações complexas. Os recursos individuais podem ser rolados para frente ou para trás independentemente, sem afetar outros recursos em andamento.

## Implantações escuras {#dark-deployments}

Como as decisões de ativação e desativação ficam fora da base de código, você pode implantar código na produção, mantendo o recurso invisível para os usuários finais. Isso é chamado de **implantação escura**.

As implantações escuras permitem que você envie o código com segurança para produção, teste-o no ambiente ativo em relação a condições reais e entre no ar quando desejar — e não quando a programação de implantação o obriga a fazê-lo.

## Implantação gradual {#gradual-rollout}

Quando estiver pronto para o lançamento, você poderá usar um sinalizador de recurso para executar uma **implantação gradual**: abrir o recurso para 1% dos usuários, medir o feedback e o desempenho e aumentar progressivamente.

Essa abordagem contínua oferece controle mais rígido sobre a experiência fornecida e um loop de comentários mais rápido com usuários reais, para que suas equipes possam responder rapidamente antes de um lançamento completo.

## Eliminar switch {#kill-switch}

Se uma versão não for aprovada como planejado (feedback desfavorável, um erro ou um problema de desempenho), você pode desativar o recurso imediatamente usando o sinalizador de recurso como **kill switch**. Nenhuma alteração de código ou reimplantação é necessária.

## Ciclo de vida do sinalizador de recurso {#lifecycle}

Um sinalizador de recurso nas Implantações de experiência segue este ciclo de vida típico:

1. Um desenvolvedor cria um sinalizador de recurso e o testa de forma isolada, sem expô-lo a outros usuários.
2. Um proprietário de produto vincula um público-alvo ao sinalizador, tornando o recurso visível para um conjunto definido de usuários externos.
3. O sinalizador é opcionalmente adicionado a um [grupo de recursos](feature-groups-to-control-multiple-features.md) para ser gerenciado junto com sinalizadores relacionados.
4. O sinalizador é adicionado opcionalmente a uma [versão](release-management.md) para coordenação entre equipes.
