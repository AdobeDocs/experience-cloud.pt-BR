---
title: Introdução aos sinalizadores
description: Saiba como o Flags no Adobe Target fornece um sistema de versão controlada para implantar recursos progressivamente para públicos-alvo direcionados.
hide: true
exl-id: befe7899-096d-4f74-a5a2-35b1fc3cbc58
source-git-commit: b3e13a42c19eb7b8b7d5d402bf9a56f89f573044
workflow-type: tm+mt
source-wordcount: '373'
ht-degree: 0%

---

# Introdução aos sinalizadores {#introduction}

>[!AVAILABILITY]
>
>O sinalizador está atualmente no Beta e está disponível para clientes do Adobe Target. Entre em contato com seu representante da Adobe para solicitar acesso.

Os sinalizadores no Adobe Target são um sistema de versão controlada que permite que as equipes implantem recursos por todo o processo de produção, mantendo controle preciso sobre quem os vê e quando. Um recurso pode estar em produção e ser invisível para os usuários finais — e ser ativado progressivamente para um público-alvo — sem nenhuma reimplantação.

## Do desenvolvimento à produção {#dev-to-prod}

Os sinalizadores oferecem suporte à jornada completa de um recurso desde seu estágio de desenvolvimento mais antigo até a disponibilidade geral:

1. **Teste de desenvolvedor** — um desenvolvedor cria um sinalizador de recurso, implanta o código em qualquer ambiente e testa somente em relação à própria sessão. Nenhum outro usuário é afetado e nenhuma ramificação é necessária.

2. **Visualização direcionada** — o proprietário de um produto vincula um público-alvo ao sinalizador de recurso, disponibilizando o recurso para um subconjunto definido de usuários (por exemplo, participantes beta ou uma região específica) para validação e feedback.

3. **Implantação gradual** — o recurso é progressivamente aberto para um público-alvo maior — 1%, 10%, 50%, 100% — com a capacidade de pausar, ajustar ou desativar o recurso em qualquer etapa.

4. **Disponibilidade geral** — Quando a validação for concluída, o recurso será disponibilizado para todos os usuários.

## Principais recursos {#capabilities}

Sinalizadores é uma plataforma de gerenciamento de recursos que fornece:

* **Sinalizadores de recursos** — Ative ou desative qualquer recurso no tempo de execução para um público-alvo direcionado, sem reimplantar o código.

* **Direcionamento de público-alvo** — Controle quem vê um recurso usando dados de perfil de usuário, regras baseadas em porcentagem, endereço de email, domínio de email, endereço IP ou atributos contextuais.

* **Grupos de recursos** — agrupe vários sinalizadores de recursos relacionados entre aplicativos e gerencie-os como uma única unidade, garantindo que o mesmo público veja uma experiência consistente.

* **Versões** — coordene grandes implantações entre equipes, agrupando sinalizadores de recursos de várias equipes e aplicativos em um único evento de versão.

* **Implantações graduais** — crie uma fase de entrega de recursos de forma incremental para reduzir riscos, obter feedback e gerenciar a carga de back-end.

* **Interruptor de eliminação** — Desative qualquer recurso imediatamente se um problema for detectado, sem uma alteração de código ou reimplantação.

* **Suporte ao AEP SDK** — os sinalizadores são implantados por meio do AEP Web SDK e do AEP Mobile SDK, permitindo uma avaliação consistente dos sinalizadores em aplicativos móveis e da Web.

<!-- -->
