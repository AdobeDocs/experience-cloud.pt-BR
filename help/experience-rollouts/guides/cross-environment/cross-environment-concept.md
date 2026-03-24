---
title: Conceito entre ambientes
description: Saiba como os recursos entre ambientes nas Implantações da Adobe Experience permitem vincular aplicativos entre ambientes e gerenciar sinalizadores de recursos de forma consistente, do desenvolvimento à produção.
source-git-commit: 5c99061a7f2aaaad98190166ea6fd79b7eb26dec
workflow-type: tm+mt
source-wordcount: '340'
ht-degree: 0%

---


# Conceito entre ambientes {#cross-environment-concept}

Os recursos entre ambientes permitem vincular as instâncias do aplicativo em diferentes ambientes de implantação — como controle de qualidade, preparo e produção — e gerenciar sinalizadores de recursos de forma consistente em todos eles a partir das implantações de experiência.

## O problema entre ambientes resolve {#problem}

Sem a vinculação entre ambientes, cada instância do aplicativo nas Implantações de experiência é completamente independente das suas homólogas em outros ambientes. Isso cria vários pontos de atrito:

* Um aplicativo chamado `my-app` em Preparo não tem relação com `my-app` em Produção — eles são tratados como aplicativos separados e não relacionados.
* Não é possível visualizar o status de um sinalizador de recurso no Preparo enquanto se trabalha na Produção. É necessário alternar ambientes manualmente para comparar estados de sinalizador.
* A importação de uma configuração de sinalizador de recurso de um ambiente inferior para um superior requer recriação manual.

## O que o ambiente cruzado permite {#what-it-enables}

Ao vincular instâncias do aplicativo entre ambientes, sua equipe pode:

* Defina quais dos ambientes de implantação do aplicativo mapear para quais ambientes de Implantações de experiência
* Use rótulos de ambiente personalizados (por exemplo, `Dev`, `Staging`, `Prod`) que correspondam às convenções de nomenclatura de sua equipe
* Exibir o status de um sinalizador de recurso em todos os ambientes vinculados de uma única visualização
* Importe sinalizadores de recursos de um ambiente inferior para um superior com alguns cliques, sem recriá-los manualmente

## Como os ambientes são estruturados {#environment-structure}

As implantações de experiência têm dois ambientes de plataforma: **Preparo** e **Produção**. Seu aplicativo, no entanto, pode ter mais ambientes — por exemplo, controle de qualidade, armazenamento temporário e produção. A vinculação entre ambientes permite decidir onde estão os ambientes de cada um dos aplicativos:

* Os ambientes de controle de qualidade e armazenamento temporário podem ser hospedados no ambiente de Preparo de implantações de experiência ou no ambiente de Produção.
* Os ambientes de produção devem ser hospedados no ambiente de produção de implantações de experiência.

Essa flexibilidade significa que você não é forçado a fazer um mapeamento &quot;igual para todos&quot;.

## Próximas etapas {#next-steps}

* [Associar ambientes a um aplicativo](associate-environments.md) — configurar os links entre as instâncias do aplicativo
* [Exibir sinalizadores de recursos entre ambientes](view-feature-flags-across-environments.md) — monitorar o status do sinalizador em todos os ambientes vinculados
* [Importar sinalizadores de recursos](import-feature-flags.md) — promover sinalizadores de recursos de ambientes inferiores a superiores
