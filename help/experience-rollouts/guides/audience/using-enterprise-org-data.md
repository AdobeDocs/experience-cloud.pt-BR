---
title: Usar dados da organização corporativa nas regras de público-alvo
description: Saiba como usar as Enterprise Organization IDs como critérios de público-alvo nas implantações de experiência da Adobe para direcionar organizações de clientes específicas.
exl-id: 74f97ec7-a809-41bf-a41d-bb57f033040f
source-git-commit: 4a3133f014a9bb9d6ed26eb9d9f763db79ce63b3
workflow-type: tm+mt
source-wordcount: '233'
ht-degree: 1%

---

# Usar dados da organização corporativa nas regras de público-alvo {#enterprise-org-data}

As Implantações de experiência são compatíveis com direcionamento de usuários com base na ID de organização empresarial (org). Isso permite implantar recursos em organizações de clientes específicas antes de disponibilizá-los amplamente.

## Adicionar uma organização a uma regra de público-alvo {#adding-org-rule}

O direcionamento da organização corporativa está disponível na guia **Público-alvo** em **Regras de público-alvo > Perfil > Empresa**.

Dois tipos de organização são compatíveis:

### Organizações DME {#dme-orgs}

As organizações DME são identificadas pela ID da organização. Ao criar a regra, insira somente a ID da organização — não inclua uma fonte de autenticação.

### Organizações de DMA {#dma-orgs}

As organizações DMA usam IDs de organização no formato `XXXXXXXXXXXXXXXXXXXXXXXX@ADOBEORG`. Ao inserir uma ID da organização DMA:

* Use a ID completa da organização, incluindo o sufixo `@ADOBEORG`.
* Digite `ADOBEORG` em maiúsculas.

**Exemplo:** `57F22B5D5A5F83AE0A495E6E@ADOBEORG`

## Observações importantes {#important-notes}

* O direcionamento baseado em organização é avaliado em relação à organização associada à sessão autenticada do usuário. Verifique se o usuário está conectado à organização correta ao testar.
* Se uma organização que você espera encontrar não estiver aparecendo nos critérios de público-alvo ou se os recursos não forem retornados como esperado para uma organização específica, entre em contato com o suporte de Implantações de experiência.
* Os ambientes de Preparo e Produção podem diferir de acordo com as organizações disponíveis. Teste as regras de público-alvo no preparo antes de promover para produção.

## Consulte também {#see-also}

* [Público-alvo em sinalizadores e grupos de recursos](audience-in-feature-flags-and-feature-groups.md)
* [Regras complexas de público](complex-rules.md)
