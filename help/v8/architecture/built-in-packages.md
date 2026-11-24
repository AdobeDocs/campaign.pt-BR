---
title: Pacotes incorporados
description: Saiba o que são pacotes integrados no Campaign v8, como eles diferem dos pacotes de dados personalizados e quais estão disponíveis
feature: Architecture
role: Admin, Developer
level: Beginner
hide: true
product_v2:
  - id: dfc56824-e8b9-499e-85d4-21aedb507314
    internal-label: Campaign
  - id: d0e9f0b2-1f2b-4134-9844-49cd4e950f27
    internal-label: Campaign v8
feature_v2:
  - id: bae31391-3416-5fbd-bc4b-2cdcae2922db
    internal-label: Architecture
  - id: c5474392-5419-4296-9e41-f6f4ce4f6e9b
    internal-label: Administration
subfeature_v2:
  - id: e656c701-3899-4db3-989c-de0980ddfffa
    internal-label: Installation
role_v2:
  - id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
    internal-label: Admin
  - id: ff6a42d2-313e-452e-93a6-792e4fad9ff8
    internal-label: Developer
level_v2:
  - id: e8ccd51f-da0d-4e3b-939b-e30d5ebb1ea5
    internal-label: Beginner
source-git-commit: a2ca220e4be9dfb4a90465b69dd08a3552040a07
workflow-type: tm+mt
source-wordcount: '821'
ht-degree: 16%
---
# Pacotes incorporados {#built-in-packages}

Os pacotes incorporados (também conhecidos como pacotes padrão) contêm os recursos do Adobe Campaign. No Campaign v8, o Adobe instala e gerencia esses pacotes para você. Não é necessário instalá-los.

## Pacotes incorporados e pacotes personalizados {#built-in-vs-custom}

O Campaign usa dois tipos de pacotes. Certifique-se de trabalhar com o correto.

| | Pacotes incorporados | Pacotes personalizados |
|---|---|---|
| Finalidade | Forneça os recursos do Campaign, como canais, integrações e complementos. | Exporte e importe sua própria configuração e dados, por exemplo, de um ambiente de preparo para um de produção. |
| Quem os gerencia | O Adobe os instala e gerencia. Com o Managed Cloud Services, não é possível modificar pacotes integrados instalados. | Você pode criá-los, exportá-los e importá-los. |
| Onde saber mais | Esta página. | [Trabalhar com pacotes de dados](../dev/packages.md) |

## Verificar os pacotes instalados {#check-installed-packages}

Para verificar quais pacotes internos estão instalados na sua instância, navegue até **[!UICONTROL Administration > Configuration > Package management > Installed packages]**. Você também pode visualizá-las na Instância de monitoramento do Painel de controle do Campaign. Saiba mais em [Visão geral do monitoramento da campanha](../start/monitor.md#monitor-instance).

Se precisar de um pacote ou complemento que não foi provisionado para você, entre em contato com o Atendimento ao cliente da Adobe ou com o gerente de transição da Adobe.

## Lista de pacotes incorporados {#list-of-built-in-packages}

A tabela a seguir lista os pacotes incorporados para obter informações. A disponibilidade de cada pacote está sujeita ao seu contrato de licença e ao seu modelo de implantação.

| Pacote | Descrição |
|---|---|
| Entrega | Pacote principal obrigatório do Adobe Campaign. Ele permite enviar deliveries. [Saiba mais](../start/gs-message.md) |
| Campanhas de marketing (Campaign) | Define, otimiza, executa e analisa campanhas de comunicação e marketing. [Saiba mais](../start/campaigns.md) |
| Recursos de marketing (MRM) | Controla ações de marketing em um modo colaborativo, com gerenciamento e rastreamento de tarefas, orçamentos e recursos de marketing. [Saiba mais](../../automation/mrm/about-marketing-resource-management.md) |
| Dispositivo de oferta (interação) | Responde em tempo real durante uma interação com um contato, fazendo uma ou várias ofertas adaptadas. [Saiba mais](../interaction/interaction.md) |
| Redes sociais (marketing social) | Sincroniza o Adobe Campaign com o X (antigo Twitter). [Saiba mais](../connect/ac-tw.md) |
| Controle e execução de mensagens transacionais (Centro de mensagens) | Gerencia mensagens de acionamento geradas por eventos em sistemas de informações, com maior disponibilidade e melhor gerenciamento de carga. [Saiba mais](../send/transactional.md) |
| Canal LINE | Envia deliveries por meio do canal LINE. [Saiba mais](../send/line/line.md) |
| Canal de correspondência direta | Envia deliveries por meio do canal de correspondência direta. [Saiba mais](../send/direct-mail.md) |
| Canal móvel (SMS) | Envia deliveries por meio do canal móvel (SMS), incluindo o conector SMS v2 (geralmente disponível desde a versão 8.9.1). [Saiba mais](../send/sms/sms.md) |
| Canal de aplicativo móvel | Envia notificações personalizadas para dispositivos iOS e Android por meio de aplicativos. [Saiba mais](../send/push.md) |
| Gerenciador de conteúdo | Cria informativos ou sites recorrentes e, em seguida, valida e publica suas mensagens. [Saiba mais](../../automation/workflow/content-management.md) |
| Pesquisas online (Gerenciador de pesquisas) | Cria e gerencia formulários online para adicionar ou modificar informações de perfil, assinar, cancelar inscrição ou inserir um concurso. [Saiba mais](../dev/surveys/about-surveys.md) |
| Análise de marketing | Analisa e mede dados, calcula estatísticas e simplifica a criação de relatórios. [Saiba mais](../reporting/gs-reporting.md) |
| Gestor de Resposta | Mede o sucesso e a lucratividade de campanhas ou ofertas de marketing em todos os canais. [Saiba mais](../../automation/response/about-response-manager.md) |
| Acesso a dados externos (Federated Data Access) | Processa informações armazenadas em bancos de dados externos sem alterar a estrutura dos dados do Adobe Campaign. [Saiba mais](../connect/fda.md) |
| Otimização de campanha | Controla, filtra e monitora as entregas para que as mensagens atendam às necessidades dos clientes e às políticas de comunicação da empresa. [Saiba mais](../../automation/campaign-opt/campaign-typologies.md) |
| Monitoramento da avaliação da entrega (avaliação da entrega por email) | Mede se as mensagens chegam à caixa de entrada sem serem rejeitadas ou marcadas como spam. [Saiba mais](../send/monitoring-deliverability.md) |
| Gerenciamento de cupom | Cria conjuntos de cupons para adicionar a ofertas de marketing. [Saiba mais](../send/personalized-coupons.md) |
| Renderização da caixa de entrada (IR) | Pré-visualiza mensagens nos contextos em que elas podem ser recebidas e verifica a compatibilidade com os principais clientes de email da área de trabalho e da Web. [Saiba mais](../send/inbox-rendering.md) |
| Marketing central/local (Marketing distribuído) | Implementa campanhas cooperativas entre entidades centrais, como sede, e entidades locais, como pontos de vendas. [Saiba mais](../../automation/distributed-marketing/about-distributed-marketing.md) |
| Conectores CRM | Vincula o Adobe Campaign a sistemas CRM de terceiros. [Saiba mais](../connect/crm.md) |
| Conectores de análise da Web | Permite que o Adobe Campaign e o Adobe Analytics interajam. [Saiba mais](../connect/ac-aa.md) |
| Integração com o AEM | Gerencia o conteúdo de emails e formulários no Adobe Experience Manager. [Saiba mais](../connect/ac-aem.md) |
| Integração de públicos-alvo compartilhados do Adobe Experience Cloud | Troca e compartilha públicos com soluções e aplicativos [!DNL Adobe CX Enterprise] (anteriormente Adobe Experience Cloud). [Saiba mais](../start/shared-audiences.md) |
| Integração com a Adobe Experience Cloud | Importa e exporta públicos das soluções [!DNL Adobe CX Enterprise] (anteriormente Adobe Experience Cloud) para a Adobe Campaign. [Saiba mais](../connect/integration.md) |
| Regulamento de Proteção de Dados de Privacidade | Adiciona funcionalidade para ajudar na conformidade com a privacidade. [Saiba mais](../start/privacy.md) |
| Suporte ao AMP | Envia emails dinâmicos com o AMP interativo para formato de email. [Saiba mais](../send/defining-interactive-content.md) |


>[!NOTE]
>
>Os pacotes Marketing resources (MRM), Coupon Management e Online survey não estão disponíveis no contexto de uma implantação Enterprise (FFDA) do Campaign. Saiba mais sobre [Disponibilidade de recursos](../architecture/enterprise-deployment.md#feature-availability).

## Tópicos relacionados {#related-topics}

* [Trabalhar com pacotes de dados](../dev/packages.md): crie, exporte e importe seus próprios pacotes personalizados.
* [Workflows técnicos](../../automation/workflow/technical-workflows.md): os workflows técnicos internos e o pacote que instala cada um deles.
* [Disponibilidade de recursos em implantações FFDA](enterprise-deployment.md#feature-availability): os recursos que não estão disponíveis em implantações Enterprise (FFDA).
* [Recursos sem suporte](../start/v7-to-v8.md#gs-removed): os recursos do Campaign Classic v7 que não têm mais suporte no v8.
* [Princípios globais](general-architecture.md): o que você pode ou não modificar em um ambiente do Managed Cloud Services.
* [Introdução ao Campaign v8](../start/get-started.md): uma visão geral dos principais recursos e complementos.
