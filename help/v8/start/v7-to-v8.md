---
title: Transição do Campaign Classic v7 para o Campaign v8
description: Entender as diferenças entre o Campaign Classic v7 e o Campaign v8
feature: Overview
role: Data Engineer
level: Beginner
exl-id: 00ba1c43-9558-4adb-83a1-6597c2bbca62
source-git-commit: 70ad2603d299c3a848382503eb31571acae0ae48
workflow-type: tm+mt
source-wordcount: '635'
ht-degree: 78%

---

# Transição de [!DNL Campaign Classic] v7 para [!DNL Campaign] v8{#gs-matrix}

Como usuário do [!DNL Campaign Classic] v7, você não deve esperar nenhuma grande mudança na maneira como costuma interagir com o [!DNL Adobe Campaign]. A maioria das alterações na v8 não é visível, exceto pequenas alterações que surgiram na interface e nas etapas de configuração.

>[!AVAILABILITY]
>
>* Por enquanto, o Campaign v8 está disponível **apenas** como um serviço na nuvem gerenciado e não pode ser implantado em um ambiente local ou híbrido. [Saiba mais](#cloud-services)
>
>* A migração de um ambiente do Campaign Classic v7 existente ainda não está disponível.



## Managed Cloud Services{#cloud-services}

O Adobe Campaign v8 está disponível como um **Managed Cloud Service**.

O Adobe Campaign Managed Cloud Services oferece uma plataforma Managed Services para projetar experiências de clientes entre canais e fornece um ambiente para a orquestração visual de campanhas, o gerenciamento de interação em tempo real e a execução entre canais. Saiba mais sobre o Campaign Managed Cloud Services no [página de descrição do produto](https://helpx.adobe.com/br/legal/product-descriptions/adobe-campaign-managed-cloud-services.html){target=&quot;_blank&quot;}.

A nova oferta combina os melhores serviços do setor com uma supervisão proativa e alertas oportunos, concentrando-se em três áreas:

* **Agilidade na nuvem** — automação da Adobe, com implantações em nuvem otimizadas e padronizadas para proporcionar um desempenho mais previsível, maior agilidade e melhorias na produtividade de autoatendimento.
* **Experiência do serviço** — monitoramento e resposta proativa a respeito de disponibilidade, capacidade e desempenho, evitando interrupções, solucionando incidentes mais rapidamente e melhorando o serviço de maneira contínua, através de análises regulares.
* **Profundo conhecimento sobre o Campaign** — serviço de alta afinidade realizado por equipes especializadas em engenharia de clientes para atender às necessidades funcionais, técnicas ou relacionadas à capacidade de entrega, reduzir o risco de implantação e melhorar o gerenciamento de alterações.

Como usuário do [!DNL Campaign Classic], observe que a maioria dos recursos do [!DNL Campaign Classic] v7 está disponível no [!DNL Campaign] v8, com exceção de um pequeno conjunto listado [nesta seção](#gs-removed).

>[!NOTE]
>
> O Campaign v8 depende de uma arquitetura híbrida. Se estiver fazendo a transição do Campaign Classic v7, observe que todas as entregas passam pelo servidor mid-sourcing. [Saiba mais](../architecture/architecture.md)
>
> Como consequência, **não é possível** fazer o roteamento interno no Campaign v8 e a conta externa foi desativada de acordo.


## [!DNL Campaign] e [!DNL Snowflake] {#ac-gs-snowflake}

O Campaign v8 funciona com o [!DNL Snowflake].

Na [Implantação empresarial (FDA)](../architecture/enterprise-deployment.md), [!DNL Adobe Campaign] O v8 funciona com dois bancos de dados: um local [!DNL Campaign] banco de dados para a interface do usuário, mensagens em tempo real e consultas unitárias e gravação por meio de APIs, e uma nuvem [!DNL Snowflake] banco de dados para execução da campanha, consultas em lote e execução do workflow.

O Campaign v8 Enterprise traz o conceito de **Full Federated Data Access** (FFDA): agora, todos os dados estão disponíveis remotamente no banco de dados da nuvem. Com essa nova arquitetura, a implantação do Campaign v8 Enterprise (FDA) simplifica o gerenciamento de dados: nenhum índice é necessário no banco de dados da nuvem. Você só precisa criar as tabelas, copiar os dados e iniciar. A tecnologia de banco de dados da nuvem não requer manutenção específica para garantir o nível de desempenho.

![](../assets/do-not-localize/glass.png) Saiba mais sobre a arquitetura do [!DNL Campaign] v8 [nesta página](../architecture/architecture.md).


## Usar sua Adobe ID para se conectar ao Campaign{#adobe-id}

Os usuários da campanha se conectam somente por meio da Adobe ID. A mesma Adobe ID é usada para manter todos os seus planos e produtos da Adobe associados a uma única conta, para todas as soluções da Adobe Experience Cloud.

![](../assets/do-not-localize/glass.png)Saiba como se conectar ao [!DNL Campaign] [nesta página](connect.md).

## Analisar dados com cubos{#adobe-reporting}

Use o módulo Marketing Analytics para analisar e medir dados, calcular estatísticas, simplificar e otimizar a criação e o cálculo de relatórios. Além disso, crie relatórios e populações de destino: uma vez identificados, eles são armazenados em listas que podem ser usadas no Adobe Campaign (direcionamento, segmentação etc.).

Os relatórios de cubo do Adobe Campaign estão otimizados e oferecem melhores recursos de escala do que o Campaign Classic v7. Antigas limitações em cubos não se aplicam ao Campaign v8.

## Recursos indisponíveis{#gs-unavailable-features}

Observe que alguns recursos ainda não estão disponíveis nessa versão do Campaign, como:

* Gerenciamento de recursos de marketing
* Modelos de implantação híbridos/no local


## Recursos incompatíveis{#gs-removed}

Para alinhar-se à nova arquitetura e ao novo modelo de implantação do Campaign v8, alguns recursos históricos do Campaign Classic v7 não são mais compatíveis com o Campaign v8, como:

* Cupons
* Rastreamento web
* Pesquisas
* Marketing social
* Conector ACS (oferta principal)
* Integração com o LDAP
* Logon de usuário/senha

>[!NOTE]
>
>Alguns recursos não disponíveis ou incompatíveis ainda podem estar visíveis na interface.