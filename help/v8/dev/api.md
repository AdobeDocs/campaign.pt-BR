---
title: 'Introdução às APIs do Campaign '
description: 'Introdução às APIs do Campaign '
feature: API
role: Data Engineer
level: Beginner
exl-id: 50e21acd-d23d-4fdd-a8aa-23c3f209bda3
source-git-commit: c44fb2de4ed0e1661801313ae0430ba9d19542f0
workflow-type: tm+mt
source-wordcount: '0'
ht-degree: 0%

---

# Introdução ao [!DNL Campaign] APIs{#gs-ac-api}

[!DNL Adobe Campaign] O vem com um conjunto de funções Javascript que você pode usar:

* em Scripts - em [!DNL Adobe Campaign] workflows
* por APIs - de sistemas externos

Você pode usar APIs do JavaScript para gravar no banco de dados da nuvem do Campaign ou ler a partir do banco de dados:

* APIs específicas de negócios que permitem agir em cada objeto: deliveries, workflows, subscrições e assim por diante. Saiba mais na [documentação do Campaign Classic v7](https://experienceleague.adobe.com/docs/campaign-classic/using/configuring-campaign-classic/api/business-oriented-apis.html){target=&quot;_blank&quot;}.
* APIs genéricas de acesso aos dados para consultar os dados do modelo de dados. Saiba mais na [documentação do Campaign Classic v7](https://experienceleague.adobe.com/docs/campaign-classic/using/configuring-campaign-classic/api/data-oriented-apis.html){target=&quot;_blank&quot;}.

Observe que [Implantação empresarial (FDA)](../architecture/enterprise-deployment.md), o Campaign funciona com dois bancos de dados: um banco de dados local para a interface do usuário, mensagens em tempo real e consultas unitárias e gravação por meio de APIs, e um banco de dados da nuvem para execução de campanha, relatórios, assimilação de dados, consultas em lote e execução de workflows.

>[!CAUTION]
>
>[!DNL Adobe Campaign] O v8 vem com um limite na taxa de transferência (TPS) da nossa camada de API. Quebrar o limite leva a um erro HTTP padrão (429). Como usuário do Managed Cloud Services, você pode entrar em contato com o Adobe para adaptar o controle de cada API.

## Pré-requisitos

Antes de usar [!DNL Adobe Campaign] APIs, é necessário conhecer os seguintes tópicos:

* JavaScript
* Protocolo SOAP
* [!DNL Adobe Campaign] datamodel

Para usar APIs e interagir com o [!DNL Adobe Campaign], você também deve estar familiarizado com o modelo de dados do .

>[!NOTE]
>Você pode gerar uma descrição completa do seu modelo de dados. Saiba mais [nesta página](datamodel.md).


**Tópicos relacionados**

* [Práticas recomendadas do modelo de dados](datamodel-best-practices.md)
