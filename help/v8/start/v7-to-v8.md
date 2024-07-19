---
title: Transição do Campaign Classic v7 para o Campaign v8
description: Saiba mais sobre as diferenças entre o Campaign Classic v7 e o Campaign v8.
feature: Overview
role: User
level: Beginner
exl-id: 00ba1c43-9558-4adb-83a1-6597c2bbca62
source-git-commit: 061197048885a30249bd18af7f8b24cb71def742
workflow-type: tm+mt
source-wordcount: '714'
ht-degree: 76%

---

# Transição do [!DNL Campaign Classic] v7 para o [!DNL Campaign] v8{#gs-matrix}

Como usuário do [!DNL Campaign Classic] v7, você não deve esperar nenhuma grande mudança na maneira como costuma interagir com o [!DNL Adobe Campaign]. A maioria das alterações na v8 não é visível, exceto pequenas alterações que surgiram na interface e nas etapas de configuração.

>[!AVAILABILITY]
>
>* Por enquanto, o Campaign v8 está disponível **apenas** como um Managed Cloud Service e não pode ser implantado em um ambiente local ou híbrido. [Saiba mais](#cloud-services)
>
>* A migração automatizada de um ambiente existente do Campaign Classic v7 ainda não está disponível.


## Managed Cloud Services{#cloud-services}

O Adobe Campaign v8 está disponível como um **Managed Cloud Service**.

O Adobe Campaign Managed Cloud Services fornece uma plataforma de serviços gerenciados na nuvem para criar experiências para clientes entre canais, além de um ambiente para orquestração visual de campanhas, gestão de interações em tempo real e execução entre canais. Saiba mais sobre os Cloud Service gerenciados pelo Campaign na [página de descrição do produto](https://helpx.adobe.com/br/legal/product-descriptions/adobe-campaign-managed-cloud-services.html){target="_blank"}.

A nova oferta combina os melhores serviços do setor com uma supervisão proativa e alertas oportunos, concentrando-se em três áreas:

* **Agilidade na nuvem** — automação da Adobe, com implantações em nuvem otimizadas e padronizadas para proporcionar um desempenho mais previsível, maior agilidade e melhorias na produtividade de autoatendimento.
* **Experiência do serviço** — monitoramento e resposta proativa a respeito de disponibilidade, capacidade e desempenho, evitando interrupções, solucionando incidentes mais rapidamente e melhorando o serviço de maneira contínua, através de análises regulares.
* **Profundo conhecimento sobre o Campaign** — serviço de alta afinidade realizado por equipes especializadas em engenharia de clientes para atender às necessidades funcionais, técnicas ou relacionadas à capacidade de entrega, reduzir o risco de implantação e melhorar o gerenciamento de alterações.

Como usuário do [!DNL Campaign Classic], observe que a maioria dos recursos do [!DNL Campaign Classic] v7 está disponível no [!DNL Campaign] v8, com exceção de um pequeno conjunto listado [nesta seção](#gs-removed).

>A nova arquitetura em nuvem permite que o Campaign simplifique processos, reduza custos, gerencie riscos e melhore a segurança dos dados. Seu ambiente do Campaign v8 vem com uma nuvem privada virtual (VPC) dedicada pré-configurada para você.


## Arquitetura híbrida {#hybrid-archi}

O Campaign v8 depende de uma **arquitetura híbrida**. Se estiver fazendo a transição do Campaign Classic v7, observe que todos os deliveries passam pelo servidor mid-sourcing.

Consequentemente:

* O roteamento interno **não é possível** no Campaign v8 e a conta externa foi desabilitada de acordo.
* O status dos deliveries não é atualizado instantaneamente - Um processo técnico é executado na instância de Marketing, o que atualizará os status do delivery em tempo hábil.


Saiba mais sobre como enviar provas de mensagem transacional ao fazer a transição do v7 nesta [página](../send/transactional-template.md#transition-from-v7).


## [!DNL Campaign] e [!DNL Snowflake] {#ac-gs-snowflake}

Em sua implantação [Corporativa (FFDA)](../architecture/enterprise-deployment.md), o [!DNL Adobe Campaign] v8 funciona com dois bancos de dados: um banco de dados [!DNL Campaign] local para a interface de mensagens em tempo real, consultas unitárias e gravações por meio de APIs, e um banco de dados [!DNL Snowflake] em nuvem para execução de campanha, consultas em lote e execução de fluxo de trabalho.

O Campaign v8 Enterprise traz o conceito de **Full Federated Data Access** (FFDA): agora, todos os dados estão disponíveis remotamente no banco de dados da nuvem. Com essa nova arquitetura, a implantação corporativa (FFDA) do Campaign v8 simplifica o gerenciamento de dados: nenhum índice é necessário no banco de dados da nuvem. Basta criar as tabelas, copiar os dados e iniciar. A tecnologia de banco de dados da nuvem não requer manutenção específica para garantir o nível de desempenho.

Saiba mais sobre a arquitetura do [!DNL Campaign] v8 [nesta página](../architecture/architecture.md).


## Usar sua Adobe ID para se conectar ao Campaign{#adobe-id}

Os usuários do Campaign se conectam apenas por meio da Adobe ID. A mesma Adobe ID é usada para manter todos os seus planos e produtos da Adobe associados a uma única conta, para todas as soluções da Adobe Experience Cloud.

Saiba como se conectar a [!DNL Campaign] em [esta página](connect.md).

## Analisar dados com cubos{#adobe-reporting}

Use o módulo Marketing Analytics para analisar e medir dados, calcular estatísticas, simplificar e otimizar a criação e o cálculo de relatórios. Além disso, crie relatórios e populações de públicos-alvo: uma vez identificados, eles são armazenados em listas que podem ser usadas no Adobe Campaign (direcionamento, segmentação etc.).

Os relatórios de cubo do Adobe Campaign v8 estão otimizados e oferecem melhores recursos de escala do que o Campaign Classic v7. Nesse modelo de implantação específico, as antigas limitações dos cubos não se aplicam ao Campaign v8. Saiba mais sobre cubos [nesta seção](../../v8/reporting/gs-cubes.md).

## Recursos indisponíveis{#gs-unavailable-features}

Observe que alguns recursos não estão disponíveis no contexto de uma [implantação Corporativa (FFDA)](../architecture/enterprise-deployment.md) do Campaign, como:

* Gerenciamento de recursos de marketing
* Cupons
* Rastreamento web
* Pesquisas

## Recursos incompatíveis{#gs-removed}

Alguns recursos históricos do Campaign Classic v7 não são mais compatíveis com o Campaign v8, como:

* Marketing social com o Facebook
* Conector ACS (oferta principal)
* Integração com o LDAP
* Logon de usuário/senha
* Modelos de implantação híbridos/no local


>[!NOTE]
>
>Alguns recursos não disponíveis ou incompatíveis ainda podem estar visíveis na interface.
