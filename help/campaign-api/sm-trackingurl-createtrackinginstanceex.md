---
source-git-commit: ffa29306eb4402ed20c7d04bdbbaffd4dde5bfe4
workflow-type: tm+mt
source-wordcount: '67'
ht-degree: 19%
---
# CreateTrackingInstanceEx

Criar ou configurar uma instância de rastreamento em um servidor de redirecionamento

```text
CreateTrackingInstanceEx ( String internalPwd, String serverUrl, String secureServerUrl, String serverUrlList, String instanceName, String cryptedPassword, String host, String imsOrgId )
```

## Parâmetros

**internalPwd** Senha interna

**serverUrl** URL externa do servidor de rastreamento

**secureServerUrl** URL segura externa do servidor de rastreamento

**serverUrlList** URLs internas dos servidores de rastreamento

**instanceName** Nome da instância a ser criada

**cryptedPassword** Senha criptografada

Máscaras DNS **host** associadas à instância

**imsOrgId** ID da organização IMS

## Retornar valor(es)

Nenhum.

## Recursos

**Esquema:** [nms:trackingUrl](s-nms-trackingurl.md)

**Estático:**

Sim
