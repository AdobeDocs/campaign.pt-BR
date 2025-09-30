---
title: Introdução às APIs do Campaign
description: Introdução às APIs do Campaign
feature: API
role: Developer
level: Intermediate, Experienced
exl-id: 50e21acd-d23d-4fdd-a8aa-23c3f209bda3
source-git-commit: 1d9d4111cde1e230220a04c8fd10a126116339ad
workflow-type: tm+mt
source-wordcount: '280'
ht-degree: 14%

---

# Introdução às [!DNL Campaign] APIs {#gs-ac-api}

[!DNL Adobe Campaign] vem com um conjunto de funções JavaScript que você pode usar:

* em Scripts - em [!DNL Adobe Campaign] fluxos de trabalho
* por APIs - de sistemas externos

>[!NOTE]
>
>* Dependendo do modelo de implantação, também é possível usar as APIs REST com o Campaign v8. [Saiba mais](../dev/api/get-started-apis.md).


Você pode usar as APIs do JavaScript para gravar no banco de dados na nuvem do Campaign ou ler a partir do banco de dados:

* APIs específicas de negócios que permitem que você atue em cada objeto: entregas, fluxos de trabalho, assinaturas e assim por diante. Saiba mais na [documentação do Campaign Classic v7](https://experienceleague.adobe.com/docs/campaign-classic/using/configuring-campaign-classic/api/business-oriented-apis.html?lang=pt-BR){target="_blank"}.
* APIs de acesso a dados genéricos para consultar os dados do modelo de dados. Saiba mais na [documentação do Campaign Classic v7](https://experienceleague.adobe.com/docs/campaign-classic/using/configuring-campaign-classic/api/data-oriented-apis.html?lang=pt-BR){target="_blank"}.

Observe que em sua [implantação corporativa (FFDA)](../architecture/enterprise-deployment.md), o Campaign funciona com dois bancos de dados: um banco de dados local para a interface de mensagens em tempo real, consultas unitárias e gravações por meio de APIs, e um banco de dados em nuvem para execução de campanha, relatórios, assimilação de dados, consultas em lote e execução de fluxo de trabalho.

>[!CAUTION]
>
>* A partir do Campaign v8.5.1, o processo de autenticação para o Campaign v8 foi alterado. Os operadores técnicos devem usar o Adobe Identity Management System (IMS) para se conectarem ao Campaign. Saiba como migrar as contas técnicas já existentes nesta [nota técnica](../../technotes/upgrades/ims-migration.md).
>
>* O [!DNL Adobe Campaign] v8 vem com um limite na taxa de transferência (TPS) da nossa camada de API. Quebrar o limite leva ao erro HTTP padrão (429). Como usuário do Managed Cloud Services, você pode entrar em contato com a Adobe para adaptar a limitação de cada API.
> 

## Pré-requisitos {#ac-api-prerequisites}

Antes de usar as APIs do [!DNL Adobe Campaign], você precisa estar familiarizado com os seguintes tópicos:

* JavaScript
* protocolo SOAP
* Modelo de dados [!DNL Adobe Campaign]

Para usar APIs e interagir com o [!DNL Adobe Campaign], você também deve estar familiarizado com seu modelo de dados.

>[!NOTE]
>É possível gerar uma descrição completa do modelo de dados. Saiba mais [nesta página](datamodel.md).


**Tópicos relacionados**

* [Práticas recomendadas do modelo de dados](datamodel-best-practices.md)
