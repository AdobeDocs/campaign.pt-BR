---
product: Adobe Campaign
title: Introdução ao Campaign v8
description: Novo no Campaign? Saiba como começar
feature: Visão geral
role: Data Engineer
level: Beginner
exl-id: 04b12907-3cb1-40f1-90b8-1524d84edf2d,e3e9b514-a69d-4650-b1b1-1b76b4f3d63f
source-git-commit: c61d8aa8e0a68ccc81a6141782f860daf061bc61
workflow-type: tm+mt
source-wordcount: '900'
ht-degree: 97%

---

# Introdução ao Adobe Campaign{#gs-ac-v8}

O Adobe Campaign fornece uma plataforma para projetar experiências de clientes entre canais, além de um ambiente para a organização visual de campanhas, a gestão de interações em tempo real e a execução entre canais.

Use o Campaign para:

* **Impulsionar a personalização e o envolvimento por meio de uma única visualização acessível do cliente**
* **Integrar canais de email, móveis, online e offline à jornada do cliente**
* **Automatizar a entrega de mensagens e ofertas relevantes e oportunas**

![](assets/ac-capabilities.png)

## Perfil de cliente integrado {#integrated-customer-profile}

Os perfis são centralizados em um banco de dados de nuvem eficiente. Há vários mecanismos possíveis para obter perfis e criar esse banco de dados: coleta on-line via formulários Web, importação manual ou automática de arquivos de texto, replicação com bancos de dados corporativos ou outros sistemas de informações. Com o Adobe Campaign, você pode incorporar o histórico de marketing, informações de compras, preferências, dados de CRM e quaisquer dados PII relevantes em uma exibição consolidada para analisar e tomar decisões.

No Adobe Campaign, os destinatários são os perfis padrão direcionados para envio de entregas (e-mails, SMS etc.). Graças aos dados dos recipients que são armazenados no banco de dados, você poderá filtrar o recipient que receberá qualquer delivery e adicionar dados de personalização ao seu conteúdo de delivery. Existem outros tipos de perfis no banco de dados. Esses perfis foram projetados para diferentes usos. Por exemplo, perfis iniciais são feitos para testar seus deliveries antes que sejam enviados ao público-alvo final.

?? As noções básicas de gerenciamento de perfil são explicadas [nesta seção](audiences.md).

?? Saiba como adicionar perfis ao Campaign [nesta seção](import.md).

## Segmentação direcionada {#targeted-segmentation}

O Adobe Campaign tem recursos avançados de segmentação e direcionamento que são fáceis de usar e permitem a criação de ofertas diferenciadas e altamente direcionadas. A funcionalidade de análise descritiva permite analisar informações sobre os altos e baixos de suas campanhas de marketing. A gestão de filtros e a funcionalidade do editor gráfico de consultas permitem filtrar sua população de assinantes e amostras ou criar grupos de destino com base em um número ilimitado de critérios.

A funcionalidade avançada de Gerenciamento de dados amplia os recursos de processamento de dados. Ela simplifica e otimiza o processo de direcionamento ao incluir dados não modelados no datamart.

?? Saiba mais sobre segmentação, criação de público e personalização [nesta seção](audiences.md).

## Organização de campanha entre canais {#cross-channel-campaign-orchestration}

O Adobe Campaign permite criar e organizar campanhas direcionadas e personalizadas em vários canais: email, correspondência direta, SMS e notificação por push. Uma única interface fornece todas as funções necessárias para agendar, organizar, configurar, personalizar, automatizar, executar e medir todas as suas campanhas e comunicações.

?? Saiba como projetar, agendar e executar uma campanha [nesta seção](campaigns.md).

## Workflows

O Adobe Campaign oferece um ambiente gráfico abrangente que permite projetar processos complexos, incluindo segmentação, execução de campanha, processamento de arquivos etc. Você pode usar um fluxo de trabalho, por exemplo, para baixar um arquivo de um servidor, descompactá-lo e importar seus registros no banco de dados do Adobe Campaign.

Um fluxo de trabalho também pode envolver usuários atribuindo tarefas ou fazendo com que eles aprovem tarefas realizadas. Isso significa que é possível atribuir uma tarefa a um ou vários usuários para trabalhar no conteúdo ou especificar alvos e aprovar provas antes de enviar a mensagem.

Os workflows podem ser usados em contextos diferentes, por exemplo:

* Direcionamento para gerenciar públicos ou enviar mensagens.
* Gerenciamento de dados (ETL) para manipular dados.
* Importação de dados para o banco de dados do Campaign.
* Processos técnicos, como limpeza do banco de dados, recuperação de informações de rastreamento etc.

?? Saiba como projetar e executar workflows [nesta seção](../config/workflows.md).

## Relatórios e análises {#analysis-and-reporting}

O Adobe Campaign permite monitorar e interpretar o comportamento dos clientes por meio do aprimoramento gradual de seus dados e perfis. As ferramentas de análise e geração de relatórios permitem capitalizar cada nova campanha, melhorar o direcionamento das suas iniciativas de marketing e otimizar seu impacto e o retorno do investimento.

?? Saiba mais sobre os recursos de relatórios e rastreamento [nesta seção](reporting.md).

## Integrações com a Adobe Experience Cloud {#adobe-experience-cloud-integrations}

Você pode combinar as funcionalidades de entrega e as funcionalidades avançadas de gerenciamento de campanhas do Adobe Campaign com um conjunto de soluções criadas para ajudar a personalizar a experiência do usuário: os acionadores do Adobe Experience Manager, Adobe Analytics, Adobe Target ou Adobe Experience Cloud, por exemplo.

?? Saiba como integrar a serviços e soluções da Adobe [nesta seção](../connect/integration.md).

## Mais informações sobre os recursos do Campaign {#core-capabilities-and-add-ons}

O Adobe Campaign oferece um conjunto de recursos para ajudá-lo a implementar e otimizar as funcionalidades de marketing conversacional de acordo com as suas necessidades e arquitetura. Alguns deles são recursos básicos, enquanto outros dependem da instalação de um pacote e de sua configuração. Uma descrição detalhada do produto está disponível aqui: [Descrição do produto Adobe Campaign v8](https://helpx.adobe.com/br/legal/product-descriptions/adobe-campaign-managed-cloud-services.html).

?? Já conhece o Campaign Classic? Saiba mais sobre as principais diferenças entre o Campaign Classic e o Campaign v8 [nesta página](capability-matrix.md).

## Espaço de trabalho e personalização

O espaço de trabalho do Campaign está disponível por meio do [Console do cliente](../dev/general-architecture.md).

![](assets/home-page.png)

?? [Saiba mais sobre o Console do Cliente do Campaign](../start/connect.md).

O workspace do Campaign pode ser adaptado de acordo com as suas necessidades.

↗️ Saiba como usar o espaço de trabalho do Campaign na documentação do [Campaign Classic v7](https://experienceleague.adobe.com/docs/campaign-classic/using/getting-started/starting-with-adobe-campaign/campaign-workspace/adobe-campaign-workspace.html?lang=pt-BR){target=&quot;_blank&quot;}

↗️ Saiba como personalizar listas na documentação do [Campaign Classic v7](https://experienceleague.adobe.com/docs/campaign-classic/using/getting-started/starting-with-adobe-campaign/campaign-workspace/adobe-campaign-ui-lists.html?lang=pt-BR){target=&quot;_blank&quot;}

Você também pode acessar alguns recursos pela Web.

?? [Saiba mais sobre o Campaign Web Access](../start/connect.md#web-access).


## Idiomas

A interface do usuário do Campaign v8 está disponível nos seguintes idiomas:

* Inglês (Reino Unido)
* Inglês (EUA)
* Francês
* Alemão
* Japonês

O idioma é selecionado durante o processo de instalação.

>[!CAUTION]
>
>O idioma não pode ser alterado após a criação da instância.

O idioma afetou datas e formatos de hora. Para obter mais informações, consulte a [documentação do Campaign Classic v7](https://experienceleague.adobe.com/docs/campaign-classic/using/getting-started/starting-with-adobe-campaign/campaign-workspace/adobe-campaign-workspace.html?lang=pt-BR#date-and-time){target=&quot;_blank&quot;}.

**Consulte também**

* [Matriz de compatibilidade do Campaign v8](compatibility-matrix.md)
* [Conectar-se ao Campaign](connect.md)
* [Perguntas frequentes](campaign-faq.md)