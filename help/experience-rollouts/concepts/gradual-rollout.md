---
title: Implantação gradual
description: Saiba como as implantações graduais em implantações de experiência permitem que você coloque a entrega de recursos em produção de forma segura, com feedback em tempo real e risco mínimo.
source-git-commit: 1c8fd9b42d08f657b4e6b16efae86faa04d15565
workflow-type: tm+mt
source-wordcount: '248'
ht-degree: 2%

---


# Implantação gradual {#gradual-rollout}

A implantação gradual coloca um novo recurso em produção de forma incremental, em vez de habilitá-lo para todos os usuários de uma só vez. Essa abordagem reduz o risco, ajuda a gerenciar a carga de backend e cria um loop de feedback apertado antes do lançamento completo.

## Benefícios {#benefits}

**Rede de segurança**
Ao lançar para um pequeno público-alvo primeiro, você pode rastrear o feedback e monitorar o comportamento na produção antes de expandir. Se ocorrerem problemas, o impacto será limitado e o recurso poderá ser desativado imediatamente, sem a necessidade de uma alteração de código ou reimplantação.

**Gerenciamento de carga de back-end**
Abrir um recurso para todos os usuários simultaneamente pode causar picos repentinos na carga do servidor. Uma implantação gradual distribui o aumento do tráfego ao longo do tempo, permitindo que a infraestrutura seja dimensionada sem problemas.

**Feedback em tempo real**
Cada fase da implantação exibe o feedback de usuários reais. As equipes podem agir com base nesse feedback — refinando a experiência, corrigindo casos de borda ou ajustando mensagens — antes da próxima fase.

## Como funciona {#how-it-works}

As Implantações de experiência fornecem regras de direcionamento granulares para aumentar a exposição do usuário passo a passo. Uma implantação gradual típica pode seguir esse padrão:

1. Habilitar o recurso para **1%** dos usuários
2. Monitorar feedback e métricas de desempenho
3. Expandir para **10%**, depois **25%** e depois **50%**
4. Atingir **100%** quando a confiança for estabelecida

Em cada etapa, uma única ação pode pausar a implantação ou desativar o recurso totalmente se algo der errado.

## Consulte também {#see-also}

* [Sinalizadores de recursos para ativar e desativar recursos](feature-flags-to-enable-disable-features.md)
* [Gerenciamento de versão](release-management.md)
