---
source-git-commit: ffa29306eb4402ed20c7d04bdbbaffd4dde5bfe4
workflow-type: tm+mt
source-wordcount: '55'
ht-degree: 27%
---
# TestCalcField

Testar o campo calculado usando as linhas de amostra armazenadas no script.

```text
XML calcFieldValues = TestCalcField ( XML dataTransferStep, String calcFieldName )
```

## Parâmetros

**dataTransferStep** Etapa de transferência de dados na qual o campo calculado é definido

**calcFieldName** Campo calculado para teste

## Retornar valor(es)

**calcFieldValues** Retorna a lista de valores de cada linha de exemplo (calcFieldValues/line) e o nome do campo (calcFieldValues/@name)

## Recursos

**Esquema:** [xtk:dataTransfer](s-xtk-datatransfer.md)

**Estático:**

Sim
