---
title: Mensagens transacionais do Campaign
description: Introdução a mensagens transacionais
feature: Transactional Messaging
role: User
level: Beginner, Intermediate
exl-id: 06fdb279-3776-433f-8d27-33d016473dee
source-git-commit: 3c7455f348468a8f00fb853a3269a1d63b81e7b8
workflow-type: tm+mt
source-wordcount: '1491'
ht-degree: 63%

---

# Introdução a mensagens transacionais{#send-transactional-messages}

O envio de mensagens transacionais (Centro de mensagens) é um módulo do Campaign criado para gerenciar mensagens por disparo. Essas notificações são geradas a partir de eventos acionados dos sistemas de informações e podem ser: fatura, confirmação de pedido, confirmação de remessa, alteração de senha, notificação de indisponibilidade de produto, extrato de conta, criação de conta de site etc.

![](../assets/do-not-localize/speech.png)  Como usuário do Managed Cloud Services, [Adobe de contato](../start/campaign-faq.md#support){target="_blank"} para configurar as mensagens transacionais do Campaign no seu ambiente.

As mensagens transacionais são usadas para enviar:

* notificações, como confirmações de pedidos ou redefinições de senha, por exemplo
* uma resposta individual em tempo real a uma ação do cliente
* conteúdo não promocional

As configurações de mensagens transacionais são detalhadas em [nesta seção](../config/transactional-msg-settings.md).

Entender a arquitetura de mensagens transacionais em [esta página](../architecture/architecture.md#transac-msg-archi).

## Princípio operacional das mensagens transacionais {#transactional-messaging-operating-principle}

O módulo de mensagens transacionais do Adobe Campaign é integrado a um sistema de informações que retorna eventos que serão transformados em mensagens transacionais personalizadas. Essas mensagens podem ser enviadas individualmente ou em lotes por email, SMS ou notificações por push.

Por exemplo, imagine que você é uma empresa com um site onde os clientes podem comprar produtos.

O Adobe Campaign permite enviar um email de notificação para clientes que adicionaram produtos ao carrinho. Quando um deles sai do site sem concluir a compra (evento externo que aciona um evento do Campaign), um email de abandono de carrinho é enviado automaticamente a eles (entrega de mensagem transacional).

As principais etapas para colocar isso em prática são detalhadas abaixo:

1. [Crie um tipo de evento](#create-event-types).
1. [Criar o modelo de mensagem](#create-message-template). Você deve vincular um evento à sua mensagem durante essa etapa.
1. [Testar a mensagem](#test-message-template).
1. [Publicar o modelo da mensagem](#publish-message-template).

Depois de criar e publicar o modelo de mensagem transacional, se um evento correspondente for acionado, os dados relevantes serão enviados para o Campaign por meio do PushEvent e PushEvents [Métodos SOAP](../send/event-description.md)e o delivery é enviado aos recipients direcionados.

## Criar tipos de evento {#create-event-types}

Para garantir que cada evento possa ser alterado em uma mensagem personalizada, primeiro é necessário criar **tipos de evento**.

Ao [criar um modelo de mensagem](#create-message-template), você selecionará o tipo de evento que corresponde à mensagem que deseja enviar.

>[!CAUTION]
>
>Você deve criar tipos de evento antes de poder usá-los em modelos de mensagem.

Para criar tipos de evento que serão processados pelo Adobe Campaign, siga as etapas abaixo:

1. Navegue até o **[!UICONTROL Administration > Platform > Enumerations]** pasta do explorador do Campaign.
1. Selecione o **[!UICONTROL Event type]** lista discriminada da lista.
1. Clique em **[!UICONTROL Add]** para criar um valor de lista discriminada. Pode ser uma confirmação de pedido, uma alteração de senha, uma alteração de entrega de pedido etc.

   ![](assets/messagecenter_eventtype_enum_001.png)

   >[!CAUTION]
   >
   >Cada tipo de evento deve corresponder a um valor na lista discriminada **[!UICONTROL Event type]**.

1. Após a criação dos valores da lista discriminada, faça logoff e logon novamente na instância para que a criação seja efetivada.

>[!NOTE]
>
>Saiba mais sobre enumerações em [esta página](../../v8/config/ui-settings.md#enumerations).


## Definir um template de mensagem transacional {#create-message-template}

Cada evento pode acionar uma mensagem personalizada. Para que isso aconteça, você precisa criar um template de mensagem para corresponder a cada tipo de evento. Os templates contêm as informações necessárias para personalizar a mensagem transacional. Você também pode usar templates para testar a pré-visualização da mensagem e enviar provas usando seed addresses antes de entregar ao target final.

### Criar o modelo

Para criar um template de mensagem, siga as etapas abaixo:

1. Acesse a pasta **[!UICONTROL Message Center >Transactional message templates]** da árvore do Adobe Campaign.
1. Clique com o botão direito do mouse na lista de templates de mensagem transacional e selecione **[!UICONTROL New]** no menu suspenso ou clique no botão **[!UICONTROL New]** acima da lista de templates de mensagem transacional.

   ![](assets/messagecenter_create_model_001.png)

1. Na janela do delivery, selecione o template do delivery apropriado para o canal que deseja usar.

   ![](assets/messagecenter_create_model_002.png)

1. Altere seu rótulo se necessário.
1. Selecione o tipo de evento que corresponda à mensagem a ser enviada. Os tipos de evento destinados a serem processados pelo Adobe Campaign devem ser criados previamente. [Saiba mais](#create-event-types)

   ![](assets/messagecenter_create_model_003.png)

   >[!CAUTION]
   >
   >Um tipo de evento nunca deve estar vinculado a mais de um template.

1. Insira uma natureza e uma descrição, depois clique em **[!UICONTROL Continue]** para criar o corpo da mensagem.

### Criar o conteúdo{#create-message-content}

A definição do conteúdo da mensagem transacional é a mesma de todos os deliveries no Adobe Campaign. Por exemplo, para um delivery de email, você pode criar conteúdo em formato HTML ou texto, adicionar anexos ou personalizar o objeto do delivery. [Saiba mais](../start/create-message.md).

>[!CAUTION]
>
>As imagens incluídas na mensagem devem ser acessíveis publicamente. O Adobe Campaign não fornece nenhum mecanismo de carregamento de imagem para mensagens transacionais.\
>Ao contrário do JSSP ou webApp, `<%=`não tem nenhum escape padrão.
>
>Você precisa escapar cada dado que vem do evento corretamente. Este escape depende da forma como esse campo é usado. Por exemplo, dentro de uma URL, use encodeURIComponent. Para ser exibido no HTML, você pode usar escapeXMLString.

Após definir o conteúdo da mensagem, você pode integrar as informações do evento no corpo da mensagem e personalizá-lo. As informações do evento são inseridas no corpo do texto graças às tags de personalização.

![](assets/messagecenter_create_content.png)

* Todos os campos de personalização vêm da carga.
* É possível referenciar um ou vários blocos de personalização em uma mensagem transacional. <!--The block content will be added to the delivery content during the publication to the execution instance.-->

Para inserir tags de personalização no corpo de uma mensagem de email, siga as etapas abaixo:

1. No template de mensagem, clique na guia que corresponde ao formato do email (HTML ou texto).
1. Insira o corpo da mensagem.
1. No corpo do texto, insira a tag usando os menus **[!UICONTROL Real time events>Event XML]**.

   ![](assets/messagecenter_create_custo_1.png)

1. Preencha a tag usando a seguinte sintaxe: **element name**.@**attribute name** como mostrado abaixo.

   ![](assets/messagecenter_create_custo_2.png)

## Testar o modelo de mensagem transacional {#test-message-template}

### Adicionar seed addresses{#add-seeds}

Um seed address permite exibir uma pré-visualização da mensagem, enviar uma prova e testar a personalização da mensagem antes de enviar a mensagem. Os seed addresses estão vinculados ao delivery e não podem ser usados para outros deliveries.

1. No modelo de mensagem transacional, clique no botão **[!UICONTROL Seed addresses]** e clique na guia **[!UICONTROL Add]** botão.

   ![](assets/messagecenter_create_seed_1.png)

1. Atribua um rótulo a ele para facilitar a seleção posteriormente e, em seguida, insira o seed address (email ou celular, dependendo do canal de comunicação).

1. Digite o identificador externo: esse campo opcional permite inserir uma chave de negócios (ID exclusiva, nome + email, etc.) que é comum a todos os aplicativos em seu site, usado para identificar seus perfis. Se esse campo também estiver presente no banco de dados de marketing do Adobe Campaign, você poderá reconciliar um evento com um perfil no banco de dados.

   ![](assets/messagecenter_create_seed_2.png)

1. Inserir dados de teste. Consulte [esta seção](#personalization-data).

   ![](assets/messagecenter_create_custo_3.png)

1. Clique em **[!UICONTROL Ok]** para confirmar a criação do seed address.

1. Repita o processo para criar quantos endereços forem necessários.

   ![](assets/messagecenter_create_seed_6.png)

Depois que os endereços forem criados, você poderá acessar sua pré-visualização e personalização.

<!--

### Add personalization data{#personalization-data}

You can add data in the message template to test transactional message personalization. This will allow you to generate a preview or send a proof. If you install the **Deliverability** module, this data allows you to display a rendering of the messages for various desktop, web or mobile clients.

The purpose of this data is to test your messages before their final delivery. These messages do not coincide with actual data to be processed by Message Center.

However, the XML structure must be identical to that of the event stored in the execution instance, as shown below. 

![](assets/messagecenter_create_custo_4.png)

This information enables you to personalize message content using personalization tags.

1. In the message template, click the **[!UICONTROL Seed addresses]** tab.
1. In the event content, enter the test information in XML format.

   ![](assets/messagecenter_create_custo_3.png)
-->

### Pré-visualizar sua mensagem transacional{#transactional-message-preview}

Após criar um ou mais seed addresses e o corpo da mensagem, é possível pré-visualizar a mensagem e verificar sua personalização.

1. No modelo de mensagem, clique no botão **[!UICONTROL Preview]** e selecione **[!UICONTROL A seed address]** na lista suspensa.

   ![](assets/messagecenter_preview_1.png)

1. Selecione o seed address criado anteriormente para exibir a mensagem personalizada.

   ![](assets/messagecenter_create_seed_7.png)

### Enviar uma prova

Você pode testar a entrega de mensagens enviando uma prova para um seed address criado anteriormente.

O envio de uma prova envolve o mesmo processo de qualquer delivery. Saiba mais sobre provas no [nesta seção](../send/preview-and-proof.md).

No entanto, para enviar uma prova de mensagem transacional, é necessário realizar as seguintes operações:

* Criar um ou mais [seed addresses](#add-seeds) com dados de teste de personalização
* Criar o conteúdo da mensagem

Para enviar a prova:

1. Clique no botão **[!UICONTROL Send a proof]** na janela do delivery.
1. Analise o delivery.
1. Corrija qualquer erro e confirme o delivery.

   ![](assets/messagecenter_send_proof_001.png)

1. Verifique se a mensagem foi entregue ao seed address e se seu conteúdo está em conformidade com sua configuração.

   ![](assets/messagecenter_send_proof_002.png)

É possível acessar as provas em cada template através da guia **[!UICONTROL Audit]**.

![](assets/messagecenter_send_proof_003.png)

## Publicar o modelo {#publish-message-template}

Quando o modelo de mensagem foi criado<!-- on the control instance--> estiver concluído, você poderá publicá-lo, o que permitirá enviar mensagens vinculadas a eventos em lote e em tempo real.

<!--This process will also publish it on all execution instances.

NOTE: When publishing transactional message templates, typology rules are also automatically published on the execution instances.

Publication lets you automatically create two message templates on the execution instances, which will allow you to send messages linked to real-time and batch events.-->

>[!CAUTION]
>
>Sempre que fizer alterações em um modelo, publique-o novamente para que essas alterações estejam em vigor durante a entrega da mensagem transacional.

1. Vá até a pasta **[!UICONTROL Message Center > Transactional message templates]** da árvore.
1. Selecione o template que deseja publicar<!--on your execution instances-->.
1. Clique em **[!UICONTROL Publish]**.

   ![](assets/messagecenter_publish_template.png)

Quando a publicação estiver concluída, ambos os templates de mensagem que serão aplicados em eventos batch e em tempo real são criados no **[!UICONTROL Administration > Production > Message Center Execution> Default > Transactional message templates]** pasta.

![](assets/messagecenter_deployed_model.png)

Depois que um modelo for publicado, se o evento correspondente for acionado, o Adobe Campaign<!--execution instance--> O receberá o evento, o vinculará ao template transacional e enviará a mensagem transacional correspondente a cada recipient.

<!--
>[!NOTE]
>
>If you replace an existing field of the transactional message template, such as the sender address, with an empty value, the corresponding field on the execution instance(s) will not be updated once the transactional message is published again. It will still contain the previous value.
>
>However, if you add a non-empty value, the corresponding field will be updated as usual after the next publication.
-->

## Cancelar a publicação de um modelo

Depois que um modelo de mensagem é publicado <!--on the execution instances-->, ela pode ter a publicação desfeita.

* Na verdade, um modelo publicado ainda poderá ser chamado se o evento correspondente for acionado: se você não estiver mais usando um modelo de mensagem, será recomendável desfazer a publicação. Dessa forma, você pode evitar o envio de uma mensagem transacional indesejada por engano.

   Por exemplo, você publicou um template de mensagem que só usa para campanhas de Natal. Talvez você queira desfazer a publicação depois que o período de Natal acabar e publicá-lo novamente no próximo ano.

* Além disso, não é possível excluir um template de mensagem transacional que tenha o status **[!UICONTROL Published]**. Você deve desfazer a publicação primeiro.

Para desfazer a publicação de um template de mensagem transacional, siga as etapas abaixo.

1. Navegue até a pasta **[!UICONTROL Message Center > Transactional message templates]**.
1. Selecione o modelo para desfazer a publicação.
1. Clique em **[!UICONTROL Unpublish]**.
1. Clique em **[!UICONTROL Start]**.

![](assets/message-center-unpublish.png)

O status do template de mensagem transacional muda de **[!UICONTROL Published]** para **[!UICONTROL Being edited]**.

Depois de desfazer a publicação:

* Ambos os modelos de mensagem (aplicados a eventos de tipo em lote e em tempo real) são excluídos<!-- from each execution instance-->.

   Eles não aparecem mais na pasta **[!UICONTROL Administration > Production > Message Center Execution > Default > Transactional message templates]**.

* Após cancelar a publicação de um modelo, você pode excluí-lo<!-- from the control instance-->.

   Para fazer isso, selecione-o na lista e clique no botão **[!UICONTROL Delete]** na parte superior direita da tela.
