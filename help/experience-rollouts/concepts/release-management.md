---
title: Gerenciamento de versões em implantações de experiência
description: Saiba como o gerenciamento de versões no Experience Rollouts coordena a entrega de recursos de várias equipes por meio de implantações escuras, testes de produção e implantações graduais.
source-git-commit: 1c8fd9b42d08f657b4e6b16efae86faa04d15565
workflow-type: tm+mt
source-wordcount: '290'
ht-degree: 1%

---


# Gerenciamento de versões em implantações de experiência {#release-management}

Uma versão principal típica envolve várias equipes e vários aplicativos, cada um com suas próprias dependências e linhas de tempo de implantação. As Implantações de experiência fornecem um modelo de gerenciamento de versões que permite que as equipes trabalhem de modo independente e, ao mesmo tempo, forneçam uma versão coordenada e controlada aos usuários finais.

## Principais recursos {#capabilities}

### Implantações escuras {#dark-deployments}

As equipes não precisam mais cronometrar a implantação do código com uma data de ativação específica. O código pode ser implantado na produção por trás de sinalizadores de recursos a qualquer momento. Os usuários finais não verão nenhuma alteração até que a versão seja ativada. As equipes podem se destacar em seu próprio ritmo, confiantes de que nada será exposto prematuramente.

### Testes em produção {#testing-in-production}

Quando o código for implantado na produção — escuro, as implantações de experiência podem abrir os recursos para testadores internos e equipes de controle de qualidade. Isso permite testes completos no ambiente de produção e dados reais de produção, sem o risco de expor as alterações aos usuários finais.

### Implantação gradual {#gradual-rollout}

Quando uma versão está pronta para ser ativada, ela não precisa ser all-or-Nothing. As implantações de experiência permitem controlar a implantação progressivamente, começando com uma pequena porcentagem de usuários, monitorando o feedback e o desempenho e expandindo o público-alvo ao longo do tempo. Isso reduz a sobrecarga dos sistemas de back-end e dá às equipes tempo para responder a quaisquer problemas antes da exposição completa.

### Ativação coordenada {#coordinated-activation}

Várias equipes desenvolvem recursos de forma independente, cada uma atrás de seus próprios sinalizadores de recursos. Quando todas as equipes estiverem prontas, as Implantações de experiência fornecerão um único ponto de controle para ativar todos os sinalizadores entre equipes e aplicativos simultaneamente — ou gradualmente — para que a versão entre em funcionamento como uma experiência coesa.

## Consulte também {#see-also}

* [Conceito de gerenciamento de versões](concept-of-release-management.md)
* [Grupos de recursos para controlar vários recursos](feature-groups-to-control-multiple-features.md)
* [Implantação gradual](gradual-rollout.md)
