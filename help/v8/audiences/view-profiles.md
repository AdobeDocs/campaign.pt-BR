---
title: Exibir perfis existentes no Campaign
description: Saiba como acessar dados de contato no Campaign
feature: Audiences, Profiles
role: User
level: Beginner
exl-id: 03f7a736-e0b9-4216-9550-507f10e6fcf6
version: Campaign v8, Campaign Classic v7
source-git-commit: ec1b41ccf532b044e75c69e795eabfb19a523ec2
workflow-type: tm+mt
source-wordcount: '452'
ht-degree: 4%

---

# Exibir perfis existentes {#view-profiles}

Navegue até **[!UICONTROL Profiles and targets]** para acessar destinatários armazenados no banco de dados do Adobe Campaign.

Nesta página, você pode [criar novo destinatário](create-profiles.md), editar um destinatário existente e acessar seus detalhes de perfil.

![](assets/profiles-and-targets.png)

Para manipulações de perfil mais avançadas, acesse a árvore do Campaign pelo link **[!UICONTROL Explorer]** na página inicial do Adobe Campaign.

![](assets/recipients-in-explorer.png)


>[!CAUTION]
>
>A tela Recipient integrada é definida por meio de um esquema XML e seu formulário associado. O esquema XML está armazenado no nó **[!UICONTROL Administration > Configuration > Data schemas]** da árvore do gerenciador do Adobe Campaign. Somente usuários especialistas podem fazer alterações nesses esquemas.
>

## Editar um perfil {#edit-a-profiles}

Selecione um perfil para exibir detalhes em uma nova guia.

![](assets/edit-a-profile.png)

Os dados relativos aos perfis são agrupados em guias. Essas guias e seu conteúdo dependem das configurações específicas e dos pacotes instalados.

Para um recipient incorporado típico, você pode acessar as seguintes guias:

* **[!UICONTROL General]**, para todos os dados gerais do perfil. Em particular, contém o sobrenome, nome, endereço de email, formato do email, etc.

  Esta guia também armazena o sinalizador **recusar** para o perfil: quando a opção **[!UICONTROL No longer contact (by any channel)]** é selecionada, o perfil fica em incluir na lista de bloqueios. Essas informações serão adicionadas aos dados de contato se o recipient clicar em um link de cancelamento de subscrição em um boletim informativo, por exemplo. Esse recipient não será mais direcionado em nenhum canal (email, correspondência direta etc.). Para obter mais informações, consulte [esta página](../send/quarantines.md).

* **Informações de contato**, que contêm o endereço de correspondência direta do perfil selecionado.

  Você pode verificar nesta tela o índice de qualidade do endereço e quantos erros o endereço contém. Essas informações são usadas diretamente pelo provedor de correspondência direta, com base no número de erros encontrados durante deliveries anteriores, e não podem ser alteradas manualmente.

* **Outros**, para campos específicos que podem ser personalizados e preenchidos dependendo das suas necessidades.

  Use o menu contextual **[!UICONTROL Field properties…]** para alterar os nomes dos campos e definir seus formatos.

  ![](assets/other-tab-field-properties.png)

  Insira as novas configurações conforme abaixo:

  ![](assets/change-field-properties.png)

  Verifique a atualização na interface do usuário:

  ![](assets/other-tab-updated.png)


  >[!CAUTION]
  >As alterações se aplicam a todos os destinatários.
  >


* **Assinaturas**, para todas as assinaturas ativas para serviços. Use a guia **Histórico** para acessar os detalhes de assinaturas e cancelamentos de assinaturas deste contato.

  ![](assets/subscription-tab.png)

  Saiba mais sobre Assinaturas [nesta seção](../start/subscriptions.md).

* **Entregas**, para todos os logs de entrega do perfil selecionado. Use esta guia para acessar o histórico de marketing do contato: rótulos, datas e status de todas as ações de entrega endereçadas ao perfil por todos os canais.


* **Rastreamento**, para todos os logs de rastreamento do perfil selecionado. Essas informações são usadas para rastrear o comportamento do perfil após os deliveries. Esta guia mostra o total cumulativo de todas as URLs rastreadas nas entregas. A lista é configurável e geralmente contém: o URL clicado, a data e hora do clique e o documento que continha o URL

  Saiba mais sobre o Rastreamento [nesta seção](../start/tracking.md).
