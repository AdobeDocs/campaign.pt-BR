---
source-git-commit: ffa29306eb4402ed20c7d04bdbbaffd4dde5bfe4
workflow-type: tm+mt
source-wordcount: '155'
ht-degree: 7%
---
# SubmitNotification

Criar e enviar uma notificação de um cenário.

```text
Number notificationId = SubmitNotification ( String scenarioName, XML target )
```

## Parâmetros

**scenarioName** Nome interno do modelo

**público-alvo** População do público-alvo da entrega que substitui o do cenário

## Retornar valor(es)

Identificador de notificação **notificationId**

## Observações

Aviso: essa API não foi criada para gerenciar grandes volumes de dados ou trabalhar em tempo real. Ele é desenvolvido para processar no máximo várias chamadas por minuto. SubmitNotification bloqueia o thread durante a análise de entrega. Isso pode levar alguns segundos. O parâmetro &quot;target&quot; especifica o target do delivery. Ele substituirá um target especificado no template. Para enviar para um target no banco de dados, o elemento target usará a seguinte sintaxe:

```xml
<delivery>
  <targets>
    <deliveryTarget>
      <targetPart type='query' exclusion='false' ignoreDeleteStatus='false'>
        <where>
          <condition expr='[@folder-id] = 1050'/>
        </where>
      </targetPart>
    </deliveryTarget>
  </targets>
</delivery>
```

Para enviar para um destino em um arquivo:

```xml
<delivery>
  <targets>
    <deliveryFile upload='false'>
      <name>c:/tmp/myFile.csv</name>
    </deliveryFile>
  </targets>
</delivery>
```

É possível definir explicitamente o target (na verdade, o conteúdo do arquivo usado como o target):

```xml
<delivery>
  <targets fromExternalSource='true'>
    <externalSource>MsgId|ClientId|Title|Name|FirstName|Mobile|Email|Market_segment|Product_propensity1|Product_propensity2|Product_propensity3|Product_propensity4|Support_Number|Amount|Threshold1|
                    000001234|M.|Martin|Peter|0650201020|pmartin@neolane.com|1|A1|A2|A3|A4|E12|120000|100000
    </externalSource>
  </targets>
</delivery>
```

Também é possível manter o target definido no template com o atributo &quot;\_keepTemplateTarget&quot;

```xml
<delivery>
  <targets _keepScenarioTarget='true'/>
</delivery>
```

## Recursos

**Esquema:** [nms:delivery](s-nms-delivery.md)

**Estático:**

Sim
