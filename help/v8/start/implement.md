---
solution: Campaign Classic
product: campaign
title: Diretrizes de implementação
description: Saiba como implementar o Campaign v8
feature: Visão geral
role: Data Engineer
level: Beginner
exl-id: 09562b6c-3d3d-4808-a70b-202172867f46
translation-type: tm+mt
source-git-commit: 6fee88c2bcfade752d45712adeab50e199f0c07c
workflow-type: tm+mt
source-wordcount: '1153'
ht-degree: 4%

---

# Diretrizes de implementação da campanha

Nesta seção, você aprenderá a ajustar o Adobe Campaign às necessidades da sua empresa. Use as diretrizes a seguir para estruturar e organizar sua implementação.

1. **Definir configurações**: conceder acesso, compartilhar o console do cliente, configurar canais (email, push, sms)
1. **Prepare seu ambiente**: importar perfis, criar públicos-alvo, criar fluxo de trabalho e modelos de campanha, criar regras de tipologia
1. **Personalize sua instância**: criar novos campos de dados, adicionar tabelas/esquemas
1. **Estender sua implantação**: conectar-se a soluções Adobe, outros produtos e sistemas - conectores, configurações de várias soluções

## Antes de começar

Esta seção inclui informações para desenvolvedores específicos de sua implementação que precisam cuidar da privacidade e da segurança antes de começar.

### Privacidade

O Adobe Campaign vem com processos e configurações que permitem usar o Campaign em conformidade com as leis de privacidade de dados aplicáveis e as preferências do recipient. Você pode gerenciar:

* **Aquisição** de dados: O Adobe Campaign permite coletar dados, inclusive informações pessoais e confidenciais. Portanto, é essencial que você receba e gerencie o consentimento de seus recipients. Saiba mais em [Campaign Classic documentation](https://experienceleague.corp.adobe.com/docs/campaign-classic/using/getting-started/privacy/privacy-and-recommendations.html?lang=en#data-acquisition)

* **Consentimento do usuário e retenção** de dados: Saiba como obter consentimento do usuário, configurar mecanismos de assinatura de aceitação dupla, facilitar a recusa e configurar a retenção de dados na documentação de privacidade do  [Campaign Classic](https://experienceleague.corp.adobe.com/docs/campaign-classic/using/getting-started/privacy/privacy-and-recommendations.html?lang=en#consent)

* **Privacidade e regulamentos** sobre proteção de dados: consulte a  [documentação de privacidade do ](https://experienceleague.corp.adobe.com/docs/campaign-classic/using/getting-started/privacy/privacy-and-recommendations.html) Campaign Classic para obter informações sobre o Regulamento Geral sobre a Proteção de Dados (GDPR) da União Europeia, a Lei de Privacidade do Consumidor da Califórnia (CCPA) e outros requisitos de privacidade internacionais e como esses regulamentos afetam sua organização e a Adobe Campaign.

### Segurança

Saiba mais sobre as diretrizes e princípios de segurança com o Adobe Campaign em [Lista de verificação de segurança do Campaign](../config/security.md))

## Definir configurações do Campaign

### Adicionar usuários e conceder permissões

Você pode adicionar usuários manualmente ao Campaign e associá-los a grupos, alinhados à sua hierarquia de funções. Os usuários poderão fazer logon e acessar os dados e permissões apropriados para eles.

:seta_upper_right: Saiba como adicionar usuários ao Adobe Campaign em [esta seção](https://experienceleague.adobe.com/docs/campaign-classic/using/getting-started/permissions/access-management.html?lang=en#getting-started).

### Instalar o console do cliente do Campaign

A principal interface de usuário do aplicativo é um cliente avançado, em outras palavras, um aplicativo nativo (Windows) que se comunica com o servidor de aplicativos Adobe Campaign exclusivamente com protocolos padrão de Internet (SOAP, HTTP etc.). O console do cliente Adobe Campaign oferece excelente facilidade de uso para produtividade, usa pouca largura de banda (por meio do uso de um cache local) e foi projetado para facilitar a implantação. Esse Console pode ser implantado a partir de um navegador da Internet, pode ser atualizado automaticamente e não requer nenhuma configuração de rede específica porque gera apenas tráfego HTTP(S).

:bulb: [Saiba mais sobre o Console do Cliente do Campaign](connect.md).

## Preparar seu ambiente

Antes de começar a enviar mensagens e criar campanhas de marketing, é necessário:

1. Importar perfis e criar públicos-alvo

   O Campaign ajuda a adicionar contatos ao banco de dados do Cloud. Você pode carregar um arquivo, agendar e automatizar várias atualizações de contato, coletar dados na Web ou inserir informações de perfis diretamente na tabela do recipient.

   :bulb: [Saiba como importar perfis](import.md).

   Os públicos-alvo são agrupados em listas e podem ser criados por meio de fluxos de trabalho. Eles podem ser direcionados em deliveries entre canais.

   :bulb: [Saiba como definir públicos-alvo](audiences.md).

1. Criar modelos

   Campanhas, entregas, tarefas ou fluxos de trabalho são todos baseados em um modelo, que armazena configurações e recursos principais. Um modelo integrado é fornecido para cada componente, para o qual nenhuma configuração específica foi definida. Você precisa configurar e adaptar modelos às suas necessidades e disponibilizá-los aos usuários finais.

   :seta_upper_right: [Saiba mais sobre modelos de email](https://experienceleague.adobe.com/docs/campaign-classic/using/sending-messages/using-delivery-templates/about-templates.html)

   :seta_upper_right: Saiba como trabalhar com templates de campanha em [esta página](https://experienceleague.adobe.com/docs/campaign-classic/using/orchestrating-campaigns/orchestrate-campaigns/marketing-campaign-templates.html?lang=en#orchestrating-campaigns)

   :seta_upper_right: Saiba como configurar um modelo de fluxo de trabalho em [esta página](https://experienceleague.adobe.com/docs/campaign-classic/using/automating-with-workflows/introduction/building-a-workflow.html?lang=en#workflow-templates)

1. Configurar regras de tipologia

   Aproveite as regras de tipologias do Campaign para filtrar, controlar e monitorar o envio de delivery. Por exemplo, as regras de fadiga controlam a frequência e a quantidade de mensagens para evitar a solicitação excessiva de recipients. Depois de implementadas, as regras de tipologia são referenciadas nos deliveries.

   :seta_upper_right: [Saiba mais sobre tipologias e gerenciamento de fadiga](https://experienceleague.adobe.com/docs/campaign-classic/using/orchestrating-campaigns/campaign-optimization/about-campaign-typologies.html?lang=en#orchestrating-campaigns)

1. Conheça o modelo de dados integrado do Campaign

   O Adobe Campaign vem com um modelo de dados predefinido. Para implementar e personalizar seu ambiente, você precisa conhecer as tabelas integradas do modelo de dados do Adobe Campaign e sua interação.

   :bulb: [Saiba mais sobre o datamodel do Campaign](../dev/datamodel.md).

## Personalize sua instância

Você pode personalizar diversas áreas e recursos do Campaign. A maioria de nossos clientes personaliza três itens:

1. **Tabelas e esquemas**

   O Adobe Campaign vem com esquemas comuns para identificar dados como: recipients, logs do delivery, assinaturas e muito mais.

   :bulb: Consulte esta seção para saber mais sobre [Modelo de dados integrado do Campaign](../dev/datamodel.md).

   :bulb: É possível estender esquemas existentes ou criar novos esquemas do zero. Saiba mais [nesta página](../dev/customize.md).

1. **Painéis e listas**

   É possível configurar facilmente listas, adicionar e remover campos e personalizar colunas.

   :bulb: Saiba como gerenciar filtros e listas no Campaign em [this page](../dev/customize.md#gs-lists-and-filters).

   Você também pode criar novos painéis para exibir dados do Campaign dependendo de suas necessidades.

   :bulb: Saiba mais em [esta página](../dev/customize.md#gs-custom-dashboards).

1. **Relatórios**

   O Campaign fornece um conjunto de relatórios internos sobre monitoramento de delivery, URLs e fluxos de clique, rastreamento, indicadores de deliverability e muito mais.

   Além dos relatórios internos, o Adobe Campaign permite gerar relatórios em vários contextos para atender a diferentes necessidades. Os princípios de uso e dos modos de implementação são detalhados neste documento.

   :bulb: Saiba mais sobre os recursos de relatório no Campaign em [this page](reporting.md).


## Configurar automação de campanha

Para orquestrar campanhas de marketing complexas para públicos diferentes em vários canais, aproveite os recursos de automação do Campaign.

* Fluxos de trabalho: gerenciar processos e dados

* Subscrições e landing pages

* Regras de tipologia: fadiga e gerenciamento de controle

## Estender sua implantação

### Implementação de várias soluções

Se estiver usando outras soluções do Adobe, você pode conectá-las ao ambiente do Campaign e combinar recursos.

* Campanha - Journey Orchestration
* Campaign - CDP em tempo real
* Campaign - Experience Cloud Triggers
* Campanha - Experience Manager
* Campanha - Target
* Campaign - Audience Manager / Serviços principais do People
* Campanha - Ativo
* Campaign - Conectores de dados do Analytics


Você também pode usar o Logon único (SSO) para se conectar ao Campaign. Saiba mais [nesta página](connect.md).

:bulb: Descubra a lista completa da solução Adobe que pode ser integrada ao Adobe Campaign [nesta página](../connect/integration.md).

### Conectores

Conecte o Campaign com sistemas de terceiros para combinar uma grande variedade de recursos e automatizar processos.

:bulb: Saiba mais sobre conectores disponíveis em [esta seção](../connect/integration.md).

**Conecte seu CRM ao Campaign**

Você pode conectar sua plataforma Adobe Campaign a seus sistemas de terceiros CRM e sincronizar dados: contatos, contas, compras etc.

:bulb: Saiba como conectar seu sistema CRM ao Campaign em [esta seção](../connect/integration.md#gs-crm-connectors)

**Conectar-se a um banco de dados externo**

Você pode conectar o banco de dados da Campaign Cloud a sistemas externos por meio do módulo Federated Data Access (FDA).

:bulb: Saiba como configurar o módulo FDA do Campaign para definir parâmetros de acesso em [esta seção](../connect/integration.md#gs-fda)
