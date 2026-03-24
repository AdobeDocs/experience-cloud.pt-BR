---
title: Monitorar e editar um plano de implantação
description: Saiba como rastrear o progresso de um plano de implantação automatizado em implantações do Adobe Experience e como pausar, retomar ou suspender um plano em andamento.
source-git-commit: d824d85c6701edc9be314713bb8e9624b183e2d2
workflow-type: tm+mt
source-wordcount: '478'
ht-degree: 0%

---


# Monitorar e editar um plano de implantação {#monitor-edit-rollout-plan}

Depois que uma implantação automatizada estiver ativa, você poderá rastrear seu progresso e intervir, se necessário. Esta página descreve como ler o indicador de progresso, pausar e retomar um plano e abortá-lo, se necessário.

Esta página supõe que você já tenha criado e publicado um plano de implantação. Consulte [Criar uma implantação automatizada](create-automated-rollout.md) se ainda não tiver configurado uma.

## Exibir progresso de implantação {#view-progress}

Depois que o plano de implantação começar a ser executado, abra a guia **Público-alvo** do recurso para ver o estado atual do plano. O plano exibe um indicador de andamento que marca qual bloco de fase está ativo no momento.

Use o indicador de progresso para entender o seguinte:

* **Blocos concluídos** — Todos os blocos de fase e espera acima do indicador foram executados. Esses blocos estão bloqueados e não podem ser editados.
* **Bloco atual** — O bloco atualmente destacado é a fase ativa ou o período de espera.
* **Blocos futuros** — Todos os blocos de fase e espera abaixo do indicador ainda não foram executados. Elas ainda podem ser editadas.

## Pausar um plano de implantação {#pause}

Para pausar a implantação em qualquer ponto enquanto ela estiver em andamento, selecione **Pausar Implantação** no console.

Quando o plano estiver pausado:

* O público-alvo do último bloco de fase concluído permanece ativo. Os usuários nesse público-alvo continuam a receber o recurso.
* O sinalizador de recurso, grupo de recursos ou grupo de recursos entre equipes permanece no estado atual ativado ou publicado. Ele continua distribuindo o recurso para o público-alvo ativo atual.
* Os próximos blocos de fase e espera permanecem editáveis.

Para retomar um plano pausado, selecione **Retomar Implantação**. O plano continua de onde parou.

## Anular um plano de implantação {#abort}

Para interromper permanentemente o plano de implantação, selecione **Abortar implantação** no console.

Quando o plano for abortado:

* O público-alvo do último bloco de fase concluído permanece ativo e o recurso continua a ser distribuído a esse público-alvo.
* O recurso em si não está desativado — se você quiser interromper o fornecimento do recurso totalmente, será necessário cancelar a versão separadamente ou desativar o sinalizador ou grupo de recursos.
* Os próximos blocos de fase e espera não podem mais ser editados.
* Um plano anulado não pode ser retomado.

>[!IMPORTANT]
>
>Cancelar um plano de implantação não desativa o recurso automaticamente. Execute uma ação separada no estado do recurso se desejar interromper a disponibilização para os usuários.

## Editar blocos de fase futuros {#edit-upcoming}

Enquanto o plano estiver em andamento (ou pausado), você ainda poderá editar qualquer fase ou bloco de espera que ainda não tenha sido executado:

* Ajuste as regras ou a porcentagem de público-alvo de um bloco de fase futuro.
* Alterar a duração ou a data fixa de um bloco de espera futuro.

Blocos concluídos são bloqueados e não podem ser alterados.

## Consulte também {#see-also}

* [Criar uma implantação automatizada](create-automated-rollout.md)
* [Conceito de implantação automatizada](automated-rollout-concept.md)
* [Estados de lançamento](../feature-flags/release-states.md)
