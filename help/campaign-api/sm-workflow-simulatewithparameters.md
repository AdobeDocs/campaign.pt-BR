---
source-git-commit: ffa29306eb4402ed20c7d04bdbbaffd4dde5bfe4
workflow-type: tm+mt
source-wordcount: '95'
ht-degree: 4%
---
# SimularComParâmetros

Inicia um fluxo de trabalho no modo de simulação e fornece parâmetros.

```text
SimulateWithParameters ( String workflowId, XML parameters )
```

## Parâmetros

**workflowId** Identificador ou nome interno do fluxo de trabalho.

**parâmetros** Parâmetros a serem transmitidos para a instância. Esses parâmetros se tornarão as variáveis de instância do fluxo de trabalho. Esse argumento é um elemento XML cujo nome deve ser variáveis e só pode incluir atributos. Exemplo:

```xml
<variables foo="abc" bar="def">
```

Os scripts JavaScript no workflow podem acessar essas variáveis do objeto instance.vars:

```javascript
    var foo = instance.vars.foo   // "abc"
    var bar = instance.vars.bar   // "def"
            
```

## Retornar valor(es)

Nenhum.

## Observações

O comando é executado de forma assíncrona e não tem efeito imediato após o retorno do método.

## Recursos

**Esquema:** [xtk:workflow](s-xtk-workflow.md)

**Estático:**

Sim
