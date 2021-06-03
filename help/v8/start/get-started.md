---
product: Adobe Campaign
title: Introdução ao Campaign v8
description: Conheça os principais recursos, a interface do usuário e as diretrizes globais
feature: Visão geral
role: Data Engineer
level: Beginner
exl-id: 04b12907-3cb1-40f1-90b8-1524d84edf2d,e3e9b514-a69d-4650-b1b1-1b76b4f3d63f
source-git-commit: 0e99b836dc035c0076f6771b5b430dfd1bd8edaf
workflow-type: tm+mt
source-wordcount: '882'
ht-degree: 88%

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

[!DNL :bulb:] As noções básicas de gerenciamento de perfil são explicadas [nesta seção](audiences.md).

[!DNL :bulb:] Saiba como adicionar perfis ao Campaign [nesta seção](import.md).

## Segmentação direcionada {#targeted-segmentation}

O Adobe Campaign tem recursos avançados de segmentação que são fáceis de usar e permitem a criação de ofertas diferenciadas e altamente direcionadas. A funcionalidade de análise descritiva permite analisar informações sobre os altos e baixos de suas campanhas de marketing. A gestão de filtros e a funcionalidade do editor gráfico de consultas permitem filtrar sua população de assinantes e amostras ou criar grupos de destino com base em um número ilimitado de critérios.

A funcionalidade avançada de Gerenciamento de dados amplia os recursos de processamento de dados. Ela simplifica e otimiza o processo de direcionamento ao incluir dados não modelados no datamart.

[!DNL :bulb:] Saiba mais sobre segmentação, criação de público e personalização [nesta seção](audiences.md).

## Organização de campanhas entre canais {#cross-channel-campaign-orchestration}

O Adobe Campaign permite criar e organizar campanhas direcionadas e personalizadas em vários canais: email, correspondência direta, SMS e notificação por push. Uma única interface fornece todas as funções necessárias para agendar, organizar, configurar, personalizar, automatizar, executar e medir todas as suas campanhas e comunicações.

[!DNL :bulb:] Saiba como projetar, agendar e executar uma campanha [nesta seção](campaigns.md).

## Workflows

O Adobe Campaign oferece um ambiente gráfico abrangente que permite projetar processos complexos, incluindo segmentação, execução de campanha, processamento de arquivos etc. Você pode usar um fluxo de trabalho, por exemplo, para baixar um arquivo de um servidor, descompactá-lo e importar seus registros no banco de dados do Adobe Campaign.

Um fluxo de trabalho também pode envolver usuários atribuindo tarefas ou fazendo com que eles aprovem tarefas realizadas. Isso significa que é possível atribuir uma tarefa a um ou vários usuários para trabalhar no conteúdo ou especificar alvos e aprovar provas antes de enviar a mensagem.

Os workflows podem ser usados em contextos diferentes, por exemplo:

* Direcionamento para gerenciar públicos ou enviar mensagens.
* Gerenciamento de dados (ETL) para manipular dados.
* Importação de dados para o banco de dados do Campaign.
* Processos técnicos, como limpeza do banco de dados, recuperação de informações de rastreamento etc.

[!DNL :bulb:] Saiba como projetar e executar workflows [nesta seção](../config/workflows.md).

## Relatórios e análises {#analysis-and-reporting}

O Adobe Campaign permite monitorar e interpretar o comportamento dos clientes por meio do aprimoramento gradual de seus dados e perfis. As ferramentas de análise e geração de relatórios permitem capitalizar cada nova campanha, melhorar o direcionamento das suas iniciativas de marketing e otimizar seu impacto e o retorno do investimento.

[!DNL :bulb:] Saiba mais sobre recursos de relatório e rastreamento  [nesta seção](reporting.md).

## Integrações com a Adobe Experience Cloud {#adobe-experience-cloud-integrations}

Você pode combinar as funcionalidades de entrega e as funcionalidades avançadas de gerenciamento de campanhas do Adobe Campaign com um conjunto de soluções criadas para ajudar a personalizar a experiência do usuário: os acionadores do Adobe Experience Manager, Adobe Analytics, Adobe Target ou Adobe Experience Cloud, por exemplo.

[!DNL :bulb:] Saiba como integrar a serviços e soluções da Adobe [nesta seção](../connect/integration.md).

## Mais informações sobre os recursos do Campaign {#core-capabilities-and-add-ons}

O Adobe Campaign oferece um conjunto de recursos para ajudá-lo a implementar e otimizar as funcionalidades de marketing conversacional de acordo com as suas necessidades e arquitetura. Alguns deles são recursos básicos, enquanto outros dependem da instalação de um pacote e de sua configuração. Uma descrição detalhada do produto está disponível aqui: [Descrição do produto Adobe Campaign v8](https://helpx.adobe.com/legal/product-descriptions/adobe-campaign-managed-cloud-services.html).

[!DNL :bulb:] Já conhece o Campaign Classic? Saiba mais sobre as principais diferenças entre o Campaign Classic e o Campaign v8 [nesta página](capability-matrix.md).

## Espaço de trabalho e personalização

O espaço de trabalho da campanha está disponível por meio do [Console do Cliente](../dev/general-architecture.md).

[!DNL :bulb:] [Saiba mais sobre o Console do Cliente do Campaign](../start/connect.md).

A área de trabalho do Campaign pode ser adaptada dependendo de suas necessidades.

[!DNL :arrow_upper_right:]  Saiba como usar o Campaign workspace na documentação do  [Campaign Classic v7](https://experienceleague.adobe.com/docs/campaign-classic/using/getting-started/starting-with-adobe-campaign/campaign-workspace/adobe-campaign-workspace.html?lang=pt-BR)

[!DNL :arrow_upper_right:]  Saiba como personalizar listas na documentação do  [Campaign Classic v7](https://experienceleague.adobe.com/docs/campaign-classic/using/getting-started/starting-with-adobe-campaign/campaign-workspace/adobe-campaign-ui-lists.html?lang=pt-BR)

Você também pode acessar alguns recursos pela Web.

[!DNL :bulb:] [Saiba mais sobre o Campaign Web Access](../start/connect.md#web-access).


## Languages

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

O idioma afetou datas e formatos de hora. Para obter mais informações, consulte a documentação do [Campaign Classic v7](https://experienceleague.adobe.com/docs/campaign-classic/using/getting-started/starting-with-adobe-campaign/campaign-workspace/adobe-campaign-workspace.html?lang=en#date-and-time).

