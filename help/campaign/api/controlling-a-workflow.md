---
title: Controle de um fluxo de trabalho
description: Saiba como controlar um fluxo de trabalho com APIs.
audience: developing
content-type: reference
topic-tags: campaign-standard-apis
role: Data Engineer
level: Experienced
badge: label="DISPONIBILIDADE LIMITADA" type="Informative" url="../campaign-standard-migration-home.md" tooltip="Restrito a usuários migrados do Campaign Standard"
source-git-commit: 84b72258789ba61016deb813e93bdca0ea142712
workflow-type: tm+mt
source-wordcount: '96'
ht-degree: 9%

---

# Controle de um fluxo de trabalho {#controlling-a-workflow}

Você pode controlar um workflow diretamente da API REST, por meio de uma solicitação POST contendo a ID do workflow e o comando de execução necessário:

`POST https://mc.adobe.io/<ORGANIZATION>/campaign/workflow/execution/<workflowID>/commands`

>[!CAUTION]
>
>Se a ID do fluxo de trabalho for alterada no Adobe Campaign, a solicitação da API não funcionará mais.

Quatro comandos de execução estão disponíveis para controlar um workflow:

* Start
* Pausar
* Retomar
* Stop

Para obter mais informações sobre os comandos de execução, consulte [Documentação da campanha](https://experienceleague.adobe.com/docs/campaign-standard/using/managing-processes-and-data/executing-a-workflow/about-workflow-execution.html).

<br/>

***Solicitações de exemplo***

* Inicie um workflow.

  ```
  -X POST https://mc.adobe.io/<ORGANIZATION>/campaign/workflow/execution/<workflowID>/commands \
  -H 'Content-Type: application/json' \
  -H 'Authorization: Bearer <ACCESS_TOKEN>' \
  -H 'Cache-Control: no-cache' \
  -H 'X-Api-Key: <API_KEY>' \
  -i
  -d '{"method":"start"}'
  ```

  <!-- + réponse -->

* Interrompa um workflow.

  ```
  -X POST https://mc.adobe.io/<ORGANIZATION>/campaign/workflow/execution/<workflowID>/commands \
  -H 'Content-Type: application/json' \
  -H 'Authorization: Bearer <ACCESS_TOKEN>' \
  -H 'Cache-Control: no-cache' \
  -H 'X-Api-Key: <API_KEY>' \
  -i
  -d '{"method":"stop"}'
  ```

  <!-- + réponse -->
