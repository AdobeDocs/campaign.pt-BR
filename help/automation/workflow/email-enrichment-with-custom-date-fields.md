---
product: campaign
title: Enriquecimento de email com campos de data personalizados
description: Saiba como enriquecer emails com campos de data personalizados
feature: Workflows
role: User, Developer
version: Campaign v8, Campaign Classic v7
exl-id: 2bb3443c-37d8-4d49-9be1-81217f56823c
TQID: 'https://experienceleague.adobe.com/Mgo8JMtAXLW86GgkEsoVTtMSfUUKPsp-G9lL0p9JBg8'
product_v2:
  - id: dfc56824-e8b9-499e-85d4-21aedb507314
    internal-label: Campaign
  - id: d0e9f0b2-1f2b-4134-9844-49cd4e950f27
    internal-label: Campaign v8
feature_v2:
  - id: a658c786-869b-4194-a780-2594d663adda
    internal-label: Data management
subfeature_v2:
  - id: fcb46c0f-76e1-48bc-9dd0-fcf9d97526cf
    internal-label: Workflows
role_v2:
  - id: b69b2659-1057-424e-8fc5-ed9e016dc554
    internal-label: User
  - id: ff6a42d2-313e-452e-93a6-792e4fad9ff8
    internal-label: Developer
source-git-commit: e13b3537d149f2bdad7e9dd66768837e5c4b595b
workflow-type: tm+mt
source-wordcount: '790'
ht-degree: 65%
---
# Enriquecimento de email com campos de data personalizados{#email-enrichment-with-custom-date-fields}



Neste exemplo, queremos enviar um e-mail com campos de dados personalizados para os destinatários que celebram seus aniversários nesse mês. O e-mail incluirá um cupom válido por uma semana antes e depois de seus aniversários.

Precisamos direcionar os destinatários de uma lista que celebram os aniversariantes deste mês com uma atividade **[!UICONTROL Split]**. Em seguida, usando a atividade **[!UICONTROL Enrichment]**, o campo de dados personalizado atuará como as datas de validade no email para a oferta especial do cliente.

![Fluxo de trabalho: listar lido, Dividir com Subconjunto para Enriquecimento, depois Entrega de email e Complemento para Fim.](assets/uc_enrichment.png)

Para criar este exemplo, aplique as seguintes etapas:

1. Na guia **[!UICONTROL Targeting and workflows]** da campanha, arraste e solte uma atividade **[!UICONTROL Read list]** para direcionar a lista de destinatários.
1. A lista a ser processada pode ser especificada explicitamente, calculada por um script ou localizada dinamicamente, de acordo com as opções selecionadas e parâmetros definidos aqui.

   ![Ler atividade de lista com a lista especificada explicitamente e a seção de filtragem Source.](assets/uc_enrichment_1.png)

1. Adicione uma atividade **[!UICONTROL Split]** para diferenciar os destinatários que farão aniversário neste mês dos outros destinatários.
1. Para dividir a lista, na categoria **[!UICONTROL Filtering of selected records]**, selecione **[!UICONTROL Add a filtering condition on the inbound population]**. Em seguida, clique em **[!UICONTROL Edit]**.

   ![Guia Dividir Subconjuntos com Adicionar uma condição de filtragem na população de entrada e o link Editar realçado.](assets/uc_enrichment_2.png)

1. Selecione **[!UICONTROL Filtering conditions]** e clique no botão **[!UICONTROL Edit expression]** para filtrar o mês de aniversário do destinatário.

   ![Janela do elemento de destino com o botão Editar expressão realçado ao lado do campo Expressão.](assets/uc_enrichment_3.png)

1. Clique em **[!UICONTROL Advanced Selection]**, em **[!UICONTROL Edit the formula using an expression]** e adicione a seguinte expressão: Month(@birthDate).
1. Na coluna **[!UICONTROL Operator]**, selecione **[!UICONTROL equal to]**.
1. Filtre ainda mais sua condição, adicionando o mês **[!UICONTROL Value]** da data atual: Month(GetDate()).

   Isso consultará os destinatários cujo mês de aniversário corresponde ao mês atual.

   ![Condição do elemento de público alvo: mês de data de nascimento igual ao mês da data atual mais 14 dias.](assets/uc_enrichment_4.png)

1. Clique em **[!UICONTROL Finish]**. Em seguida, na guia **[!UICONTROL General]** da sua atividade **[!UICONTROL Split]**, clique em **[!UICONTROL Generate complement]**, na categoria **[!UICONTROL Results]**.

   Com o resultado **[!UICONTROL Complement]**, é possível adicionar uma atividade de entrega ou atualizar uma lista. Aqui, adicionamos uma atividade **[!UICONTROL End]**.

   ![Divida a guia Geral com a opção Gerar complemento marcada na seção Resultados.](assets/uc_enrichment_6.png)

Agora, é necessário configurar a atividade **[!UICONTROL Enrichment]**:

1. Adicione uma atividade **[!UICONTROL Enrichment]** depois do subconjunto para adicionar campos de data personalizados.

   ![Fluxo de trabalho com uma atividade Enrichment adicionada à transição de Subconjunto da atividade Split.](assets/uc_enrichment_7.png)

1. Abra a atividade **[!UICONTROL Enrichment]**. Na categoria **[!UICONTROL Complementary information]**, clique em **[!UICONTROL Add data]**.

   ![Atividade Enrichment com o link de dados Add realçada na seção Complementary information.](assets/uc_enrichment_8.png)

1. Selecione **[!UICONTROL Data linked to the filtering dimension]** e, em seguida, **[!UICONTROL Data of the filtering dimension]**.
1. Clique no botão **[!UICONTROL Add]**.

   ![Janela de dados a serem adicionados com o botão Adicionar realçado ao lado da lista Colunas de saída.](assets/uc_enrichment_9.png)

1. Adicione um **[!UICONTROL Label]**. Em seguida, na coluna **[!UICONTROL Expression]**, clique em **[!UICONTROL Edit expression]**.

   ![Colunas de saída com o rótulo Birthdate e o botão Editar expressão realçados na coluna Expression.](assets/uc_enrichment_10.png)

1. Primeiro, precisamos direcionar a semana antes da data de nascimento como a **Validity start date** com a seguinte **[!UICONTROL Expression]**: `SubDays([target/@birthDate], 7)`.

   ![Colunas de saída com o rótulo Birthdate e a expressão Date of birth (target/@birthDate).](assets/uc_enrichment_11.png)

1. Depois, para criar o campo personalizado **Validity end date** que direciona a semana após a data de nascimento, é necessário adicionar a **[!UICONTROL Expression]**: `AddDays([target/@birthDate], 7)`.

   É possível adicionar um rótulo à expressão.

   ![Colunas de saída listando Birthdate e a coluna Validity start date com sua expressão e alias.](assets/uc_enrichment_12.png)

1. Clique em **[!UICONTROL Ok]**. Agora o enriquecimento está pronto.

Após a atividade **[!UICONTROL Enrichment]**, você pode adicionar uma entrega. Nesse caso, adicionamos uma entrega de email para enviar uma oferta especial com datas de validade para celebrar os aniversários dos clientes no mês atual.

1. Arraste e solte uma atividade **[!UICONTROL Email delivery]** após a atividade **[!UICONTROL Enrichment]**.

   ![Fluxo de trabalho com uma atividade de entrega de email adicionada após a atividade de Enriquecimento.](assets/uc_enrichment_15.png)

1. Clique duas vezes na atividade **[!UICONTROL Email delivery]** para começar a personalizar a entrega.
1. Adicione um **[!UICONTROL Label]** à entrega e clique em **[!UICONTROL Continue]**.
1. Clique em **[!UICONTROL Save]** para criar a entrega de email.
1. Verifique na **[!UICONTROL Approval]** guia da entrega de e-mail **[!UICONTROL Properties]** se a opção **[!UICONTROL Confirm delivery before sending option]** está marcada.

   Em seguida, inicie o fluxo de trabalho para enriquecer a transição de saída com as informações de direcionamento.

   ![Guia Aprovações de propriedades de entrega com a opção Confirmar a entrega antes de enviar marcada.](assets/uc_enrichment_18.png)

Agora é possível começar a projetar a entrega de email com os campos de data personalizados criados na atividade **[!UICONTROL Enrichment]**.

1. Clique duas vezes na atividade **[!UICONTROL Email delivery]**.
1. Adicione suas extensões do target ao email. Elas devem estar dentro da seguinte expressão para configurar o formato de suas datas de validade:

   ```
   <%=
           formatDate(targetData.alias of your expression,"%2D.%2M")  %>
   ```

1. Clique no botão ![Personalization da barra de ferramentas com uma seta suspensa.](assets/uc_enrichment_16.png). Selecione **[!UICONTROL Target extension]** e então as datas de validade personalizadas criadas anteriormente com a atividade **[!UICONTROL Enrichment]** para adicionar a extensão à expressão formatDate.

   ![Menu do Personalization Submenu de extensão do Target listando a data de início da validade e a data de término da validade.](assets/uc_enrichment_19.png)

1. Configure seu conteúdo de e-mail conforme necessário.

   ![Conteúdo do HTML de email com expressões formatDate usando campos targetData para as datas de validade.](assets/uc_enrichment_17.png)

1. Visualize seu e-mail para verificar se os campos de data personalizados foram corretamente configurados.

   ![Guia Visualização de email mostrando a mensagem de aniversário com as datas de validade de 20/12 a 03/01 preenchidas.](assets/uc_enrichment_20.png)

Seu e-mail está pronto. É possível começar a enviar as provas e confirmar a entrega para enviar os e-mails de aniversário.
