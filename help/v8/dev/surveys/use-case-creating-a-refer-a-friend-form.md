---
product: campaign
title: Criar uma pesquisa Indique um Amigo
description: Saiba mais sobre como criar um formulário Indique um Amigo
feature: Surveys
version: Campaign v8, Campaign Classic v7
exl-id: bd94c41a-813a-4ddb-a2bd-c3deab022482
TQID: 'https://experienceleague.adobe.com/n0qp8Q0p18fMbRYxAOu5Qj-0TCf8YgL5vF71F-ZGjbM'
product_v2:
  - id: dfc56824-e8b9-499e-85d4-21aedb507314
    internal-label: Campaign
  - id: d0e9f0b2-1f2b-4134-9844-49cd4e950f27
    internal-label: Campaign v8
feature_v2:
  - id: a075b2c1-7748-4328-b7f6-343aa314616a
    internal-label: Campaigns
  - id: c5474392-5419-4296-9e41-f6f4ce4f6e9b
    internal-label: Administration
  - id: a4671286-a59f-47e3-b97b-90627a1977d5
    internal-label: Communication channels
  - id: 71b1c383-45b9-57e0-b8cd-ea2e98a01a26
    internal-label: Surveys
subfeature_v2:
  - id: ed29abcd-b6a8-4d4b-ab8b-b7e746973281
    internal-label: Web Forms
  - id: e739ee2b-6228-412e-878f-45de0791417d
    internal-label: Use cases
topic_v2:
  - id: e0eb8757-182f-49f3-94a4-1587d16f5094
    internal-label: Personalization
  - id: eddd9b14-83bd-4ff4-9072-54a4a484abb7
    internal-label: Administration
source-git-commit: d3b34546c1b08190772154efe6f818b98cc1094c
workflow-type: tm+mt
source-wordcount: '820'
ht-degree: 71%
---
# Caso de uso: criar um formulário de indicação{#use-case-creating-a-refer-a-friend-form}

>[!AVAILABILITY]
>
>As pesquisas não estão disponíveis para [implantações do FFDA do Campaign](../../architecture/enterprise-deployment.md).



Neste exemplo, queremos oferecer uma competição aos destinatários do banco de dados. O formulário Web terá uma seção para inserir respostas e outra para indicar um amigo inserindo seu endereço de email.

![Formulário de competição com uma área de identificação, uma área de teste com perguntas aleatórias e uma área de convite para indicar um amigo](assets/s_ncs_admin_survey_viral_sample_0.png)

Os blocos de identificação e concorrência são criados usando os processos descritos anteriormente.

Para configurar e criar o bloco de referência, siga as etapas abaixo:

1. Crie um formulário Web de competição com perguntas e um campo para inserir as informações de contato de um amigo, conforme mostrado abaixo:

   ![Estrutura do formulário de competição com uma Identificação, um Jogo e uma seção de Indicação com campos de contatos de amigos](assets/s_ncs_admin_survey_viral_sample_2.png)

   O campo **Sua mensagem** permite inserir uma mensagem para o indicado. Quem indicou também deve inserir seu **Sobrenome**, **Nome** e **Email**.

   As informações inseridas nos campos são armazenadas em uma tabela específica conhecida como tabela do visitante.

   >[!NOTE]
   >
   >Se o destinatário não tiver consentido, você não pode armazená-lo com os destinatários no banco de dados. Eles serão armazenados temporariamente na tabela **visitor** (**nms:visitor**) criada para campanhas de marketing viral. Essa tabela é removida regularmente graças às operações de **limpeza**.
   >
   >Neste exemplo, queremos direcionar os destinatários para sugerir que façam parte da competição recomendada por quem indicou. No entanto, nessa mensagem, também queremos oferecer uma subscrição de um de nossos serviços de informação. Caso se subscrevam, eles podem ser armazenados no banco de dados.

   ![Estrutura do formulário com o campo Seu sobrenome na seção Indique um amigo selecionado](assets/s_ncs_admin_survey_viral_sample_5.png)

   O conteúdo dos campos relacionados ao indicado será usado no script de criação de perfil e na mensagem enviada para eles.

1. Comece criando um script para vincular quem indicou ao indicado.

   Ele contém as seguintes instruções:

   ![Diagrama de formulário com a caixa de script Informações do indicado aberta, definindo a ID de visitante, URL de encaminhamento e campos de referenciador](assets/s_ncs_admin_survey_viral_sample_4.png)

   ```javascript
   ctx.recipient.visitor.@id = xtk.session.GetNewIds(1)
   ctx.recipient.visitor.@forwardUrl = "APP5"
   ctx.recipient.visitor.@referrerEmail = ctx.recipient.@email
   ctx.recipient.visitor.@referrerFirstName = ctx.recipient.@firstName
   ctx.recipient.visitor.@referrerLastName = ctx.recipient.@lastName
   ```

   O sobrenome, o nome e o endereço de email inseridos no bloco de identificação da página são identificados como o sobrenome, nome e endereço de email de quem indicou. Esses campos serão reintroduzidos no corpo da mensagem enviada ao indicado.

   O valor APP5 corresponde ao nome interno do formulário Web: essas informações permitem descobrir a origem do indicado, ou seja, vincular o visitante ao formulário Web com base no qual foi criado.

1. A caixa de armazenamento permite coletar informações e armazená-las no banco de dados.

   ![Caixa de diálogo de armazenamento com o elemento Visitante selecionado nas opções de reconciliação para armazenar o indicado](assets/s_ncs_admin_survey_viral_sample_4b.png)

1. Em seguida, crie o modelo da entrega vinculado ao serviço de informação criado durante a etapa 1. Ele será selecionado no campo **[!UICONTROL Choose scenario]** do serviço de informações.

   O modelo da entrega usado para criar a mensagem de oferta de referência contém as seguintes informações:

   ![Convidar um modelo de entrega de amigo com um assunto e conteúdo do HTML que use campos de personalização](assets/s_ncs_admin_survey_viral_sample_7.png)

   Esse modelo tem as seguintes características:

   * Selecione a tabela do visitante como target mapping.

     ![Caixa de diálogo Selecionar destino com Visitantes (nms:visitor) selecionada como mapeamento de destino da entrega](assets/s_ncs_admin_survey_viral_sample_7b.png)

   * As informações de contato do indicado e as informações de quem indicou são obtidas na tabela do visitante. Elas são inseridas usando o botão de personalização.

     ![Menu Personalization no conteúdo de entrega, lista do submenu Visitante Sobrenome, Nome, Email e campos de Referenciador](assets/s_ncs_admin_survey_viral_sample_7a.png)

   * Esse modelo contém um link para o formulário da competição e o link de subscrição para o indicado se subscrever no boletim informativo.

     O link de subscrição é inserido por um bloco de personalização. Por padrão, ele permite subscrever perfis no serviço de **boletim informativo.** Esse bloco de personalização pode ser alterado para atender às suas necessidades, por exemplo, para subscrever o recipient a um serviço diferente.

   * O nome interno (&quot;quem indicou&quot; aqui) será usado no script de entrega da mensagem conforme mostrado abaixo.

   >[!NOTE]
   >
   >Consulte a [documentação do Campaign v8](https://experienceleague.adobe.com/docs/campaign/campaign-v8/send/create-templates.html?lang=pt-BR){target="_blank"} para obter mais informações sobre modelos de entrega.

1. Crie o segundo script para entregar as mensagens de subscrição.

   ![Caixa de script Referee de armazenamento e envio de mensagens, com código que enfileira a notificação de email de referência para o indicado](assets/s_ncs_admin_survey_viral_sample_7c.png)

   ```javascript
   // Updtate visitor to have a link to the referrer recipient
   ctx.recipient.visitor.@referrerId = ctx.recipient.@id
   ctx.recipient.visitor.@xtkschema = "nms:visitor"
   ctx.recipient.visitor.@_operation = "update" 
   ctx.recipient.visitor.@_key = "@id" 
   xtk.session.Write(ctx.recipient.visitor)
   
   // Send email to friend
   nms.delivery.QueueNotification("referrer",
   <delivery>
   <targets>
     <deliveryTarget>
       <targetPart type='query' exclusion='false' ignoreDeleteStatus='false'>
         <where>
           <condition expr={'@id IN ('+ ctx.recipient.visitor.@id +')' }/>
         </where>
       </targetPart>
      </deliveryTarget>
     </targets>
    </delivery>)
   ```

1. Publique o formulário da competição e envie um convite para os destinatários do público alvo inicial. Quando um deles convida um amigo, uma entrega com base no modelo de **oferta de indicação** é criado.

   ![Página de questionário concluída com uma seção Convidar um amigo e a lista de Entregas mostrando a entrega em andamento](assets/s_ncs_admin_survey_viral_sample_8.png)

   O indicado é adicionado à pasta do visitante no **[!UICONTROL Administration > Visitors node]**:

   ![Pasta Visitantes listando o indicado, com a guia Geral do visitante mostrando o nome, email e referenciador](assets/s_ncs_admin_survey_viral_sample_9.png)

   Seu perfil contém as informações inseridas por quem indicou. Ele é armazenado com base nas configurações inseridas no script de formulário. Se decidirem subscrever o boletim informativo, eles serão salvos na tabela de destinatários.
