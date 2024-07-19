---
audience: end-user
title: Criar um delivery de notificação por push avançado
description: Saiba como criar uma entrega de notificação por push avançada do Android com o Adobe Campaign Web
feature: Push
role: User
level: Beginner
exl-id: 42e3623b-b401-4fcc-80a7-ea38347fddc6
source-git-commit: 5236cc94e78db11b8975ad84c49594b282fdecf3
workflow-type: tm+mt
source-wordcount: '1157'
ht-degree: 13%

---

# Criar uma entrega de push avançada do Android {#rich-push}

>[!AVAILABILITY]
>
>Este recurso está em **Disponibilidade Limitada** (DL).

Com o Firebase Cloud Messaging, você pode escolher entre dois tipos de mensagens:

* O **[!UICONTROL Data message]** é manipulado pelo aplicativo cliente. Essas mensagens são enviadas diretamente para o aplicativo móvel, que gera e exibe uma notificação do Android no dispositivo. As mensagens de dados contêm somente as variáveis personalizadas do aplicativo.

* O **[!UICONTROL Notification message]**, manipulado automaticamente pelo SDK do FCM. O FCM exibe automaticamente a mensagem nos dispositivos dos usuários em nome do aplicativo do cliente. As mensagens de notificação contêm um conjunto predefinido de parâmetros e opções, mas ainda podem ser personalizadas com variáveis de aplicativo personalizadas.

## Definir o conteúdo da notificação {#push-message}

>[!IMPORTANT]
>
>Antes de criar uma Notificação por push avançada, primeiro é necessário configurar o conector. Consulte [esta página](https://experienceleague.adobe.com/en/docs/campaign-classic/using/sending-messages/sending-push-notifications/configure-the-mobile-app/configuring-the-mobile-application-android#configuring-external-account-android) para obter o procedimento detalhado.

Depois que o delivery de push é criado, é possível definir seu conteúdo. Três modelos estão disponíveis:

* **Modelo padrão** permite enviar notificações com um ícone simples e uma imagem associada.

* **Modelo Básico** pode incluir texto, imagens e botões em suas notificações.

* **Modelo do Carrossel** permite enviar notificações com texto e várias imagens que os usuários podem passar.

Navegue pelas guias abaixo para saber como redigir sua mensagem para cada modelo.

>[!BEGINTABS]

>[!TAB Modelo padrão]

1. No menu suspenso **[!UICONTROL Notification type]**, selecione **[!UICONTROL Default]**.

   ![](assets/rich_push_default.png)

1. Para redigir a mensagem, insira o texto nos campos **[!UICONTROL Title]** e **[!UICONTROL Message]**.

   ![](assets/rich_push_default_2.png)

1. Use campos de personalização dinâmicos para definir conteúdo, personalizar dados e adicionar conteúdo dinâmico. [Saiba mais](../send/personalize.md)

1. Para personalizar ainda mais sua notificação por push, configure o **[!UICONTROL Notification options]** e o **[!UICONTROL HTTPv1 additional options]** de sua notificação por push. [Saiba mais](#push-advanced)

   ![](assets/rich_push_default_3.png)

Depois de definir o conteúdo da mensagem, você pode usar assinantes de teste para pré-visualizar e testar a mensagem.

>[!TAB Modelo básico]

1. No menu suspenso **[!UICONTROL Notification Type]**, selecione **[!UICONTROL Basic]**.

   ![](assets/rich_push_basic.png)

1. Para redigir a mensagem, insira o texto nos campos **[!UICONTROL Title]**, **[!UICONTROL Message]** e **[!UICONTROL Expanded message]**.

   O texto **[!UICONTROL Message]** aparece no modo de exibição recolhido enquanto **[!UICONTROL Expanded message]** é exibido quando a notificação é expandida.

   ![](assets/rich_push_basic_2.png)

1. Use campos de personalização dinâmicos para definir conteúdo, personalizar dados e adicionar conteúdo dinâmico. [Saiba mais](../send/personalize.md)

1. No menu **[!UICONTROL Color options]**, insira os códigos de cor hexadecimais para **[!UICONTROL Title]**, **[!UICONTROL Message]** e **[!UICONTROL Background]**.

1. Adicione um **[!UICONTROL Remind later button]**, se necessário. Digite sua **[!UICONTROL Reminder Text]** e **Data** nos campos correspondentes.

   O campo **[!UICONTROL Reminder Date]** espera um valor que representa uma época em segundos.

1. Clique em **[!UICONTROL Add button]** e preencha os seguintes campos:

   * **[!UICONTROL Label]**: Texto exibido no botão.
   * **[!UICONTROL Link URI]**: especifique o URI a ser executado ao clicar no botão.

   Você tem a opção de incluir até três botões na sua notificação por push. Se você optar por **[!UICONTROL Remind later button]**, poderá incluir apenas um máximo de dois botões.

1. Selecione o **[!UICONTROL Link type]** da URL vinculada do seu botão:

   * **[!UICONTROL Web URL]**: as URLs da Web direcionam os usuários para o conteúdo online. Ao clicar em, eles solicitam que o navegador da Web padrão do dispositivo abra e navegue até o URL designado.

   * **[!UICONTROL Deeplink]**: deep links são URLs que direcionam os usuários para seções específicas em um aplicativo, mesmo que ele esteja fechado. Quando clicada, uma caixa de diálogo pode ser exibida, permitindo que os usuários escolham entre vários aplicativos capazes de manipular o link.

   * **[!UICONTROL Open App]**: as URLs de aplicativos abertos permitem que você se conecte diretamente ao conteúdo em um aplicativo. Ela permite que o aplicativo se estabeleça como o manipulador padrão para um tipo específico de link, ignorando a caixa de diálogo de desambiguação.

   Para obter mais informações sobre como lidar com Links de aplicativos da Android, consulte a [documentação de Desenvolvedores da Android](https://developer.android.com/training/app-links).

   ![](assets/rich_push_basic_3.png)

1. Para personalizar ainda mais sua notificação por push, configure o **[!UICONTROL Notification options]** e o **[!UICONTROL HTTPv1 additional options]** de sua notificação por push. [Saiba mais](#push-advanced)

   ![](assets/rich_push_basic_4.png)

Depois de definir o conteúdo da mensagem, você pode usar assinantes de teste para pré-visualizar e testar a mensagem.

>[!TAB Modelo do carrossel]

1. No menu suspenso **[!UICONTROL Notification Type]**, selecione **[!UICONTROL Carousel]**.

   ![](assets/rich_push_carousel.png)

1. Para redigir a mensagem, insira o texto nos campos **[!UICONTROL Title]**, **[!UICONTROL Message]** e **[!UICONTROL Expanded message]**.

   O texto **[!UICONTROL Message]** aparece no modo de exibição recolhido enquanto **[!UICONTROL Expanded message]** é exibido quando a notificação é expandida.

   ![](assets/rich_push_carousel_1.png)

1. Use o Editor de expressão para definir o conteúdo, personalizar os dados e adicionar conteúdo dinâmico. [Saiba mais](../send/personalize.md)

1. No menu **[!UICONTROL Color options]**, insira os códigos de cor hexadecimais para **[!UICONTROL Title]**, **[!UICONTROL Message]** e **[!UICONTROL Background]**.

1. Escolha como o **[!UICONTROL Carousel]** é operado:

   * **[!UICONTROL Auto]**: percorre automaticamente imagens como slides, fazendo a transição em intervalos predefinidos.
   * **[!UICONTROL Manual]**: permite que os usuários deslizem manualmente entre slides para navegar pelas imagens.

1. No menu suspenso **[!UICONTROL Layout]**, selecione a opção **[!UICONTROL Filmstrip]** para incluir visualizações das imagens anteriores e seguintes ao lado do slide principal.

1. Clique em **[!UICONTROL Add image]** e insira a URL da imagem, a URL do Texto e da Ação.

   Certifique-se de incluir no mínimo três imagens e no máximo cinco imagens.

   ![](assets/rich_push_carousel_2.png)

1. Para personalizar ainda mais sua notificação por push, configure o **[!UICONTROL Notification options]** e o **[!UICONTROL HTTPv1 additional options]** de sua notificação por push. [Saiba mais](#push-advanced)

   ![](assets/rich_push_carousel_3.png)

Depois de definir o conteúdo da mensagem, você pode usar assinantes de teste para pré-visualizar e testar a mensagem.

>[!ENDTABS]

## Configurações avançadas de notificações por push {#push-advanced}

### Opções de notificação {#notification-options}

| Parâmetro | Descrição |
|---------|---------|
| **[!UICONTROL Channel ID]** | Defina a ID do canal da sua notificação. O aplicativo deve criar um canal com essa ID de canal antes que qualquer notificação com essa ID de canal seja recebida. |
| **[!UICONTROL Icon]** | Defina o ícone da notificação que será exibido em seus dispositivos de perfis. |
| **[!UICONTROL Sound]** | Defina o som que será reproduzido quando o dispositivo receber sua notificação. |
| **[!UICONTROL Tag]** | Defina um identificador usado para substituir notificações existentes na gaveta de notificações. Isso ajuda a evitar o acúmulo de várias notificações e garante que somente a notificação relevante mais recente seja exibida. |
| **[!UICONTROL Color]** | Defina a cor do ícone da sua notificação com código de cor hexadecimal. |
| **[!UICONTROL Click action]** | Defina a ação associada a um clique do usuário em sua notificação. |
| **[!UICONTROL Notification background color]** | Defina a cor do plano de fundo da Notificação com os códigos de cor hexadecimal. |
| **[!UICONTROL Link type]** | <ul><li>URL da Web: os URLs da Web direcionam os usuários para conteúdo online. Ao clicar em, eles solicitam que o navegador da Web padrão do dispositivo abra e navegue até o URL designado.</li><li>Deeplink: deep links são URLs que orientam os usuários para seções específicas em um aplicativo, mesmo que ele esteja fechado. Quando clicada, uma caixa de diálogo pode ser exibida, permitindo que os usuários escolham entre vários aplicativos capazes de manipular o link.</li><li> Abrir aplicativo: as URLs abertas do aplicativo permitem que você se conecte diretamente ao conteúdo em um aplicativo. Ela permite que o aplicativo se estabeleça como o manipulador padrão para um tipo específico de link, ignorando a caixa de diálogo de desambiguação.</li></ul> |

### Opções adicionais do HTTPv1 {#additional-options}

| Parâmetro | Descrição |
|---------|---------|
| **[!UICONTROL Ticker]** | Defina o texto do ticker da sua notificação. Disponível somente para dispositivos definidos como Android 5.0 Lollipop. |
| **[!UICONTROL Sticky]** | Quando ativada, a notificação permanece visível mesmo depois que o usuário clica nela. <br>Se desativada, a notificação é automaticamente descartada quando o usuário interage com ela. O comportamento fixo permite que notificações importantes persistam na tela por períodos mais longos. |
| **[!UICONTROL Image]** | Defina o URL da imagem que será exibido na sua notificação. |
| **[!UICONTROL Notification Priority]** | Defina o nível de prioridade da sua notificação, que pode ser padrão, mínimo, baixo ou alto. O nível de prioridade determina a importância e a urgência da notificação, influenciando como ela é exibida e se pode ignorar determinadas configurações do sistema. Para obter mais informações, consulte a [documentação do FCM](https://firebase.google.com/docs/reference/fcm/rest/v1/projects.messages#notificationpriority). |
| **[!UICONTROL Notification Count]** | Defina o número de novas informações não lidas a serem exibidas diretamente no ícone do aplicativo. Isso permite que o usuário veja rapidamente o número de notificações pendentes. |
| **[!UICONTROL Visibility]** | Defina o nível de visibilidade de sua notificação, que pode ser público, privado ou secreto. O nível de visibilidade determina quanto do conteúdo da notificação é exibido na tela de bloqueio e em outras áreas confidenciais. Para obter mais informações, consulte a [documentação do FCM](https://firebase.google.com/docs/reference/fcm/rest/v1/projects.messages#visibility). |
| **[!UICONTROL Application variables]** | Permite definir o comportamento da notificação. Essas variáveis são totalmente personalizáveis e incluídas com parte do conteúdo da mensagem enviada para o dispositivo móvel. |
