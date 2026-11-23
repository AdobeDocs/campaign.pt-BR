---
source-git-commit: ffa29306eb4402ed20c7d04bdbbaffd4dde5bfe4
workflow-type: tm+mt
source-wordcount: '143'
ht-degree: 2%
---
# SpawnWithParameters

Cria uma instância de fluxo de trabalho a partir de um modelo e invoca o método [StartWithParameters](sm-workflow-startwithparameters.md) nessa instância.

```text
Number instanceId = SpawnWithParameters ( String workflowId, XML parameters )
```

## Parâmetros

**workflowId** Identificador ou nome interno do modelo de fluxo de trabalho.

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

**instanceId** Identificador da instância criada a partir do modelo.

## Observações

O comando é executado no modo assíncrono e não tem efeito imediato após o retorno do método. O workflow é iniciado com a conta dos operadores de chamada, exceto se um logon específico estiver vinculado ao template na tabela de logon do workflow, caso em que esse logon é usado.

## Recursos

**Esquema:** [xtk:workflow](s-xtk-workflow.md)

**Estático:**

Sim
