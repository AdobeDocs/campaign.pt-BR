---
title: Introdução às APIs do Campaign
description: Introdução às APIs do Campaign
feature: API
role: Developer
level: Intermediate, Experienced
exl-id: 50e21acd-d23d-4fdd-a8aa-23c3f209bda3
source-git-commit: 07e85c2933194a24b4275519dd7da9c3226f6a3c
workflow-type: tm+mt
source-wordcount: '282'
ht-degree: 9%

---

# Introdução ao [!DNL Campaign] APIs {#gs-ac-api}

[!DNL Adobe Campaign] O vem com um conjunto de funções JavaScript que podem ser usadas:

* em Scripts - em [!DNL Adobe Campaign] workflows
* por APIs - de sistemas externos

Você pode usar APIs JavaScript para gravar no banco de dados na nuvem do Campaign ou ler a partir do banco de dados:

* APIs específicas de negócios que permitem que você atue em cada objeto: entregas, fluxos de trabalho, assinaturas e assim por diante. Saiba mais em [Documentação do Campaign Classic v7](https://experienceleague.adobe.com/docs/campaign-classic/using/configuring-campaign-classic/api/business-oriented-apis.html){target="_blank"}.
* APIs de acesso a dados genéricos para consultar os dados do modelo de dados. Saiba mais em [Documentação do Campaign Classic v7](https://experienceleague.adobe.com/docs/campaign-classic/using/configuring-campaign-classic/api/data-oriented-apis.html){target="_blank"}.

Observe que, em seu [Implantação corporativa (FFDA)](../architecture/enterprise-deployment.md), o Campaign funciona com dois bancos de dados: um banco de dados local para a interface do usuário de mensagens em tempo real e consultas unitárias e gravação por meio de APIs, e um banco de dados em nuvem para execução de campanha, relatórios, assimilação de dados, consultas em lote e execução de fluxo de trabalho.

>[!CAUTION]
>
>* Como usuário do Campaign em transição do Campaign Standard, você pode usar as APIs REST com o Campaign v8. [Saiba mais](https://experienceleague.adobe.com/en/docs/experience-cloud/campaign/apis/get-started-apis){target="_blank"}.
>
>* A partir do Campaign v8.5.1, o processo de autenticação para o Campaign v8 foi alterado. Os operadores técnicos devem usar o Adobe Identity Management System (IMS) para se conectarem ao Campaign. Saiba como migrar as contas técnicas já existentes nesta [nota técnica](../../technotes/upgrades/ims-migration.md).
>
>* [!DNL Adobe Campaign] O v8 vem com um limite na taxa de transferência (TPS) da nossa camada de API. Quebrar o limite leva ao erro HTTP padrão (429). Como usuário do Managed Cloud Service, você pode entrar em contato com o Adobe para adaptar a limitação de cada API.
> 

## Pré-requisitos {#ac-api-prerequisites}

Antes de usar [!DNL Adobe Campaign] APIs, você precisa conhecer os seguintes tópicos:

* JavaScript
* Protocolo SOAP
* [!DNL Adobe Campaign] datamodel

Para usar APIs e interagir com [!DNL Adobe Campaign], você também deve estar familiarizado com seu modelo de dados.

>[!NOTE]
>É possível gerar uma descrição completa do modelo de dados. Saiba mais [nesta página](datamodel.md).


**Tópicos relacionados**

* [Práticas recomendadas do modelo de dados](datamodel-best-practices.md)
