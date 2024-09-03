---
title: Selecionar público por SMS
description: Saiba como configurar o público-alvo de uma entrega de SMS
feature: SMS
role: User
level: Beginner, Intermediate
source-git-commit: 24a6d56a79995cd0113d8438d1bd3314a3872e35
workflow-type: tm+mt
source-wordcount: '457'
ht-degree: 17%

---


# Selecionar a audiência da entrega de SMS {#sms-audience}

Antes de selecionar seu público-alvo, [saiba mais sobre o público-alvo aqui](../../audiences/gs-audiences.md).

Na maioria dos casos, o target principal de um delivery é extraído do banco de dados do Adobe Campaign (modo padrão). No entanto, o público-alvo também pode ser armazenado em um arquivo externo. [Saiba mais nesta seção](#external-audience).

## Público-alvo no Adobe Campaign

Para selecionar o público do seu delivery, siga as etapas abaixo:

1. No editor de entrega, clique no link **[!UICONTROL To]**. Você terá uma janela **[!UICONTROL Select target]** aberta

1. Como o público é armazenado no banco de dados do Adobe Campaign, na guia **[!UICONTROL Main target]**, escolha a opção **[!UICONTROL Defined in the database]**.

   ![](assets/audience_to.png){zoomable="yes"}

1. Selecione o **[!UICONTROL Target mapping]** na lista suspensa. O target mapping padrão do Adobe Campaign é Destinatários, com base no esquema **[!UICONTROL nms:recipient]**.

   Outros target mappings estão disponíveis e alguns podem ser relacionados à sua configuração específica. Para obter mais informações sobre target mappings, consulte [Trabalhar com target mappings](../../audiences/target-mappings.md).

1. Clique no botão **[!UICONTROL Add]** para definir os filtros de restrição.

   Em seguida, é possível selecionar o tipo de filtragem a ser aplicado:

   ![](assets/audience_filters.png){zoomable="yes"}

   Para usar um tipo de destino, selecione-o e clique no botão **[!UICONTROL Next]**.

   Estes são os tipos de target oferecidos por padrão:

   * **[!UICONTROL Filtering conditions]**: permite que você defina uma consulta e exiba o resultado.
   * **[!UICONTROL A list of recipients]**: permite selecionar uma lista preparada contendo seu público
   * **[!UICONTROL A recipient]**: permite selecionar diretamente um destinatário na tabela.
   * **[!UICONTROL Recipients included in a folder]**: permite selecionar uma pasta na árvore de navegação do explorador
   * **[!UICONTROL Recipients of a delivery]**: permite selecionar a audiência de uma entrega anterior
   * **[!UICONTROL Recipients of deliveries belonging to a folder]**: permite selecionar a audiência de todas as entregas em uma determinada pasta
   * **[!UICONTROL Subscribers of an information service]**: esta opção permite que você selecione um boletim informativo ao qual os destinatários devem ser inscritos para receberem a entrega que está sendo criada.
   * **[!UICONTROL User filters]**: permite usar os filtros predefinidos.

   A opção **[!UICONTROL Exclude recipients from this segment]** permite apontar os destinatários que não atendem aos critérios de target definidos. Para usar essa opção, selecione a caixa apropriada e, em seguida, aplique o direcionamento, conforme definido anteriormente, para excluir os perfis resultantes.

1. Insira o nome do público no campo de rótulo e clique no botão **[!UICONTROL Finish]** para validar o público.

   ![](assets/audience_finish.png){zoomable="yes"}

   Você pode adicionar a população alvo quantas forem necessárias ao clicar novamente no botão **[!UICONTROL Add]**. Você também pode excluir alguns deles clicando na cruz localizada depois de seu rótulo.

## Público-alvo em um arquivo externo {#external-audience}

Você pode usar o Adobe Campaign para enviar uma entrega em um público-alvo que não esteja em seu banco de dados, mas em um arquivo externo.

Estas são as etapas:

1. No editor de entrega, clique no link **[!UICONTROL To]**. Você terá uma janela **[!UICONTROL Select target]** aberta

1. Escolha a opção **[!UICONTROL Defined in an external file]**.

   ![](assets/audience_externalfile.png){zoomable="yes"}

1. Por padrão, os destinatários são importados do banco de dados. Nesse caso, você precisa selecionar o **[!UICONTROL Target mapping]**. Para obter mais informações sobre target mappings, consulte [Trabalhar com target mappings](../../audiences/target-mappings.md).

   Caso contrário, você também pode escolher **[!UICONTROL Do not import the recipients into the database]**.

1. Ao importar o arquivo, clique no link **[!UICONTROL File format definition…]** para selecionar e configurar o arquivo externo.

1. Clique no botão **[!UICONTROL Finish]** para validar o público-alvo.
