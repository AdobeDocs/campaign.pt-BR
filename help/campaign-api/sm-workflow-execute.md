---
source-git-commit: ffa29306eb4402ed20c7d04bdbbaffd4dde5bfe4
workflow-type: tm+mt
source-wordcount: '50'
ht-degree: 8%
---
# Executar

Executa um fluxo de trabalho imediatamente e aguarda sua conclusão.

```text
XML workflow = Execute ( String workflowId, Boolean simulationMode, Boolean keepResult, Boolean logSQL )
```

## Parâmetros

**workflowId** Identificador ou nome interno do fluxo de trabalho.

**simulationMode** Simulação de execução.

**keepResult** Manter resultados provisórios.

**logSQL** É necessário salvar um rastreamento de ordens SQL?

## Retornar valor(es)

**workflow** O resultado da execução.

## Recursos

**Esquema:** [xtk:workflow](s-xtk-workflow.md)

**Estático:**

Sim
