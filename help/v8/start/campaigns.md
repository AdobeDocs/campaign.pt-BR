---
solution: Campaign v8
product: Adobe Campaign
title: Introdução a campanhas de marketing
description: Introdução a campanhas de marketing
feature: Públicos
role: Data Engineer
level: Beginner
exl-id: b5a6c845-13a7-4746-b856-a08a3cf80b66,c4798c8f-619e-4a60-80d7-29b9e4c61168
source-git-commit: ab7e458db5ad5696d144c17f6e89e4437a476d11
workflow-type: tm+mt
source-wordcount: '730'
ht-degree: 22%

---

# Introdução às campanhas de marketing{#gs-ac-campaigns}

A Adobe Campaign oferece um conjunto de soluções que ajudam você a personalizar e entregar campanhas em todos os seus canais online e offline. Você pode criar, configurar, executar e analisar campanhas de marketing. Todas as campanhas de marketing podem ser gerenciadas a partir de um centro de controle unificado. Descubra como navegar e criar campanhas de marketing nesta seção.

As campanhas incluem ações (deliveries) e processos (importação ou extração de arquivos), além de recursos (documentos de marketing e delivery outlines). Eles são usados em campanhas de marketing. As campanhas são parte de um programa, e os programas estão incluídos em um plano de campanha.

## Organização de campanhas entre canais

O Adobe Campaign permite que você crie e organize campanhas direcionadas e personalizadas em vários canais: e-mail, mala direta, SMS e notificação por push. Uma única interface fornece todas as funções necessárias para agendar, organizar, configurar, personalizar, automatizar, executar e medir todas as suas campanhas e comunicações.

### Conceitos principais

Antes de começar a implementar campanhas de marketing, você precisa conhecer os seguintes conceitos:

* **Campanha** de marketing: uma campanha centraliza todos os elementos relacionados a uma campanha de marketing: deliveries, regras de direcionamento, custos, arquivos de exportação, documentos relacionados etc. Cada campanha é anexada a um programa.

* **Programa**: um programa permite definir ações de marketing para um período de calendário: iniciar, prospecção, fidelização etc. Cada programa contém campanhas vinculadas a um calendário, que fornece uma visualização geral.

* **Plano**: o plano de marketing pode conter vários programas. Ele está vinculado a um período de calendário, tem um orçamento alocado e também pode ser vinculado a documentos e objetivos.

* **Fluxo de trabalho** da campanha: um workflow de campanha contém atividades para criar a lógica de campanha. Use workflows da campanha para definir públicos e criar deliveries para todos os canais disponíveis.

* **Campanhas** recorrentes: as campanhas recorrentes são criadas a partir de um template específico que define o template de workflow a ser executado e o agendamento de execução.

* **Campanhas** periódicas: uma campanha periódica é uma campanha criada automaticamente de acordo com o agendamento de execução de seu template.

## Área de trabalho da campanha de marketing

O Adobe Campaign permite criar, configurar, executar e analisar todas as campanhas de marketing de um centro de controle unificado.

[!DNL :arrow_upper_right:] Saiba como acessar e implementar campanhas de marketing na documentação do  [Campaign Classic v7](https://experienceleague.adobe.com/docs/campaign-classic/using/orchestrating-campaigns/about-marketing-campaigns/accessing-marketing-campaigns.html?lang=en#orchestrating-campaigns)


## Etapas principais para iniciar

As principais etapas para criar uma campanha de marketing entre canais são:

1. **Planejar e projetar programas e campanhas de marketing**

   Defina a hierarquia e o cronograma, defina o orçamento, adicione recursos e selecione operadores.

   [!DNL :arrow_upper_right:] Saiba como criar um plano de marketing e configurar campanhas na documentação do  [Campaign Classic v7](https://experienceleague.adobe.com/docs/campaign-classic/using/orchestrating-campaigns/orchestrate-campaigns/setting-up-marketing-campaigns.html?lang=en#creating-plan-and-program-hierarchy)

   Todas as campanhas de marketing são baseadas em um template, que armazena as principais configurações e recursos. Um modelo integrado é fornecido para criar uma campanha para a qual nenhuma configuração específica foi definida. Você pode criar e configurar seus modelos de campanha e, em seguida, criar campanhas com base nesses modelos.

   [!DNL :arrow_upper_right:] Saiba como trabalhar com templates de campanha na documentação do  [Campaign Classic v7](https://experienceleague.adobe.com/docs/campaign-classic/using/orchestrating-campaigns/orchestrate-campaigns/marketing-campaign-templates.html?lang=en#orchestrating-campaigns)

   [!DNL :arrow_upper_right:] Descubra campanhas recorrentes e como configurá-las na documentação do  [Campaign Classic v7](https://experienceleague.adobe.com/docs/campaign-classic/using/orchestrating-campaigns/orchestrate-campaigns/setting-up-marketing-campaigns.html?lang=en#recurring-and-periodic-campaigns)

1. **Definir públicos-alvo**

   Você pode criar o público-alvo em um workflow ou selecionar um grupo existente, como uma lista de recipients, assinantes de um boletim informativo, recipients de um delivery anterior ou qualquer condição de filtragem.

   [!DNL :arrow_upper_right:] Saiba como definir o público-alvo de suas mensagens na documentação do  [Campaign Classic v7](https://experienceleague.adobe.com/docs/campaign-classic/using/orchestrating-campaigns/orchestrate-campaigns/marketing-campaign-target.html?lang=en#orchestrating-campaigns)

1. **Criar deliveries**

   Selecione os canais, defina o conteúdo da mensagem e inicie os deliveries.

   [!DNL :arrow_upper_right:] Saiba como criar e iniciar deliveries de campanha de marketing na documentação do  [Campaign Classic v7](https://experienceleague.adobe.com/docs/campaign-classic/using/orchestrating-campaigns/orchestrate-campaigns/marketing-campaign-deliveries.html?lang=en#creating-deliveries)

   Você pode associar vários documentos a uma campanha: relatório, foto, página da Web, diagrama, etc.

   [!DNL :arrow_upper_right:] Saiba mais sobre documentos associados na documentação do  [Campaign Classic v7](https://experienceleague.adobe.com/docs/campaign-classic/using/orchestrating-campaigns/orchestrate-campaigns/marketing-campaign-assets.html?lang=en#adding-documents)

1. **Configurar o processo de aprovação**

   O Adobe Campaign permite que você configure processos de aprovação colaborativa para os principais estágios da campanha de marketing. Para cada campanha você pode aprovar o target, o conteúdo e os custos do delivery. Os operadores do Adobe Campaign responsáveis pela aprovação podem ser notificados por e-mail e podem aceitar ou rejeitar a aprovação por meio do console ou por meio de uma conexão com a Web.

   [!DNL :arrow_upper_right:] Saiba como configurar e gerenciar aprovações na documentação do  [Campaign Classic v7](https://experienceleague.adobe.com/docs/campaign-classic/using/orchestrating-campaigns/orchestrate-campaigns/marketing-campaign-approval.html?lang=en#orchestrating-campaigns)

