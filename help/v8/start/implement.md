---
title: Diretrizes de implementação
description: Saiba como implementar o Campaign v8
feature: Overview
role: User
level: Intermediate
exl-id: 09562b6c-3d3d-4808-a70b-202172867f46
source-git-commit: be085eaf7e1e7ded5986fdb6100045daba4d88fe
workflow-type: tm+mt
source-wordcount: '1148'
ht-degree: 97%

---

# Diretrizes de implementação do Campaign{#gs-implementation}

Nesta seção, você aprenderá a ajustar o Adobe Campaign de acordo com as necessidades da sua empresa. Use as diretrizes a seguir para estruturar e organizar sua implementação.

1. **Definir configurações**: conceda acesso, compartilhe o console do cliente, configure canais (email, push, sms). [Saiba mais](#implementation-ac-settings)
1. **Preparar seu ambiente**: importar perfis, criar públicos-alvo, criar fluxo de trabalho e modelos de campanha, criar regras de tipologia. [Saiba mais](#implementation-prepare-your-env)
1. **Personalizar sua instância**: criar novos campos de dados, adicionar tabelas/esquemas. [Saiba mais](#implementation-custom-your-instance)
1. **Automatizar seus processos**: configurar os recursos de automação do Adobe Campaign. [Saiba mais](#implementation-automation)
1. **Estender sua implantação**: conectar-se a soluções Adobe, outros produtos e sistemas — conectores, configurações de várias soluções. [Saiba mais](#implementation-extend)

>[!CAUTION]
>
>Com o **Campaign Managed Cloud Services**, o ambiente e a configuração inicial são definidos pela Adobe, de acordo com os termos do contrato de licença. Você não tem permissão para modificar pacotes integrados instalados, esquemas integrados ou relatórios.
>
>Se precisar usar um complemento do Campaign ou um recurso específico que não foi fornecido para você, entre em contato com sua **Gerência de transição da Adobe**.

## Antes de começar{#before-starting}

Esta seção contém informações críticas sobre privacidade e segurança que precisam ser examinadas e consideradas antes mesmo de iniciar a implementação real.

### Privacidade{#implementation-privacy}

O Adobe Campaign vem com processos e configurações que permitem usar o Campaign em conformidade com as leis de privacidade de dados aplicáveis e as preferências do destinatário. Você pode gerenciar:

* **Aquisição de dados**: o Adobe Campaign permite que você colete dados, incluindo informações pessoais e confidenciais. Portanto, é essencial que você receba e monitore o consentimento de seus destinatários.

  Saiba mais na [documentação do Campaign Classic v7](https://experienceleague.adobe.com/docs/campaign-classic/using/getting-started/privacy/privacy-and-recommendations.html?lang=pt-BR#data-acquisition){target="_blank"}

* **Consentimento do usuário e retenção de dados**: você deve obter o consentimento do usuário, configurar mecanismos de assinatura de participação dupla, facilitar a recusa e configurar a retenção de dados.

  Saiba mais em [documentação de privacidade do Campaign Classic v7](https://experienceleague.adobe.com/docs/campaign-classic/using/getting-started/privacy/privacy-and-recommendations.html?lang=pt-BR#consent){target="_blank"}

* **Regulamentos de proteção de dados e privacidade**: consulte [esta seção](privacy.md) para obter mais informações sobre os requisitos de privacidade e como esses regulamentos afetam sua organização e o Adobe Campaign.

### Segurança

Saiba mais sobre as diretrizes e princípios de segurança com o Adobe Campaign na [Lista de verificação de segurança do Campaign](../config/security.md).

## Definir configurações do Campaign{#implementation-ac-settings}

### Adicionar usuários e conceder permissões{#implementation-add-users}

Você pode adicionar usuários manualmente ao Campaign e associá-los a grupos, alinhados à sua hierarquia de funções. Os usuários poderão fazer logon e acessar os dados e permissões apropriados para eles.

Saiba como adicionar usuários ao Adobe Campaign [nesta seção](../start/gs-permissions.md).

### Instalar o console do cliente do Campaign{#implementation-install-console}

A principal interface do aplicativo é um cliente avançado, em outras palavras, um aplicativo nativo (Windows) que se comunica com o servidor de aplicativos do Adobe Campaign exclusivamente com protocolos padrão de Internet (SOAP, HTTP etc.). O console do cliente do Adobe Campaign oferece excelente facilidade de uso para produtividade, usa pouca largura de banda (por meio do uso de um cache local) e foi projetado para facilitar a implantação. Esse console pode ser implantado a partir de um navegador da Internet, atualizado automaticamente e não requer nenhuma configuração de rede específica porque gera apenas tráfego HTTP(S).

[Saiba mais sobre o Console do cliente do Campaign](connect.md).

## Preparar seu ambiente{#implementation-prepare-your-env}

Antes de começar a enviar mensagens e criar campanhas de marketing, é necessário:

1. **Importar perfis e criar públicos-alvo**

   O Campaign ajuda a adicionar contatos ao banco de dados da nuvem. Você pode carregar um arquivo, agendar e automatizar várias atualizações de contato, coletar dados na Web ou inserir informações de perfil diretamente na tabela do destinatário.

   [Saiba como importar perfis](import.md).

   Os públicos-alvo são agrupados em listas e podem ser criados por meio de workflows. Eles podem ser direcionados em entregas entre canais.

   [Saiba como definir públicos-alvo](audiences.md).

1. **Usar modelos**

   Campanhas, entregas, tarefas ou workflows são todos baseados em um modelo, que armazena configurações e recursos principais. Um modelo integrado é fornecido para cada componente, para o qual nenhuma configuração específica foi definida. Você precisa configurar e adaptar modelos às suas necessidades e disponibilizá-los aos usuários finais.


   Saiba como trabalhar com modelos de campanha [nesta página](https://experienceleague.adobe.com/docs/campaign/automation/campaign-orchestration/marketing-campaign-templates.html?lang=pt-BR){target="_blank"}.

   Saiba como configurar um modelo de fluxo de trabalho em [esta página](https://experienceleague.adobe.com/docs/campaign/automation/workflows/introduction/build-a-workflow.html?lang=pt-BR){target="_blank"}.

   Saiba mais sobre modelos de email na [documentação do Campaign Classic v7](https://experienceleague.adobe.com/docs/campaign-classic/using/sending-messages/using-delivery-templates/about-templates.html?lang=pt-BR){target="_blank"}.


1. **Configurar regras de tipologia**

   Aproveite as regras de tipologias do Campaign para filtrar, controlar e monitorar a entrega. Por exemplo, as regras de fadiga controlam a frequência e a quantidade de mensagens para evitar a solicitação excessiva de destinatários. Depois de implementadas, as regras de tipologia são referenciadas nas entregas.

   Saiba mais sobre tipologias e gerenciamento de fadiga [nesta seção](https://experienceleague.adobe.com/docs/campaign/automation/campaign-optimization/campaign-typologies.html?lang=pt-BR){target="_blank"}.

1. **Conheça o modelo de dados integrado do Campaign**

   O Adobe Campaign vem com um modelo de dados predefinido. Para implementar e personalizar seu ambiente, você precisa conhecer as tabelas integradas do modelo de dados do Adobe Campaign e saber como elas se relacionam entre si.

   [Saiba mais sobre o modelo de dados do Campaign](../dev/datamodel.md)

## Personalizar sua instância{#implementation-custom-your-instance}

Você pode personalizar diversas áreas e recursos do Campaign. A maioria de nossos clientes personaliza três itens:

1. **Tabelas e esquemas**

   O Adobe Campaign vem com esquemas comuns para identificar dados como: destinatários, logs de entrega, subscrições e muito mais.

   Consulte esta seção para saber mais sobre o [Modelo de dados integrado do Campaign](../dev/datamodel.md).

   É possível estender esquemas já existentes ou criar novos do zero. Saiba mais [nesta página](../dev/customize.md).

1. **Painéis e listas**

   É possível configurar facilmente listas, adicionar e remover campos e personalizar colunas.

   Saiba como gerenciar filtros e listas no Campaign [nesta página](../dev/customize.md#gs-lists-and-filters).

   Você também pode criar novos painéis para exibir dados do Campaign de acordo com suas necessidades.

   Saiba mais [nesta página](../dev/customize.md#gs-custom-dashboards).

1. **Relatórios**

   O Campaign fornece um conjunto de relatórios integrados sobre monitoramento de entrega, URLs e fluxos de clique, rastreamento, indicadores de capacidade de delivery e muito mais.

   Além dos relatórios integrados, o Adobe Campaign permite gerar relatórios em vários contextos para atender a diferentes necessidades. Os princípios de uso e dos modos de implementação são detalhados neste documento.

   Saiba mais sobre os recursos de relatórios no Campaign [nesta página](../reporting/gs-reporting.md).


## Configurar automação de campanha{#implementation-automation}

Para orquestrar campanhas de marketing complexas em públicos-alvo diferentes em vários canais, aproveite os recursos de automação do Campaign.

* Use **fluxos de trabalho** para gerenciar processos e dados. Saiba mais [nesta documentação](../../automation/workflow/about-workflows.md)

* Configurar processos de **assinatura** e **landing pages**.  Saiba mais [nesta página](../start/subscriptions.md)

* Configurar **regras de tipologia** para definir a fadiga e o gerenciamento de controle.  Saiba mais [nesta documentação](../../automation/campaign-opt/campaign-typologies.md)


## Estender sua implantação{#implementation-extend}

### Implementação de várias soluções{#implementation-multi-solutions}

Se estiver usando outras soluções da Adobe, você poderá conectá-las ao ambiente do Campaign e combinar recursos.

* Campaign — Journey Orchestration
* Campaign — CDP em tempo real
* Campaign — Triggers da Experience Cloud
* Campaign — Experience Manager
* Campaign — Target
* Campaign — Audience Manager/serviços principais de pessoas
* Campaign — ativo
* Campaign — conectores de dados do Analytics


Também é possível usar o logon único (SSO) para se conectar ao Campaign. Saiba mais [nesta página](connect.md).

Conheça a lista completa de soluções da Adobe que podem ser integradas ao Adobe Campaign [nesta página](../connect/integration.md).

### Conectores{#implementation-connectors}

Conecte o Campaign com sistemas de terceiros para combinar uma grande variedade de recursos e automatizar processos.

Saiba mais sobre conectores disponíveis [nesta seção](../connect/integration.md).

**Conecte seu CRM ao Campaign**

Você pode conectar sua plataforma do Adobe Campaign a seus sistemas de terceiros CRM e sincronizar dados: contatos, contas, compras etc.

Saiba como conectar seu sistema de CRM ao Campaign [nesta seção](../connect/integration.md#gs-crm-connectors)

**Conectar-se a um banco de dados externo**

Você pode conectar o banco de dados da nuvem do Campaign a sistemas externos por meio do módulo Federated Data Access (FDA).

Saiba como configurar o módulo FDA do Campaign para definir parâmetros de acesso [nesta seção](../connect/integration.md#gs-fda)
