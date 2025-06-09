---
title: Criar perfis de teste no Campaign
description: Saiba como criar e gerenciar perfis de teste no Adobe Campaign
feature: Audiences, Profiles, Seed Address, Proofs
role: User
level: Beginner
exl-id: 878b5963-100c-4dd7-97a0-c59a62c493b1
source-git-commit: e4f6c70ecdcf7414b5f49a43933cfd1c967a0905
workflow-type: tm+mt
source-wordcount: '928'
ht-degree: 55%

---

# Criar e gerenciar perfis de teste {#create-test-profiles}

## O que é um seed address? {#gs-seeds}

Os perfis de teste são criados como seed addresses. Eles são usados para direcionar destinatários que não correspondem aos critérios de direcionamento definidos. Os seed addresses permitem visualizar e testar a personalização e renderização antes de enviar o delivery, enviando provas.

Os seed addresses têm os seguintes benefícios:

* Substituição aleatória de campos com dados obtidos de perfis de recipients: permite inserir somente o endereço de email, por exemplo, na seção seed address e permite que o Campaign preencha automaticamente os outros campos no formulário do perfil. Saiba mais na [documentação do Campaign Classic v7](https://experienceleague.adobe.com/docs/campaign-classic/using/sending-messages/using-seed-addresses/use-case--selecting-seed-addresses-on-criteria.html?lang=pt-BR){target="_blank"}.
* Ao usar um fluxo de trabalho com funcionalidades de gestão de dados, os dados adicionais processados nas entregas podem ser inseridos no nível do seed address para forçar valores, evitando assim a substituição de valores aleatórios.
* Os seed addresses são excluídos automaticamente dos relatórios nas seguintes estatísticas da entrega: **[!UICONTROL Clicks]**, **[!UICONTROL Opens]**, **[!UICONTROL Unsubscriptions]**.

Esses seed addresses são adicionados ao target das entregas ao serem importados ou criados diretamente na entrega ou na campanha.

>[!NOTE]
>
>Os seed addresses não são criados na tabela de recipients, mas em uma tabela separada. Se a tabela de destinatários é estendida com novos dados, a tabela de seed addresses também deverá ser ampliada, assim como os mesmos dados. Caso contrário, os campos estendidos não são considerados para seed addresses.
>
>Um exemplo de como estender a tabela de seed addresses é apresentado na [documentação do Campaign Classic v7](https://experienceleague.adobe.com/docs/campaign-classic/using/sending-messages/using-seed-addresses/use-case--selecting-seed-addresses-on-criteria.html?lang=pt-BR){target="_blank"}.

## Criar seed addresses

Os seed addresses não são gerenciados por meio de perfis e destinos padrão, mas em um nó dedicado do Adobe Campaign Explorer: **[!UICONTROL Resources > Campaign management > Seed addresses]**. Você pode criar subpastas para organizar os seed addresses.

O Adobe Campaign também permite criar modelos de seed addresses que são importados para entregas ou campanhas e adaptados com base nas necessidades específicas das entregas e campanhas relacionadas. Consulte [Criar modelos de seed address](#creating-seed-address-templates).

### Definir endereços {#defining-addresses}

Para criar seed addresses, siga estas etapas:

1. Clique no botão **[!UICONTROL New]** acima da lista de seed addresses.
1. Insira os dados vinculados ao endereço nos campos correspondentes da guia **[!UICONTROL Recipient]**. Os campos disponíveis correspondem aos campos padrão nos perfis dos destinatários da entrega (tabela nms:recipient): sobrenome, nome, email, etc.

   >[!NOTE]
   >
   >O rótulo do endereço é preenchido automaticamente com o sobrenome e o nome que você definiu.
   >
   >Não é necessário inserir todos os campos de cada guia ao criar um seed address. Os elementos de personalização ausentes são inseridos aleatoriamente durante a análise de entrega.

1. Na guia **[!UICONTROL Address fields]**, insira os valores a serem inseridos nos logs de entrega durante a fase de análise, na tabela **[!UICONTROL nms:broadLog]**.

1. Na guia **[!UICONTROL Additional data]**, insira os dados de personalização usados para as entregas criadas nos workflows de gestão de dados, aos quais você deseja atribuir um valor específico.

   Verifique se os dados adicionais de destino foram definidos com um alias que comece com &#39;@&#39; na atividade de fluxo de trabalho **[!UICONTROL Enrichment]**. Caso contrário, você não poderá usá-los corretamente com seus seeds addresses na atividade de entrega.

### Criar modelos de seed address {#creating-seed-address-templates}

Você pode criar templates de endereço que podem ser importados e modificados para cada delivery. O processo é o mesmo que ao definir um novo seed address. A única diferença é que os templates de seed address devem ser armazenados em uma pasta do tipo &#39;template&#39;.

### Seed addresses para deliveries de correspondência direta {#direct-mail-seed-addresses}

Para [entregas de correspondência direta](../send/direct-mail.md), os seed addresses são adicionados durante a extração e combinados no documento de saída.

Para entregas de mala direta, o formato do arquivo de extração deve estar em conformidade com as seguintes limitações:

* Não deve usar a opção **[!UICONTROL Handle groupings (GROUP BY+HAVING)]**.

* Se as coleções de elemento forem extraídas, esses campos têm um valor vazio para os seed addresses, a menos que a opção **[!UICONTROL Single row (expert user)]** esteja selecionada.

## Adicionar seed addresses em um delivery{#seed-addresses-in-a-delivery}

Para adicionar seed addresses específicos em uma entrega, clique no link **[!UICONTROL To]** e selecione a guia **[!UICONTROL Seed addresses]** Seed addresses.

Há três modos de inserção possíveis:

1. Insira seed addresses únicos.  Para fazer isso, clique no botão **[!UICONTROL Add]** e defina o conteúdo dos campos de endereço. Repita para cada endereço.

1. Importe [modelos de seed address](#creating-seed-address-template) e adapte-os de acordo com suas necessidades. Para fazer isso, clique no link **[!UICONTROL Import seed templates...]** e selecione a pasta que contém os modelos de endereço.

   Se necessário, depois da execução, clique duas vezes neles ou no botão **[!UICONTROL Detail...]** para adaptar o conteúdo de cada endereço.

1. Crie uma condição para selecionar dinamicamente os endereços de controle a serem inseridos. Para fazer isso, clique no link **[!UICONTROL Edit the dynamic condition...]** e insira os parâmetros de seleção do seed address. Por exemplo, você pode incluir todos os seed addresses contidos em uma pasta específica ou seed addresses que pertencem a um departamento específico da sua organização.

   Um exemplo é apresentado na [documentação do Campaign Classic v7](https://experienceleague.adobe.com/docs/campaign-classic/using/sending-messages/using-seed-addresses/use-case--selecting-seed-addresses-on-criteria.html?lang=pt-BR){target="_blank"}.

Para entregas, você também pode personalizar a maneira como os endereços são inseridos no arquivo de extração. Por padrão, eles são inseridos na ordem de classificação do arquivo de saída, mas você pode optar por inseri-los no final ou no início do arquivo, ou aleatoriamente entre os destinatários do target principal.

## Adicionar seed addresses em uma campanha {#seed-addresses-in-a-campaign}

Para adicionar seed addresses a um target para uma campanha, selecione a operação e clique na guia **[!UICONTROL Edit]**.

Clique no link **[!UICONTROL Advanced campaign settings...]** e depois na guia **[!UICONTROL Seed addresses]**. Os seed addresses inseridos a partir da campanha são adicionados ao target de cada delivery na campanha.

## Seed addresses e tabela personalizada {#using-an-external-recipient-table}

Se a tabela da entrega for uma tabela externa, você precisará fazer configurações adicionais. O schema **[!UICONTROL nms:seedmember]** deve ser estendido. Uma guia é adicionada aos seed addresses para definir os campos adequados

Nesse caso, para adicionar seed addresses ao delivery, insira os campos adequados diretamente na guia correspondente ou importe os templates de endereços.

<!--The **nms:seedMember** schema extension is [this section](../../configuration/using/seed-addresses.md).-->
