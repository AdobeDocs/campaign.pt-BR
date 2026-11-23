---
source-git-commit: ffa29306eb4402ed20c7d04bdbbaffd4dde5bfe4
workflow-type: tm+mt
source-wordcount: '54'
ht-degree: 29%
---
# generateRegisterHookScript

Gera o script de extensão a ser chamado durante o evento de “registro” de “appSubscriptionRcp”.

```text
String JSScriptStr = generateRegisterHookScript ( XML additionalXmlNodes )
```

## Parâmetros

**additionalXmlNodes** nós XML que contêm o vínculo entre parâmetros adicionais e o campo de mapeamento de destino.

## Retornar valor(es)

**JSScriptStr** Script JS que permite vincular parâmetros adicionais a campos no target mapping.

## Recursos

**Esquema:** [nms:mobileApp](s-nms-mobileapp.md)

**Estático:**

Sim
