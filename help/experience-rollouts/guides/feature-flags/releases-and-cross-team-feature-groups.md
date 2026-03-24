---
title: Versões e grupos de recursos entre equipes
description: Saiba mais sobre a diferença entre versões e grupos de recursos entre equipes em implantações de experiência do Adobe e quando usar cada um deles para implantações coordenadas de várias equipes.
source-git-commit: d311efb995b20ffc17370d68d57dd84a8605896c
workflow-type: tm+mt
source-wordcount: '339'
ht-degree: 1%

---


# Versões e grupos de recursos entre equipes {#releases-and-cross-team}

As versões do e os grupos de recursos entre equipes oferecem suporte a implantações coordenadas em várias equipes e aplicativos. A escolha certa depende dos requisitos de armazenamento em cache, das necessidades de direcionamento de público-alvo e de quanto controle você deseja sobre o processo.

## Grupos de recursos entre equipes {#cross-team-feature-groups}

Um grupo de recursos entre equipes permite agrupar sinalizadores de recursos de aplicativos de propriedade de equipes diferentes e gerenciá-los com critérios avançados de público-alvo.

Principais características:

* **Autoatendimento** — Nenhuma solicitação de suporte é necessária para criar uma
* **Direcionamento de público-alvo avançado** — oferece suporte ao conjunto completo de critérios de público-alvo (atributos de perfil, variáveis de contexto, implantação percentual)
* **Sem limite** no número que você pode criar
* **Nenhum armazenamento em cache** — as avaliações de sinalizador de recursos exigem uma chamada de API; não há suporte para armazenamento em cache no nível da SDK

Para obter instruções de criação passo a passo, consulte [Criar um grupo de recursos entre equipes](create-cross-team-feature-group.md).

## Versões {#releases}

Uma versão do foi projetada para inicializações grandes e coordenadas em que o armazenamento em cache no nível do SDK é necessário. As versões usam direcionamento de público-alvo com base em token de autenticação.

Principais características:

* **Requer uma solicitação de suporte** — as versões não são totalmente automatizadas; entre em contato com o suporte a Implantações de Experiência para criar uma
* **Cache do SDK** — Todos os dados de versão são armazenados em cache localmente no servidor SDK, reduzindo as chamadas de API
* **Critérios de público-alvo limitados** — as regras de público-alvo são baseadas em tokens de autenticação (país, email, ID de usuário, porcentagem etc.)
* **Versões ativas limitadas** — Um número limitado de versões ativas pode existir de cada vez; planeje fechar ou incluir versões de linha de base dentro de três meses

## Comparação {#comparison}

| | Grupo de recursos entre equipes | Versão |
|---|---|---|
| Autoatendimento | ✓ | Requer solicitação de suporte |
| Critérios avançados de público-alvo | ✓ | Limitado |
| Teste AB | ✗ | ✗ |
| Cache do SDK | ✗ | ✓ |
| Limite ativo | Sem limite | Limitado |

## Recomendação {#recommendation}

Se o seu caso de uso envolver direcionamento avançado de público-alvo e gerenciamento de autoatendimento, use um **grupo de recursos entre equipes**. Se seus serviços de back-end exigirem cache em nível de SDK e os critérios mais simples de público-alvo das versões forem suficientes, use uma **versão**.

## Consulte também {#see-also}

* [Recursos, grupos de recursos e versões](features-feature-groups-releases.md)
* [Criar um grupo de recursos entre equipes](create-cross-team-feature-group.md)
* [Solicitar uma versão](request-a-release.md)
