---
title: Cronograma
description: Saiba como agendar um sinalizador de recurso, grupo de recursos ou grupo de recursos entre equipes para ativar automaticamente em uma data e hora futuras em Implantações da Adobe Experience.
exl-id: f8309daa-428b-41a0-8817-89c8f603bec8
source-git-commit: 454b5c719a5f8be82d1ed835da58bfca6316def2
workflow-type: tm+mt
source-wordcount: '247'
ht-degree: 2%

---

# Agendar {#schedule}

O agendamento é um recurso opcional que permite definir uma data e hora futuras para um sinalizador de recurso ou grupo de recursos ser ativado automaticamente. A alternância manual liga/desliga permanece disponível e não é necessária sua substituição por uma programação.

O agendamento é compatível com:

* Sinalizadores de recursos
* Grupos de recursos

## Etapa 1: definir o agendamento {#set-schedule}

1. Abra o sinalizador de recurso ou o grupo de recursos no console.
2. Selecione o botão **Agendar** no lado direito da tela.
3. Na janela pop-up, defina a **data e hora de início** e selecione o **fuso horário**.

## Etapa 2: Salvar {#save}

Selecione **Definir Agendamento** e salve as configurações. A programação não entrará em vigor até que você a salve.

## Depois que uma programação é definida {#after-schedule-set}

Depois de salvo, a data e a hora agendadas aparecem no sinalizador de recurso ou na exibição de grupo de recursos.

Se você tentar alternar o estado ativado/desativado manualmente enquanto uma programação estiver ativa, será exibido um aviso perguntando se você deseja sobrepor a programação ou cancelar a ação.

## Na data e hora programadas {#on-schedule}

No horário agendado, o sinalizador de recurso ou grupo de recursos é ativado automaticamente (passa para o estado ATIVADO).

Depois que o agendamento é acionado, o botão **Agendar** fica desabilitado. Os agendamentos só podem ser definidos quando o sinalizador de recurso ou o grupo de recursos está no estado desativado.

## Consulte também {#see-also}

* [Criar o primeiro sinalizador de recurso](create-your-first-feature-flag.md)
* [Criar um grupo de recursos](create-a-feature-group.md)
