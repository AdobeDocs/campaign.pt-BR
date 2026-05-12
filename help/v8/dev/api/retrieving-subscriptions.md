---
title: Recuperação de subscrições
description: Saiba como recuperar assinaturas com APIs
role: Developer
level: Experienced
exl-id: 6d935074-3196-45c5-97cd-ccb7c80bbba8
TQID: https://experienceleague.adobe.com/PxFql-omcIMizY-oMBl75gfo2UmmLTanrhQqw5te--A
product_v2:
  - id: dfc56824-e8b9-499e-85d4-21aedb507314
feature_v2:
  - id: b12f6872-9271-4369-85e5-86969a0b99a2
subfeature_v2:
  - id: bf97c196-a4d1-4fa3-a151-e68a114c8ac0
role_v2:
  - id: ff6a42d2-313e-452e-93a6-792e4fad9ff8
source-git-commit: 15d7b12d07f84356fac7bee2a54a0057c5d00d41
workflow-type: tm+mt
source-wordcount: 200
ht-degree: 1%

---

# Recuperação de assinaturas com APIs {#retrieving-subscriptions-api}

## Recuperação de perfis que assinaram um serviço

Este é um procedimento de duas etapas.

1. Recupere o URL de assinaturas do serviço desejado.
1. Execute uma solicitação GET no URL de assinaturas. Ele retorna a lista de subscrições para o serviço, com cada perfil associado.

>[!CAUTION]
>
>A API REST retorna a propriedade &quot;href&quot;, que contém o URL a ser usado. <b>Sempre usar a URL contida na resposta para fazer a solicitação de API subsequente</b>.

<br/>

***Solicitação de exemplo***

Execute uma solicitação GET para recuperar o serviço.

```
-X GET https://mc.adobe.io/<ORGANIZATION>/campaign/profileAndServices/service/<PKEY> \
-H 'Content-Type: application/json' \
-H 'Authorization: Bearer <ACCESS_TOKEN>' \
-H 'Cache-Control: no-cache' \
-H 'X-Api-Key: <API_KEY>'
```

Ele retorna o URL de subscrições do serviço.

```
  {
    ...
    "messageType": "email",
    "name": "SVC1",
    "subscriptions": {
                "href": "https://mc.adobe.io/<ORGANIZATION>/campaign/profileAndServices/service/<PKEY>/subscriptions/"
    },
    ...
  },
```

Execute uma solicitação GET no URL de assinaturas.

```
-X GET https://mc.adobe.io/<ORGANIZATION>/campaign/profileAndServices/service/<PKEY>/subscriptions \
-H 'Content-Type: application/json' \
-H 'Authorization: Bearer <ACCESS_TOKEN>' \
-H 'Cache-Control: no-cache' \
-H 'X-Api-Key: <API_KEY>'
```

A lista de subscrições do serviço é exibida, com cada perfil associado.

```
  {
    ...
    "service": ...,
    "serviceName": "SVC3",
    "subscriber": {
        "PKey": "<PKEY>",
        "email": "",
        "firstName": "John",
        "href": "https://mc.adobe.io/<ORGANIZATION>/campaign/profileAndServices/profile/<PKEY>",
        "lastName": "Doe",
    },
  }
```

## Recuperar os serviços que um perfil assinou

Este é um procedimento de duas etapas.

1. Recupere o URL de assinaturas de um determinado perfil.
1. Execute uma solicitação GET no URL. Retorna a lista de subscrições do perfil, com cada serviço associado.

<br/>

***Solicitação de exemplo***

Execute uma solicitação GET para recuperar o perfil.

```
-X GET https://mc.adobe.io/<ORGANIZATION>/campaign/profileAndServices/profile/<PKEY> \
-H 'Content-Type: application/json' \
-H 'Authorization: Bearer <ACCESS_TOKEN>' \
-H 'Cache-Control: no-cache' \
-H 'X-Api-Key: <API_KEY>'
```

Ele retorna o URL de assinaturas do perfil.

```
  {
    ...
    "postalAddress":...,
    "preferredLanguage": "none",
    "subscriptions": {
      "href": "https://mc.adobe.io/<ORGANIZATION>/campaign/profileAndServices/profile/<PKEY>/subscriptions/"
    },
    ...
  }
```

Execute uma solicitação GET no URL de assinaturas.

```
-X GET https://mc.adobe.io/<ORGANIZATION>/campaign/profileAndServices/profile/<PKEY>/subscriptions \
-H 'Content-Type: application/json' \
-H 'Authorization: Bearer <ACCESS_TOKEN>' \
-H 'Cache-Control: no-cache' \
-H 'X-Api-Key: <API_KEY>'
```

Retorna a lista de serviços que o perfil assinou.

```
  {
    ...
    "PKey": "<PKEY>",
    "created": "2017-03-03 10:54:00.363Z",
    "service": {
      "PKey": "<PKEY>",
      "href": "https://mc.adobe.io/<ORGANIZATION>/campaign/profileAndServices/service/<PKEY>",
      "label": "Sport Newsletter",
      "name": "SVC1",
      "title": "Sport Newsletter (SVC1)"
    },
    ...
  }
```
