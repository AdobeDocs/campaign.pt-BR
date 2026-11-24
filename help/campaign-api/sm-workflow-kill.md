---
source-git-commit: ffa29306eb4402ed20c7d04bdbbaffd4dde5bfe4
workflow-type: tm+mt
source-wordcount: '79'
ht-degree: 3%
---
# Eliminar

Interrompe incondicionalmente um workflow.

```text
Kill ( String workflowId )
```

## Parâmetros

**workflowId** Identificador ou nome interno do fluxo de trabalho.

## Retornar valor(es)

Nenhum.

## Observações

Esse método é útil se um workflow não puder ser interrompido normalmente. Isso pode acontecer se o workflow ou uma tarefa tiver uma afinidade em particular ou se o módulo wfserver que lida com essa afinidade não estiver mais em execução. Nesse caso, o workflow permanece sinalizado como &#39;Stop requested&#39; e só pode ser interrompido pelo comando Kill.

## Recursos

**Esquema:** [xtk:workflow](s-xtk-workflow.md)

**Estático:**

Sim
