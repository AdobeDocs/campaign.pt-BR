---
source-git-commit: ffa29306eb4402ed20c7d04bdbbaffd4dde5bfe4
workflow-type: tm+mt
source-wordcount: '27'
ht-degree: 37%
---
# RegisterGroup

Adicionar destinatários selecionados a uma lista

```text
RegisterGroup ( XML groupList, XML recipientList, Boolean register )
```

## Parâmetros

Listas de **groupList**

**recipientList** Lista de destinatários

**registrar** destinatários de inscrição/cancelamento de inscrição

## Retornar valor(es)

Nenhum.

## Exemplo

```javascript
//List
var entity = <entityList><key value="24447964"/>
              <where>
                <condition enabledIf="" expr="@id = 24447964"/>
              </where>
            </entityList>
 
//Recipient
var choice = <choiceList><key value="18995462"/>
              <where>
                <condition enabledIf="" expr="@id = 18995462"/>
              </where>
            </choiceList>
nms.recipient.RegisterGroup(entity,choice,true)
        
```

## Recursos

**Esquema:** [nms:recipient](s-nms-recipient.md)

**Estático:**

Sim
