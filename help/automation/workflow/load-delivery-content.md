---
product: campaign
title: Carregar conteúdo da entrega
description: Carregamento de conteúdo da entrega
feature: Workflows
role: User
version: Campaign v8, Campaign Classic v7
exl-id: 08febcbc-1703-4d36-89e1-32c903618084
TQID: https://experienceleague.adobe.com/iTopl-qZwqJdSMV-ZiJ3ymveNdCsAb8IR-SXQmt9VhI
product_v2:
  - id: dfc56824-e8b9-499e-85d4-21aedb507314
role_v2:
  - id: b69b2659-1057-424e-8fc5-ed9e016dc554
topic_v2:
  - id: eddd9b14-83bd-4ff4-9072-54a4a484abb7
source-git-commit: 15d7b12d07f84356fac7bee2a54a0057c5d00d41
workflow-type: tm+mt
source-wordcount: 304
ht-degree: 100%

---

# Carregar conteúdo da entrega{#loading-delivery-content}

Se o conteúdo de entrega estiver disponível em um arquivo HTML localizado em servidores Amazon S3, FTP ou SFTP, é possível carregar facilmente esse conteúdo nas entregas do Adobe Campaign.

Para fazer isso:

1. Se ainda não tiver definido uma conexão entre o Adobe Campaign e o servidor (S)FTP que hospeda os arquivos de conteúdo, crie uma nova conta externa S3, FTP ou SFTP em **[!UICONTROL Administration]** > **[!UICONTROL Platform]** > **[!UICONTROL External Accounts]**. Especifique nesta conta externa o endereço e as credenciais usadas para estabelecer a conexão com o servidor S3 ou (S)FTP.

   Veja um exemplo de uma conta externa S3:

   ![](assets/delivery_loadcontent_filetransfertexamples3.png)

1. Crie um novo fluxo de trabalho, por exemplo, em **[!UICONTROL Profiles and Targets]** > **[!UICONTROL Jobs]** > **[!UICONTROL Targeting workflows]**.
1. Adicione uma atividade **[!UICONTROL File transfer]** ao fluxo de trabalho e a configure especificando:

   * A conta externa a ser usada para se conectar ao servidor S3 ou (S)FTP.
   * O caminho do arquivo no servidor S3 ou (S)FTP.

   ![](assets/delivery_loadcontent_filetransfertexample.png)

1. Adicione uma atividade **[!UICONTROL Delivery]** e conecte-a à transição de saída da atividade **[!UICONTROL File transfer]**. Configure como apresentado a seguir:

   * Entrega: de acordo com suas necessidades, pode ser uma entrega específica que já foi criada no sistema ou uma nova entrega com base em um modelo existente.
   * Destinatários: neste exemplo, é considerado que o target é especificado na própria entrega.
   * Conteúdo: mesmo que o conteúdo seja importado na atividade anterior, selecione **[!UICONTROL Specified in the delivery]**. Como o conteúdo é importado diretamente de um arquivo localizado em um servidor remoto, ele não tem identificador quando processado pelo fluxo de trabalho e não pode ser identificado como proveniente do evento de entrada.
   * Ação a executar: selecione **[!UICONTROL Save]** para salvar a entrega e acessá-la a partir de **[!UICONTROL Campaign management]** > **[!UICONTROL Deliveries]** após a execução do fluxo de trabalho.

   ![](assets/delivery_loadcontent_activityexample.png)

1. Na guia **[!UICONTROL Script]** da atividade **[!UICONTROL Delivery]**, adicione o seguinte comando para carregar o conteúdo do arquivo importado na entrega:

   ```
   delivery.content.html.source=loadFile(vars.filename)
   ```

   ![](assets/delivery_loadcontent_script.png)

1. Salve e execute o fluxo de trabalho. Uma nova entrega com o conteúdo carregado é criada em **[!UICONTROL Campaign management]** > **[!UICONTROL Deliveries]**.

