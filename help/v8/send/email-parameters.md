---
title: Parâmetros de email no Adobe Campaign
description: Saiba mais sobre as opções e configurações específicas do delivery de email no Adobe Campaign.
feature: Email
role: User
level: Beginner, Intermediate, Experienced
source-git-commit: 44f30f753e3ed75b7e56caf7bd8cdfa7cbee5c35
workflow-type: tm+mt
source-wordcount: '840'
ht-degree: 50%

---

# Parâmetros de email {#email-parameters}

Esta seção apresenta as opções e os parâmetros disponíveis nas propriedades de delivery específicas para delivery de email.

## Usar Email Cco {#email-bcc}

<!--
>[!NOTE]
>
>This capability is available starting Campaign v8.3. To check your version, refer to [this section](../start/compatibility-matrix.md#how-to-check-your-campaign-version-and-buildversion)-->

Você pode configurar o Adobe Campaign para manter uma cópia dos emails enviados da sua plataforma.

O próprio Adobe Campaign não gerencia arquivos arquivados. Ele permite enviar as mensagens de sua escolha para um endereço de email CCO dedicado (cópia oculta), de onde elas podem ser processadas e arquivadas usando um sistema externo. Os arquivos .eml correspondentes aos emails enviados podem ser transferidos para um servidor remoto, como um servidor de email SMTP.

>[!CAUTION]
>
>Por motivos de privacidade, os emails com CCO devem ser processados por um sistema de arquivamento capaz de armazenar informações de identificação pessoal (PII) seguras.

O destino do arquivamento é o endereço de email CCO de sua escolha, que permanecerá invisível para os recipients do delivery.

![](../assets/do-not-localize/speech.png)  Como usuário do Managed Cloud Services, [Adobe de contato](../start/campaign-faq.md#support){target="_blank"} para comunicar o endereço de email CCO que será usado para arquivamento.

Depois que o endereço de email de CCO for definido, você deverá ativar a opção dedicada no nível do delivery.

>[!CAUTION]
>
>**[!UICONTROL Email BCC]** não está ativado por padrão. Você precisa ativá-lo manualmente no delivery de email ou no template do delivery.

Para fazer isso, siga as etapas abaixo:

1. Ir para **[!UICONTROL Campaign Management]** > **[!UICONTROL Deliveries]** ou **[!UICONTROL Resources]** > **[!UICONTROL Templates]** > **[!UICONTROL Delivery templates]**.
1. Selecione o delivery de sua escolha ou duplique o predefinido **[!UICONTROL Email delivery]** e selecione o template duplicado.
1. Clique no botão **[!UICONTROL Properties]**.
1. Selecione a guia **[!UICONTROL Delivery]**.
1. Marque a opção **[!UICONTROL Email BCC]**.

   ![](assets/email-bcc.png)

1. Selecione **[!UICONTROL Ok]**.

Uma cópia de todas as mensagens enviadas para cada delivery com base neste modelo será enviada para o endereço Cco de email que foi configurado.

Observe as seguintes especificidades e recomendações:

* Você só pode usar um endereço de email CCO.

* Verifique se o endereço CCo tem capacidade de recepção suficiente para arquivar todos os emails enviados.

* Email Cco <!--with Enhanced MTA--> O envia para o endereço de email CCO antes de entregar aos recipients, o que pode resultar no envio de mensagens com CCO, mesmo que os deliveries originais possam ter sido rejeitados. Para obter mais informações sobre rejeições, consulte [Entender as falhas de delivery](delivery-failures.md).

* Se os emails enviados para o endereço CCo forem abertos e clicados, isso será considerado no **[!UICONTROL Total opens]** e **[!UICONTROL Clicks]** da análise de envio, o que poderá causar alguns erros de cálculo.

<!--Only successfully sent emails are taken in account, bounces are not.-->

## Selecionar formatos de mensagem {#selecting-message-formats}

Você pode alterar o formato das mensagens de email enviadas. Para fazer isso, edite as propriedades do delivery e clique na guia **[!UICONTROL Delivery]**.

![](assets/email-message-format.png)

Selecione o formato do email na seção inferior da janela:

* **[!UICONTROL Use recipient preferences]** (modo padrão)

  O formato da mensagem é definido de acordo com os dados armazenados no perfil do recipient e armazenado por padrão no campo **[!UICONTROL email format]** (@emailFormat). Se um recipient deseja receber mensagens em determinado formato, esse será o formato enviado. Se o campo não estiver preenchido, uma mensagem multipart-alternative será enviada (veja abaixo).

* **[!UICONTROL Let recipient mail client choose the most appropriate format]**

  A mensagem contém os dois formatos: texto e HTML. O formato exibido no recebimento depende da configuração do software de email do recipient (multipart-alternative).

  >[!IMPORTANT]
  >
  >Essa opção inclui ambas as versões do documento. Portanto, reduz a taxa de transferência do delivery, pois o tamanho da mensagem é maior.

* **[!UICONTROL Send all messages in text format]**

  A mensagem é enviada em formato de texto. O formato HTML não será enviado, mas usado somente para a mirror page quando o recipient clicar na mensagem.

<!--
>[!NOTE]
>
>For more on defining the email content, see [this section]().-->

## Definir codificação de caracteres {#character-encoding}

Na guia **[!UICONTROL SMTP]** dos parâmetros do delivery, a seção **[!UICONTROL Character encoding]** permite definir uma codificação específica.

A codificação padrão é UTF-8. Se alguns dos provedores de email de seus recipients não oferecerem suporte à codificação padrão UTF-8, você pode definir uma codificação específica para exibir corretamente os caracteres especiais aos recipients dos seus emails.

Por exemplo, você deseja enviar um email contendo caracteres japoneses. Para garantir que todos os caracteres sejam exibidos corretamente para seus recipients no Japão, é possível usar uma codificação que ofereça suporte aos caracteres japoneses em vez do padrão UTF-8.

Para fazer isso, selecione a opção **[!UICONTROL Force the encoding used for messages]** na seção **[!UICONTROL Character encoding]** e escolha uma codificação na lista suspensa que é exibida.

![](assets/email-smtp-encoding.png)

## Gerenciar emails rejeitados {#managing-bounce-emails}

A variável **[!UICONTROL SMTP]** A guia das propriedades do delivery permite também configurar a gestão de emails devolvidos.

* **[!UICONTROL Errors-to-address]**: Por padrão, os emails devolvidos são recebidos na caixa de erro padrão da plataforma, mas é possível definir um endereço de erros específico para uma entrega.

* **[!UICONTROL Bounce address]**: também é possível definir outro endereço para o qual os emails devolvidos não processados são encaminhados. Esse endereço permite investigar os motivos para a rejeição quando os emails não puderam ser qualificados automaticamente pelo aplicativo.

Cada um desses campos pode ser personalizado usando o ícone dedicado. Saiba mais sobre campos de personalização em [nesta seção](personalization-fields.md).

![](assets/email-smtp-bounce.png)

Para obter mais informações sobre gerenciamento de rejeição de emails, consulte [esta seção](delivery-failures.md#bounce-mail-management).

## Adicionar cabeçalhos SMTP {#adding-smtp-headers}

É possível adicionar cabeçalhos SMTP às entregas Para fazer isso, use a seção relevante da guia **[!UICONTROL SMTP]** no delivery.

O script inserido nessa janela deve referenciar um cabeçalho por linha no seguinte formulário: **name:value**.

Os valores são codificados automaticamente se necessário.

>[!IMPORTANT]
>
>Adicionar um script para inserir cabeçalhos SMTP adicionais é apenas para usuários avançados.
>
>A sintaxe desse script deve estar em conformidade com os requisitos desse tipo de conteúdo: não há espaço não utilizado, nenhuma linha vazia, etc.

![](assets/email-smtp-headers.png)

<!--
## Generate mirror page {#generating-mirror-page}

The mirror page is an HTML page accessible online via a web browser. Its content is identical to the email. It can be useful if your recipients are experiencing rendering issues or broken images when trying to view your email in their inbox.

Learn how to insert a link to the mirror page in [this section](mirror-page.md).-->