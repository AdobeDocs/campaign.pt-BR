---
source-git-commit: ffa29306eb4402ed20c7d04bdbbaffd4dde5bfe4
workflow-type: tm+mt
source-wordcount: '56'
ht-degree: 28%
---
# RegisterTrackingInstance

Aprova uma instância de rastreamento em um servidor de redirecionamento (definindo o identificador do banco de dados).

```text
RegisterTrackingInstance ( String serverUrl, String secureServerUrl, String serverUrlList, String instanceName, String cryptedPassword )
```

## Parâmetros

**serverUrl** URL externa do servidor de rastreamento

**secureServerUrl** URL segura externa do servidor de rastreamento

**serverUrlList** URLs internas dos servidores de rastreamento

**instanceName** Nome da instância a ser aprovada

**cryptedPassword** Senha criptografada

## Retornar valor(es)

Nenhum.

## Recursos

**Esquema:** [nms:trackingUrl](s-nms-trackingurl.md)

**Estático:**

Sim
