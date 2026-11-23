---
source-git-commit: ffa29306eb4402ed20c7d04bdbbaffd4dde5bfe4
workflow-type: tm+mt
source-wordcount: '41'
ht-degree: 29%
---
# CreateRequestByName

Criar uma nova solicitação do GDPR usando o nome interno do namespace

```text
Number id = CreateRequestByName ( String namespaceName, String reconciliationValue, Number type, Boolean confirmDeletePending )
```

## Parâmetros

**namespaceName** Nome interno do namespace

**reconciliationValue** Valor de reconciliação

Valor de reconciliação de **type**

**confirmDeletePending** Solicitar confirmação antes de excluir os dados

## Retornar valor(es)

**id** ID da solicitação recém-criada

## Recursos

**Esquema:** [nms:gdprRequest](s-nms-gdprrequest.md)

**Estático:**

Sim
