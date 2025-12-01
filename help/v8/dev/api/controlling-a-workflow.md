---
title: Controle de um fluxo de trabalho
description: Saiba como controlar um fluxo de trabalho com APIs.
audience: developing
content-type: reference
topic-tags: campaign-standard-apis
role: Data Engineer
level: Experienced
exl-id: 79eacc31-d5a2-4e13-aa0b-744d7ab7004f
source-git-commit: 5b9793d98d12afb28e987b16bc2e34f0ee72ac5f
workflow-type: tm+mt
source-wordcount: '80'
ht-degree: 12%

---

# Controle de um fluxo de trabalho {#controlling-a-workflow}

Você pode controlar um workflow diretamente da API REST, por meio de uma solicitação POST contendo a ID do workflow e o comando de execução necessário:

`POST https://mc.adobe.io/<ORGANIZATION>/campaign/workflow/execution/<workflowID>/commands`

>[!CAUTION]
>
>Se a ID do fluxo de trabalho for alterada no Adobe Campaign, a solicitação da API não funcionará mais.

Quatro comandos de execução estão disponíveis para controlar um workflow:

* Start
* Pause
* Retomar
* Parar


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

* Pausar um workflow.

  ```
  -X POST https://mc.adobe.io/<ORGANIZATION>/campaign/workflow/execution/<workflowID>/commands \
  -H 'Content-Type: application/json' \
  -H 'Authorization: Bearer <ACCESS_TOKEN>' \
  -H 'Cache-Control: no-cache' \
  -H 'X-Api-Key: <API_KEY>' \
  -i
  -d '{"method":"pause"}'
  ```

  <!-- + réponse -->

* Retomar um workflow.

  ```
  -X POST https://mc.adobe.io/<ORGANIZATION>/campaign/workflow/execution/<workflowID>/commands \
  -H 'Content-Type: application/json' \
  -H 'Authorization: Bearer <ACCESS_TOKEN>' \
  -H 'Cache-Control: no-cache' \
  -H 'X-Api-Key: <API_KEY>' \
  -i
  -d '{"method":"resume"}'
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
