---
title: Conceito de implantação automatizada
description: Entenda como as implantações automatizadas funcionam nas implantações de experiência do Adobe, incluindo blocos de fase, blocos de espera e como o plano de implantação avança automaticamente.
source-git-commit: d824d85c6701edc9be314713bb8e9624b183e2d2
workflow-type: tm+mt
source-wordcount: '414'
ht-degree: 2%

---


# Conceito de implantação automatizada {#automated-rollout-concept}

Uma implantação automatizada permite definir todo o seu plano de implantação em fases de uma só vez. Em vez de retornar manualmente ao console para expandir o público-alvo de cada fase, configure todas as fases e seus agendamentos antecipadamente e as implantações de experiência avançam automaticamente por meio delas.

As implantações automatizadas são compatíveis com sinalizadores de recursos, grupos de recursos e grupos de recursos entre equipes.

## Como funciona {#how-it-works}

Um plano de implantação é composto de **blocos de fase** e **blocos de espera** que são executados em sequência:

* **Bloco de fases** — Define os critérios de público-alvo para uma fase da implantação. Quando o plano atinge um bloco de fase, esse público-alvo se torna o público-alvo ativo do recurso.
* **Bloco de espera** — Define a pausa entre dois blocos de fase. Um bloco de espera pode ser uma duração relativa (por exemplo, &quot;aguardar 3 dias&quot;) ou uma data e hora fixas.

O plano é iniciado quando você publica o recurso ou o agenda para uma data futura. As Implantações de experiência movem-se de um bloco para o próximo automaticamente de acordo com o agendamento configurado.

## Comportamento do bloco de fase {#phase-block-behavior}

Cada bloco de fase subsequente é pré-preenchido com o público da fase anterior. Isso facilita a criação de implantações de expansão incremental, em que cada nova fase inclui todos os grupos de público-alvo anteriores, além dos novos.

>[!IMPORTANT]
>
>As regras de público-alvo em cada bloco de fase são editáveis, portanto, não exclua os critérios de público-alvo das fases anteriores ao adicionar novos. A redução do escopo do público-alvo no meio da implantação pode resultar na perda inesperada de acesso de usuários a um recurso.

## Estados do plano de implantação {#rollout-plan-states}

Depois que um plano de implantação estiver ativo, ele poderá estar em um dos três estados:

| Estado | Descrição |
|---|---|
| **Em andamento** | O plano está em execução. Um indicador de progresso no console mostra qual bloco de fase está ativo no momento. Todos os blocos concluídos estão bloqueados e não podem ser editados. |
| **Em pausa** | O plano está em espera. O público-alvo do último bloco de fase concluído permanece ativo. Os blocos de fase e espera futuros ainda podem ser editados enquanto estão pausados. |
| **Anulado** | O plano foi interrompido permanentemente. O público-alvo do último bloco de fase concluído permanece ativo. Não são permitidas mais edições no plano. Abortar o plano não desativa o recurso — você deve alterar separadamente o estado do recurso se desejar parar de distribuí-lo. |

## Consulte também {#see-also}

* [Criar uma implantação automatizada](create-automated-rollout.md)
* [Monitorar e editar um plano de implantação](monitor-edit-rollout-plan.md)
* [Definir um recurso para implantação gradual](../feature-flags/set-feature-gradual-rollout.md)
