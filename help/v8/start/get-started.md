---
solution: Campaign
product: Adobe Campaign
title: Introdução ao Campaign v8
description: Conheça os principais recursos, a interface do usuário e as diretrizes globais
feature: Visão geral
role: Data Engineer
level: Beginner
exl-id: 04b12907-3cb1-40f1-90b8-1524d84edf2d,e3e9b514-a69d-4650-b1b1-1b76b4f3d63f
translation-type: tm+mt
source-git-commit: 8dd7b5a99a0cda0e0c4850d14a6cb95253715803
workflow-type: tm+mt
source-wordcount: '821'
ht-degree: 56%

---

# Introdução ao Adobe Campaign{#gs-ac-v8}

O Adobe Campaign fornece uma plataforma para projetar experiências de clientes entre canais, além de um ambiente para a organização visual de campanhas, a gestão de interações em tempo real e a execução entre canais.

Use o Campaign para:

* Impulsionar a personalização e o envolvimento por meio de uma única visualização acessível do cliente
* Integre canais de email, móveis, online e offline à jornada do cliente
* Automatize a entrega de mensagens e ofertas significativas e oportunas

![](assets/ac-capabilities.png)

## Perfil de cliente integrado {#integrated-customer-profile}

Os perfis são centralizados em um banco de dados em nuvem potente. Há vários mecanismos possíveis para obter perfis e criar esse banco de dados: coleta on-line via formulários Web, importação manual ou automática de arquivos de texto, replicação com bancos de dados corporativos ou outros sistemas de informações. Com o Adobe Campaign, você pode incorporar o histórico de marketing, informações de compras, preferências, dados de CRM e quaisquer dados PII relevantes em uma exibição consolidada para analisar e tomar decisões.

No Adobe Campaign, os destinatários são os perfis padrão direcionados para envio de entregas (e-mails, SMS etc.). Graças aos dados dos recipients que são armazenados no banco de dados, você poderá filtrar o recipient que receberá qualquer delivery e adicionar dados de personalização ao seu conteúdo de delivery. Existem outros tipos de perfis no banco de dados. Esses perfis foram projetados para diferentes usos. Por exemplo, perfis iniciais são feitos para testar seus deliveries antes que sejam enviados ao público-alvo final.

:bulb: As noções básicas de gerenciamento de perfil são explicadas em [esta seção](audiences.md).

:bulb: Saiba como adicionar perfis ao Campaign em [esta seção](import.md).

## Segmentação direcionada {#targeted-segmentation}

O Adobe Campaign tem recursos avançados de segmentação que são fáceis de usar e permitem a criação de ofertas diferenciadas e altamente direcionadas. A funcionalidade de análise descritiva permite analisar informações sobre os altos e baixos de suas campanhas de marketing. A gestão de filtros e a funcionalidade do editor gráfico de consultas permitem filtrar sua população de assinantes e amostras ou criar grupos de destino com base em um número ilimitado de critérios.

A funcionalidade avançada de Gestão de dados amplia os recursos de processamento de dados. Ela simplifica e otimiza o processo de segmentação ao incluir dados não modeladas no datamart.

:bulb: Saiba mais sobre segmentação, criação de público-alvo e personalização em [esta seção](audiences.md).

## Organização de campanhas entre canais {#cross-channel-campaign-orchestration}

O Adobe Campaign permite que você crie e organize campanhas direcionadas e personalizadas em vários canais: e-mail, mala direta, SMS e notificação por push. Uma única interface fornece todas as funções necessárias para agendar, organizar, configurar, personalizar, automatizar, executar e medir todas as suas campanhas e comunicações.

:bulb: Saiba como projetar, agendar e executar uma campanha em [esta seção](campaigns.md).

## Workflows

O Adobe Campaign oferece um ambiente gráfico abrangente que permite projetar processos complexos, incluindo segmentação, execução de campanha, processamento de arquivos etc. Por exemplo, você pode usar um workflow para baixar um arquivo de um servidor, descompactá-lo e importar seus registros para o banco de dados do Adobe Campaign.

Um workflow também pode envolver usuários atribuindo tarefas ou fazendo com que eles aprovem tarefas realizadas. Isso significa que é possível atribuir uma tarefa a um ou vários usuários para trabalhar no conteúdo ou especificar alvos e aprovar provas antes de enviar a mensagem.

Os workflows podem ser usados em contextos diferentes, como por exemplo:

* Direcionamento para gerenciar públicos-alvo ou enviar mensagens.
* Gestão de dados (ETL) para manipular dados.
* Importação de dados para o banco de dados do Campaign.
* Processos técnicos, como limpeza do banco de dados, recuperação de informações de rastreamento etc.

:bulb: Saiba como projetar e executar workflows em [esta seção](../config/workflows.md).

## Relatórios e análises {#analysis-and-reporting}

O Adobe Campaign permite monitorar e interpretar o comportamento dos clientes por meio do aprimoramento gradual de seus dados e perfis. As ferramentas de análise e geração de relatórios permitem capitalizar cada nova campanha, melhorar o direcionamento das suas iniciativas de marketing e otimizar seu impacto e o retorno sobre o investimento.

:bulb:  Saiba mais sobre os recursos de relatório e rastreamento em [esta seção](reporting.md).

## Integrações com a Adobe Experience Cloud {#adobe-experience-cloud-integrations}

Você pode combinar as funcionalidades de delivery e as funcionalidades avançadas de gerenciamento de campanhas do Adobe Campaign com um conjunto de soluções criadas para ajudar a personalizar a experiência de seus usuários: os acionadores do Adobe Experience Manager, Adobe Analytics, Adobe Target ou Adobe Experience Cloud, por exemplo. É possível também integrar o Adobe IMS e fazer logon no Campaign com sua Adobe ID.

:bulb: Saiba como integrar com serviços e soluções do Adobe em [esta seção](../connect/integration.md).

## Mais sobre os recursos do Campaign {#core-capabilities-and-add-ons}

O Adobe Campaign oferece um conjunto de recursos para ajudá-lo a implementar e otimizar as funcionalidades de marketing conversacional de acordo com a sua necessidade e arquitetura. Alguns deles são recursos básicos, enquanto outros dependem da instalação de um pacote e de sua configuração. Uma descrição detalhada do produto está disponível aqui: [Descrição do produto Adobe Campaign v8](https://helpx.adobe.com/br/legal/product-descriptions/adobe-campaign-classic---product-description.html).

:bulb: Já conhece o Campaign Classic? Saiba mais sobre as principais diferenças entre o Campaign Classic e o Campaign v8 em [this page](capability-matrix.md).

## Workspace e personalização

A área de trabalho do Campaign está disponível por meio do Console do cliente.

:bulb:  Saiba como usar o espaço de trabalho do Campaign em [esta seção](https://experienceleague.adobe.com/docs/campaign-classic/using/getting-started/starting-with-adobe-campaign/campaign-workspace/adobe-campaign-workspace.html)

:bulb:  Saiba como personalizar listas em [esta seção](https://experienceleague.adobe.com/docs/campaign-classic/using/getting-started/starting-with-adobe-campaign/campaign-workspace/adobe-campaign-ui-lists.html)

Você também pode acessar alguns recursos pela Web.

