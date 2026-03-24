---
title: Recursos, grupos de recursos e versões
description: Saiba mais sobre as diferenças entre sinalizadores de recursos, grupos de recursos, grupos de recursos entre equipes e versões nas implantações da Adobe Experience e quando usar cada um.
source-git-commit: d311efb995b20ffc17370d68d57dd84a8605896c
workflow-type: tm+mt
source-wordcount: '347'
ht-degree: 2%

---


# Recursos, grupos de recursos e versões {#features-feature-groups-releases}

As implantações de experiência fornecem quatro artefatos para gerenciar implantações de recursos. Escolher a opção certa depende do escopo da implantação, do número de equipes envolvidas e dos recursos de direcionamento de público-alvo necessários.

## Os quatro artefatos {#artifacts}

**Sinalizador de recurso**
A unidade mais atômica. Controla um único recurso para um único aplicativo, de propriedade de uma equipe. Pode ser ativado ou desativado para um público-alvo definido.

**Grupo de recursos**
Uma coleção de sinalizadores de recursos pertencentes à mesma equipe. Permite o gerenciamento de vários sinalizadores em vários aplicativos em uma equipe como uma única unidade.

**Grupo de recursos entre equipes**
Estende os recursos do grupo de recursos em várias equipes e aplicativos. Autoatendimento e compatível com critérios avançados de público-alvo, mas não compatível com armazenamento em cache.

**Versão**
Projetado para implantações grandes e coordenadas em várias equipes e aplicativos. Usa direcionamento de público com base em token de autenticação. Oferece suporte ao armazenamento em cache no servidor SDK.

## Comparação {#comparison}

| | Sinalizador de recurso | Grupo de recursos | Grupo de recursos entre equipes | Versão |
|---|---|---|---|---|
| **Função necessária para gerenciar a audiência** | Proprietário da versão do produto | Proprietário da versão do produto | Administrador de recursos | Gerenciador de versão |
| **Aplicativos** | Solteiro | Múltiplos (mesma equipe) | Múltiplo (equipe cruzada) | Múltiplo (equipe cruzada) |
| **Equipes** | Solteiro | Solteiro | Entre equipes | Entre equipes |
| **Critérios avançados de público-alvo** | ✓ | ✓ | ✓ | Limitado |
| **porcentagem de implantação** | Combinado com qualquer critério de público-alvo | Combinado com qualquer critério de público-alvo | Combinado com qualquer critério de público-alvo | Combinado com critérios de público-alvo fixos |
| **Teste A/B** | ✓ | ✓ | ✗ | ✗ |
| **Armazenamento em cache no servidor SDK** | Somente sinalizadores padrão de ligar/desligar | Sem armazenamento em cache | Sem armazenamento em cache | Todas as versões armazenadas em cache localmente |
| **Autoatendimento** | ✓ | ✓ | ✓ | Requer solicitação de suporte |
| **Trilha de auditoria** | ✓ | ✓ | ✓ | ✓ |

## Quando usar cada {#when-to-use}

| Cenário | Usar |
|---|---|
| Teste ou implantação de um único recurso para um aplicativo | **Sinalizador de recurso** |
| Coordenação de vários recursos na mesma equipe, entrando em funcionamento ao mesmo tempo | **Grupo de recursos** |
| Coordenação de recursos entre aplicativos em diferentes equipes, com direcionamento avançado | **Grupo de recursos entre equipes** |
| Lançamento coordenado em várias equipes, com cache em nível de SDK | **Versão** |

## Consulte também {#see-also}

* [Criar o primeiro sinalizador de recurso](create-your-first-feature-flag.md)
* [Criar um grupo de recursos](create-a-feature-group.md)
* [Criar um grupo de recursos entre equipes](create-cross-team-feature-group.md)
* [Versões e grupos de recursos entre equipes](releases-and-cross-team-feature-groups.md)
