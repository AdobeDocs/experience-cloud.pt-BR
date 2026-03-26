---
title: Recursos e grupos de recursos
description: Saiba mais sobre as diferenças entre sinalizadores de recursos e grupos de recursos em implantações de experiência do Adobe e quando usar cada um.
source-git-commit: c654ca1507abcefcff84cef9f99830042939805d
workflow-type: tm+mt
source-wordcount: '189'
ht-degree: 4%

---


# Recursos e grupos de recursos {#features-feature-groups}

As implantações de experiência fornecem dois artefatos para gerenciar implantações de recursos. Escolher a opção certa depende do escopo da implantação e do número de recursos envolvidos.

## Os dois artefatos {#artifacts}

**Sinalizador de recurso**
A unidade mais atômica. Controla um único recurso para um único aplicativo. Pode ser ativado ou desativado para um público-alvo definido.

**Grupo de recursos**
Uma coleção de sinalizadores de recursos pertencentes à mesma equipe. Permite gerenciar vários sinalizadores em vários aplicativos como uma única unidade.

## Comparação {#comparison}

| | Sinalizador de recurso | Grupo de recursos |
|---|---|---|
| **Função necessária para gerenciar a audiência** | Proprietário da versão do produto | Proprietário da versão do produto |
| **Aplicativos** | Solteiro | Múltiplos (mesma equipe) |
| **Critérios avançados de público-alvo** | ✓ | ✓ |
| **porcentagem de implantação** | Combinado com qualquer critério de público-alvo | Combinado com qualquer critério de público-alvo |
| **Teste A/B** | ✓ | ✓ |
| **Autoatendimento** | ✓ | ✓ |
| **Trilha de auditoria** | ✓ | ✓ |

## Quando usar cada {#when-to-use}

| Cenário | Usar |
|---|---|
| Teste ou implantação de um único recurso para um aplicativo | **Sinalizador de recurso** |
| Coordenação de vários recursos na mesma equipe, entrando em funcionamento ao mesmo tempo | **Grupo de recursos** |

## Consulte também {#see-also}

* [Criar o primeiro sinalizador de recurso](create-your-first-feature-flag.md)
* [Criar um grupo de recursos](create-a-feature-group.md)
