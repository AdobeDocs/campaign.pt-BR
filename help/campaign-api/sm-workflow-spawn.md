---
source-git-commit: ffa29306eb4402ed20c7d04bdbbaffd4dde5bfe4
workflow-type: tm+mt
source-wordcount: '120'
ht-degree: 3%
---
# Spawn

Cria uma instância de workflow a partir de um modelo, aplica uma correção e inicia este workflow.

```text
Number instanceId = Spawn ( String workflowId, XML patch )
```

## Parâmetros

**workflowId** Identificador ou nome interno do modelo de fluxo de trabalho.

**patch** O elemento XML que deve ser mesclado com o modelo para obter a instância antes de executá-la. Exemplo:

```xml
    <workflow>
      <activities>
        <extern name="notepad">
          <additionnalArgs><![CDATA[c:\xxx.txt]]>
          </additionnalArgs>
        </extern>
      </activities>
    </workflow>
    
```

Este exemplo substitui os argumentos da atividade &#39;notepad&#39;. Se não quiser aplicar essa correção, use um elemento &lt;workflow/> vazio ou uma string vazia.

## Retornar valor(es)

**instanceId** Identificador da instância criada a partir do modelo.

## Observações

O comando é executado no modo assíncrono e não tem efeito imediato após o retorno do método. O workflow é iniciado com a conta do operador de chamada.

## Recursos

**Esquema:** [xtk:workflow](s-xtk-workflow.md)

**Estático:**

Sim
