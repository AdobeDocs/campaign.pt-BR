---
title: Criar a primeira entrega
description: Criar a primeira entrega
feature: Email, Push, SMS, Direct Mail, Cross Channel Orchestration
role: User
level: Beginner
exl-id: 6cf8a929-637e-4e51-9160-5980ca727efb
source-git-commit: cf292ecd7d30862d7d195536ecc5be709fe037b3
workflow-type: tm+mt
source-wordcount: '1525'
ht-degree: 43%

---

# Criar a primeira entrega {#create-a-msg}

Nesta página, você aprenderá a criar uma única entrega de uma só vez. Você pode criar outros tipos de deliveries para atender aos seus casos de uso. Saiba mais sobre os diferentes tipos de entregas e como criá-los em [esta página](gs-message.md).

As principais etapas ao criar um delivery de uma só vez são:

1. **Criar uma nova entrega**. [Leia mais](#create-the-delivery)

1. **Defina o conteúdo da entrega**. [Leia mais](#content-of-the-delivery)

1. **Selecione a população alvo**. [Leia mais](#target-population)

Em seguida, você pode preparar, testar, enviar e monitorar suas mensagens.

>[!NOTE]
>
>As etapas descritas nesta seção pressupõem que todos os destinatários de destino e seus perfis estejam armazenados no banco de dados, exceto no caso de entrega externa (consulte [Seleção de destinatários externos](steps-defining-the-target-population.md#selecting-external-recipients)).

## Criar a entrega {#create-the-delivery}

Para criar um delivery, siga estas etapas:

1. Clique em **[!UICONTROL Create]** acima da lista de entregas. Ao criar um novo delivery, você deve selecionar o canal de delivery. Para fazer isso, selecione o template de entrega apropriado na lista suspensa no campo **[!UICONTROL Delivery template]**.

   ![](../send/assets/select-the-new-template.png)

   Um modelo integrado é fornecido para cada canal que você instalou: correspondência direta, email, telefone, canal móvel (SMS), X (Twitter), etc. Os canais disponíveis na lista dependem do contrato de licença.

   Você poderá criar novos modelos de entrega para pré-configurar parâmetros específicos de acordo com suas necessidades. Para obter mais informações, consulte [esta seção](about-templates.md).

1. Insira um nome para a entrega no campo **[!UICONTROL Label]**.

   (opcional) Um código de delivery também pode ser atribuído ao delivery. O nome do delivery e seu código estão visíveis na lista de deliveries, mas não estão expostos aos recipients.

1. (opcional) Adicione uma descrição no campo **[!UICONTROL Description]**.
1. (opcional) Selecione a natureza do delivery no campo relevante. Essas informações são úteis para o rastreamento da entrega: você poderá filtrar com base nesse critério na lista de entrega ou criar consultas usando esse critério de seleção.
1. Clique em **[!UICONTROL Continue]** para confirmar essas informações e exibir a janela de configuração de mensagem.

## Definir o conteúdo do delivery {#content-of-the-delivery}

O conteúdo da entrega está pronto para ser configurado. A definição do conteúdo da entrega é específica para cada canal. Para obter mais informações, consulte a seção dedicada:

* [Definir o conteúdo do email](../send/email.md)
* [Definir o conteúdo do SMS](../send/sms/sms-content.md)
* [Definir o conteúdo da correspondência direta](../send/direct-mail.md)
* [Desativar o conteúdo da notificação por push](../send/push.md)


## Definir o público-alvo {#target-population}

Para cada delivery, você poderá definir vários tipos de públicos-alvo:

* **Público principal**: perfis que recebem mensagens. [Saiba mais](#select-the-main-target)
* **Destino da prova**: perfis que recebem mensagens de prova. Uma prova é uma mensagem especial com a qual é possível testar um delivery antes de enviá-lo ao público alvo principal. [Saiba mais](#select-the-proof-target)

Além disso, no contexto de uma campanha de marketing, você pode adicionar:

* **Seed addresses**: destinatários que estão fora do destino da entrega, mas recebem a entrega. [Saiba mais](../audiences/test-profiles.md)
* **Grupos de controle**: população que não recebe a entrega, usada para rastrear o comportamento e o impacto da campanha. [Saiba mais](../../automation/campaigns/marketing-campaign-target.md#add-a-control-group).

### Selecionar os principais destinatários da entrega {#select-the-main-target}

Na maioria dos casos, o público-alvo principal é extraído do banco de dados do Adobe Campaign (modo padrão). No entanto, os destinatários também podem ser armazenados em um [arquivo externo](steps-defining-the-target-population.md#selecting-external-recipients).

Para selecionar os destinatários da entrega, siga as etapas abaixo:

1. No editor de entrega, selecione **[!UICONTROL To]**.
1. Se os destinatários estiverem armazenados no banco de dados, selecione a primeira opção.

   ![](../send/sms/assets/audience_to.png){zoomable="yes"}

1. Selecione o [target mapping](../audiences/target-mappings.md) na lista suspensa **[!UICONTROL Target mapping]**.
1. Clique no botão **[!UICONTROL Add]** para definir os filtros de restrição.

   ![](assets/target-type.png){width="60%" align="left" zoomable="yes"}

   Selecione um tipo de filtro e clique em **[!UICONTROL Next]** para definir as condições. Você pode exibir os destinatários filtrados na guia **[!UICONTROL Preview]**. Dependendo do tipo de target, o botão **[!UICONTROL Refine target]** permite combinar vários critérios de definição do target.

   Os seguintes tipos de target estão disponíveis:

   * **[!UICONTROL Filtering conditions]**: use esta opção para definir uma consulta e exibir o resultado. Saiba como criar uma consulta em [esta seção](../../automation/workflow/query.md).
   * **[!UICONTROL A list of recipients]**: use essa opção para direcionar a uma lista de perfis. Saiba mais sobre listas em [esta seção](../audiences/create-audiences.md).
   * **[!UICONTROL A recipient]**: use esta opção para selecionar um perfil específico no banco de dados.
   * **[!UICONTROL Recipients included in a folder]**: use esta opção para direcionar todos os perfis contidos em uma pasta específica.
   * **[!UICONTROL Recipients of a delivery]**: use essa opção para criar o público alvo dos recipients de uma entrega. Você deverá selecionar a entrega na lista:

     ![](assets/target-recipient-delivery.png)

   * **[!UICONTROL Delivery recipients belonging to a folder]**: use essa opção para criar o público-alvo a partir das entregas de recipients incluídos em uma pasta específica.

     ![](assets/target-delivery-folder.png)

     Você poderá filtrar o comportamento dos destinatários ao selecionar na lista suspensa:

     ![](assets/target-filter-behavior.png)

     >[!NOTE]
     >
     >A opção **[!UICONTROL Include sub-folders]** também permite direcionar as entregas contidas nas pastas localizadas na estrutura de árvore abaixo do nó selecionado.

   * **[!UICONTROL Subscribers of an information service]**: esta opção permite que você selecione um boletim informativo ao qual os destinatários devem ser inscritos para receberem a entrega que está sendo criada.

     ![](assets/target-service.png)

   * **[!UICONTROL User filters]**: essa opção permite que você acesse os filtros pré-configurados para usá-los como critérios de filtragem para perfis no banco de dados. Os filtros pré-configurados são apresentados [nesta seção](../audiences/create-filters.md#default-filters).
   * A opção **[!UICONTROL Exclude recipients from this segment]** permite apontar os recipients que não atendem aos critérios de target definidos. Para usar essa opção, selecione a caixa apropriada e, em seguida, aplique o direcionamento, conforme definido anteriormente, para excluir os perfis resultantes.

1. Insira um nome para esse direcionamento no campo **[!UICONTROL Label]**. Por padrão, o rótulo é o do primeiro critério de direcionamento. Ao combinar os critérios de filtragem, é recomendável usar um nome explícito.
1. Clique em **[!UICONTROL Finish]** para validar as opções de direcionamento.

   Os critérios de definição do target definidos são resumidos na seção central da guia de configuração do target principal. Clique em um critério para exibir seu conteúdo (configuração e visualização). Para excluir um critério, clique na cruz localizada depois de seu rótulo.

   ![](assets/target-remove-criterion.png)

#### Selecionar destinatários externos {#selecting-external-recipients}

Você pode enviar mensagens para perfis que não estão armazenados no banco de dados, mas em um arquivo externo. Por exemplo, para enviar um delivery a recipients importados de um arquivo de texto, siga estas etapas:

1. Clique no link **[!UICONTROL To]** para selecionar os destinatários da sua entrega.
1. Selecione a opção **[!UICONTROL Defined in an external file]**.
1. Selecione o arquivo que contém os recipients.
1. Ao importar os destinatários, clique no link **[!UICONTROL File format definition...]** para selecionar e configurar o arquivo externo.

   Para obter mais informações sobre importação de dados, consulte a [documentação do Campaign Classic v7](https://experienceleague.adobe.com/en/docs/campaign-classic/using/getting-started/importing-and-exporting-data/generic-imports-exports/executing-import-jobs#step-2---source-file-selection){target="_blank"}.

1. Clique em **[!UICONTROL Finish]** e configure sua entrega como uma entrega padrão.

>[!CAUTION]
>
>Ao definir o conteúdo da mensagem para delivery de email, não inclua o link para a mirror page: ele não poderá ser gerado nesse modo de delivery.

#### Definir configurações de exclusão {#define-exclusion-settings}

Ao definir o target de uma entrega, a guia **[!UICONTROL Exclusions]** é usada para limitar o número de mensagens. Os parâmetros padrão são recomendados, mas você poderá adaptar as configurações dependendo das suas necessidades. No entanto, essas opções só devem ser alteradas por um usuário expert para evitar qualquer erro ou mau uso.

Você poderá optar por excluir endereços que atingiram um determinado número de erros consecutivos ou cuja classificação de qualidade está abaixo de um limite especificado nessa janela. Você também poderá escolher se autoriza ou não endereços não qualificados para os quais nenhum dado foi retornado.

Clique no link **[!UICONTROL Edit...]** para modificar a configuração padrão.

![](assets/target-exclusion-settings.png)

As seguintes opções estão disponíveis:

* **[!UICONTROL Exclude duplicate addresses during delivery]**: esta opção está ativa por padrão e remove endereços de email duplicados durante a entrega. A estratégia aplicada pode variar de acordo com a forma como o Adobe Campaign é usado e o tipo de dados no banco de dados. O valor da opção pode ser configurado para cada template de delivery.
* **[!UICONTROL Exclude recipients who no longer want to be contacted]**, ou seja, destinatários cujos endereços de email estão na lista de bloqueios (“opt out”). Essa opção deve permanecer selecionada para observar a ética profissional de marketing eletrônico.
* **[!UICONTROL Exclude quarantined recipients]**: essa opção permite excluir do público-alvo quaisquer perfis com um endereço que esteja em quarentena. É altamente recomendável manter essa opção selecionada. Saiba mais sobre gerenciamento de quarentena em [esta seção](understanding-quarantine-management.md).
* **[!UICONTROL Limit delivery]** para um determinado número de mensagens. Essa opção permite que você insira o número máximo de mensagens a serem enviadas. Se o público-alvo exceder o número de mensagens indicadas, uma seleção aleatória será aplicada ao público-alvo. Para enviar todas as mensagens, mantenha esse valor como &#39;0&#39;.
* **[!UICONTROL Keep duplicate records (same identifier)]**: essa opção permite enviar várias entregas a destinatários que atendem a vários critérios de direcionamento.

### Selecionar os destinatários das mensagens de prova {#select-the-proof-target}

Para deliveries de email, você pode enviar provas para validar o conteúdo da mensagem. O envio de provas permite a verificação do link de opção de não participação, a mirror page e quaisquer outros links, validação da mensagem, verificação da exibição das imagens, detecção de possíveis erros, etc. Você também pode verificar seu design e renderização em diferentes dispositivos.

Uma prova é uma mensagem específica que permite testar uma mensagem antes de enviá-la para o público-alvo principal. Os recipients da prova são responsáveis pela aprovação da mensagem: renderização, conteúdo, configurações de personalização e configuração.

Para obter mais informações sobre recipients de prova e envio, consulte [esta seção](../send/preview-and-proof.md#send-proofs).

![](../send/assets/do-not-localize/how-to-video.png) [Conheça este recurso no vídeo](#seeds-and-proofs-video)


#### Tutorial em vídeo {#seeds-and-proofs-video}

Este vídeo mostra como adicionar seeds e provas a um email existente e o procedimento para o seu envio.

>[!VIDEO](https://video.tv.adobe.com/v/333404?quality=12)


Vídeos extras sobre procedimentos do Campaign Classic estão disponíveis [aqui](https://experienceleague.adobe.com/docs/campaign-classic-learn/tutorials/overview.html?lang=pt-BR).

## Preparar e validar o delivery {#validate-the-delivery}

Quando uma entrega for criada e configurada, você deverá validá-la antes de enviá-la para o target principal.

Para fazer isso:

1. **Analisar o delivery**: esta etapa permite preparar as mensagens para a entrega. [Saiba mais](../send/delivery-analysis.md).

1. **Enviar provas**: esta etapa permite controlar o conteúdo, os URLs, a personalização etc. [Saiba mais](../send/preview-and-proof.md).

>[!IMPORTANT]
>
>As duas etapas acima DEVEM SER executadas após cada modificação no conteúdo da mensagem.


## Configurar e enviar a entrega {#configuring-and-sending-the-delivery}

Acesse os parâmetros de delivery para definir mais configurações e definir como enviar suas mensagens. Você pode definir a prioridade do delivery, configurar o envio de ondas, definir as configurações de nova tentativa e testar o envio do delivery. Quando essa configuração estiver concluída, você poderá confirmar o envio. As mensagens são enviadas imediatamente ou com base no cronograma de delivery.

Saiba como definir as configurações de entrega em [esta página](../send/configure-and-send.md).
