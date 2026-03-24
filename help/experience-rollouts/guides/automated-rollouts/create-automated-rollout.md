---
title: Criar uma implantação automatizada
description: Saiba como configurar um plano de implantação automatizado em implantações de experiência do Adobe com blocos de fase e blocos de espera para que seu público-alvo se expanda automaticamente com o tempo.
source-git-commit: d824d85c6701edc9be314713bb8e9624b183e2d2
workflow-type: tm+mt
source-wordcount: '522'
ht-degree: 0%

---


# Criar uma implantação automatizada {#create-automated-rollout}

Uma implantação automatizada permite definir todas as fases de implantação e seus agendamentos em uma sessão. As Implantações de experiência avançam de uma fase para a próxima automaticamente, sem exigir que você retorne ao console para cada etapa. Consulte [Conceito de implantação automatizada](automated-rollout-concept.md) para obter uma visão geral.

As implantações automatizadas são compatíveis com sinalizadores de recursos, grupos de recursos e grupos de recursos entre equipes.

## Etapa 1: Ativar implantação automatizada {#enable-automated-rollout}

Ao criar um novo sinalizador de recurso, grupo de recursos ou grupo de recursos entre equipes, abra a guia **Detalhes Básicos** e localize a opção **Selecionar tipo de implantação**. O padrão é **Manual**. Para habilitar um plano de implantação automatizada, selecione **Implantação automatizada**.

>[!NOTE]
>
>Quando você seleciona Implantação automatizada, o campo Implantação percentual em Detalhes básicos é automaticamente definido como 100% e se torna não editável. Você controlará a porcentagem de cada fase individualmente na guia Público-alvo.

## Etapa 2: criar o plano de implantação {#build-rollout-plan}

Abra a guia **Público-alvo** e habilite a opção **Fases**. Isso ativa os controles **Adicionar Bloco de Fase** e **Adicionar Bloco de Espera**.

Para criar seu plano de implantação, adicione blocos de fase e espera na ordem em que deseja que eles sejam executados:

### Adicionar um bloco de fase {#add-phase-block}

Um bloco de fase define os critérios de público-alvo para uma fase da implantação. O primeiro bloco de fase é configurado usando os critérios de público-alvo já existentes na página. Para cada bloco de fase subsequente, o público da fase anterior é pré-preenchido como ponto de partida.

Configure o público-alvo para cada bloco de fase:

* **Percentage** — Defina qual porcentagem do público-alvo definido recebe o recurso nesta fase.
* **Regras de público-alvo** — Adicione regras baseadas em perfil, contexto ou segmento para usuários específicos.

>[!IMPORTANT]
>
>Cada fase subsequente deve expandir, não substituir, o público da fase anterior. Não remova as regras de público-alvo de fases anteriores ao configurar fases posteriores, pois isso pode excluir inadvertidamente os usuários que já estavam recebendo o recurso.

### Adicionar um bloco de espera {#add-wait-block}

Um bloco de espera define a pausa entre dois blocos de fase. Depois de adicionar um bloco de espera, selecione uma das seguintes opções:

| Opção | Descrição |
|---|---|
| **Aguardar** | Uma duração relativa — por exemplo, aguarde 2 dias, aguarde 4 horas. As Implantações de experiência avançam para o próximo bloco de fase depois que essa duração expirar. |
| **Aguardar** | Uma data e hora fixas. As Implantações de experiência avançam para o próximo bloco de fase no momento especificado. |

### Adicionar blocos de fase subsequentes {#add-subsequent-phases}

Repita o processo para adicionar outros blocos de fase e blocos de espera até que seu plano de implantação completo esteja configurado.

## Etapa 3: agendar ou publicar a implantação {#schedule-or-publish}

Quando o plano de implantação estiver concluído, escolha como ativá-lo:

* **Agendar** — Defina uma data e hora futuras para que a implantação seja iniciada automaticamente. Consulte [Agendamento](../feature-flags/schedule.md) para obter detalhes.
* **Publicar manualmente** — Ative o sinalizador de recurso ou mova o grupo de recursos para o estado **Publicar** para iniciar imediatamente.

O plano começa a ser executado a partir do primeiro bloco de fase. Você pode monitorar e editar o plano ativo a qualquer momento. Consulte [Monitorar e editar um plano de implantação](monitor-edit-rollout-plan.md).

## Consulte também {#see-also}

* [Conceito de implantação automatizada](automated-rollout-concept.md)
* [Monitorar e editar um plano de implantação](monitor-edit-rollout-plan.md)
* [Definir um recurso para implantação gradual](../feature-flags/set-feature-gradual-rollout.md)
* [Critérios de público](../audience/audience-in-feature-flags-and-feature-groups.md)
