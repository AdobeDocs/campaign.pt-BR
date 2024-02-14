---
title: Exibir perfis existentes no Campaign
description: Saiba como acessar dados de contato no Campaign
feature: Audiences, Profiles
role: User
level: Beginner
exl-id: 03f7a736-e0b9-4216-9550-507f10e6fcf6
source-git-commit: b5574ba2d9fa520b701f7af4e34862304b825a66
workflow-type: tm+mt
source-wordcount: '552'
ht-degree: 6%

---

# Exibir perfis existentes{#view-profiles}

Navegue até **[!UICONTROL Profiles and targets]** para acessar destinatários armazenados no banco de dados do Adobe Campaign.

Nessa página, é possível [criar novo destinatário](create-profiles.md), edite um recipient existente e acesse os detalhes do perfil.

![](assets/profiles-and-targets.png)

Para manipulações de perfil mais avançadas, acesse a árvore do Campaign pelo **[!UICONTROL Explorer]** na página inicial do Adobe Campaign.

![](assets/recipients-in-explorer.png)


>[!CAUTION]
>
>A tela Recipient integrada é definida por meio de um esquema XML e seu formulário associado. O esquema XML é armazenado na variável **[!UICONTROL Administration > Configuration > Data schemas]** nó da árvore do explorador do Adobe Campaign. Somente usuários especialistas podem fazer alterações nesses esquemas.
>

## Editar um perfil{#edit-a-profiles}

Selecione um perfil para exibir detalhes em uma nova guia.

![](assets/edit-a-profile.png)

Os dados relativos aos perfis são agrupados em guias. Essas guias e seu conteúdo dependem das configurações específicas e dos pacotes instalados.

Para um recipient incorporado típico, você pode acessar as seguintes guias:

* **[!UICONTROL General]**, para todos os dados gerais do perfil. Em particular, contém o sobrenome, nome, endereço de email, formato do email, etc.

  Essa guia também armazena as **recusar** sinalizador do perfil: quando a variável **[!UICONTROL No longer contact (by any channel)]** for selecionada, o perfil estará em incluir na lista de bloqueios. Essas informações serão adicionadas aos dados de contato se o recipient clicar em um link de cancelamento de subscrição em um boletim informativo, por exemplo. Esse recipient não será mais direcionado em nenhum canal (email, correspondência direta etc.). Para obter mais informações, consulte [esta página](../send/quarantines.md).

* **Informações de contato**, que contém o endereço de correspondência direta do perfil selecionado.

  Você pode verificar nesta tela o índice de qualidade do endereço e quantos erros o endereço contém. Essas informações são usadas diretamente pelo provedor de correspondência direta, com base no número de erros encontrados durante deliveries anteriores, e não podem ser alteradas manualmente.

* **Outro**, para campos específicos que podem ser personalizados e preenchidos dependendo das suas necessidades.

  Use o **[!UICONTROL Field properties…]** menu contextual para alterar os nomes dos campos e definir seu formato.

  ![](assets/other-tab-field-properties.png)

  Insira as novas configurações conforme abaixo:

  ![](assets/change-field-properties.png)

  Verifique a atualização na interface do usuário:

  ![](assets/other-tab-updated.png)


  >[!CAUTION]
  >As alterações se aplicam a todos os destinatários.
  >


* **Assinaturas**, para todas as assinaturas ativas para serviços. Use o **Histórico** para acessar detalhes de assinaturas e cancelamentos de assinaturas deste contato.

  ![](assets/subscription-tab.png)

  Saiba mais sobre Assinaturas [nesta seção](../start/subscriptions.md).

* **Entregas**, para todos os logs de delivery do perfil selecionado. Use esta guia para acessar o histórico de marketing do contato: rótulos, datas e status de todas as ações de entrega endereçadas ao perfil por todos os canais.


* **Rastreamento**, para todos os logs de rastreamento do perfil selecionado. Essas informações são usadas para rastrear o comportamento do perfil após os deliveries. Esta guia mostra o total cumulativo de todas as URLs rastreadas nas entregas. A lista é configurável e geralmente contém: o URL clicado, a data e hora do clique e o documento que continha o URL

  Saiba mais sobre rastreamento [nesta seção](../start/tracking.md).


## Perfis ativos {#active-profiles}

Um perfil ativo é aquele com o qual o cliente tentou se comunicar nos últimos 12 meses por meio de qualquer canal. As métricas de licença são baseadas em perfis ativos. Saiba mais em [Descrição do produto Adobe Campaign](https://helpx.adobe.com/br/legal/product-descriptions/adobe-campaign-managed-cloud-services.html){target="_blank"}.

>[!CAUTION]
>
>* Um perfil que se tornou alvo de várias entregas é contado apenas uma vez.
>
>* Perfis direcionados no contexto de Marketing social no X (anteriormente conhecido como Twitter) não são considerados como perfis ativos.

Você pode monitorar o número de perfis ativos em sua instância diretamente do Painel de controle do Campaign. Para obter mais informações, consulte [Documentação do Painel de controle do Campaign](https://experienceleague.adobe.com/docs/control-panel/using/performance-monitoring/active-profiles-monitoring.html?lang=pt-BR){target="_blank"}.
