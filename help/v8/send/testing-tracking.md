---
title: Testar o rastreamento de mensagens
description: Saiba como testar o rastreamento de mensagens antes de enviar seus deliveries
feature: Monitoring
role: User
level: Beginner
exl-id: 16ad36b7-c13e-4b77-86ca-41c9ef174172
source-git-commit: edbe7ab49a628436dfb4d27ae17122917d7371e9
workflow-type: tm+mt
source-wordcount: '626'
ht-degree: 3%

---

# Testar o rastreamento de mensagens {#testing-tracking}

Antes de enviar a entrega para todo o público-alvo, é essencial testar a funcionalidade de rastreamento para garantir que todos os links funcionem corretamente e que os dados de rastreamento sejam capturados corretamente. Esse processo de verificação ajuda a identificar e corrigir problemas de rastreamento antes que sua campanha entre em vigor, evitando possíveis problemas com redirecionamentos de link, carregamento de pixel de rastreamento ou coleta de dados.

O rastreamento de testes permite:

* Verifique se todos os links na sua mensagem estão corretamente rastreados e redirecionados
* Confirme se o link de mirror page funciona e é rastreado
* Verifique se os pixels de rastreamento são carregados corretamente para o rastreamento aberto
* Verificar se os parâmetros personalizados em URLs foram capturados com precisão
* Validar se o workflow técnico de rastreamento processa os dados corretamente

Você pode testar o rastreamento em páginas de espelhamento, logs de email e links seguindo as etapas abaixo:

## Etapa 1: criar um delivery de teste {#create-test-delivery}

1. Crie um novo delivery de email que será usado para teste. [Saiba como criar uma entrega](../start/create-message.md)
1. Projete seu conteúdo de email com links que deseja rastrear. [Saiba mais sobre design de conteúdo de email](defining-the-email-content.md)
1. Adicione um bloco de personalização de mirror page no conteúdo do email. [Saiba mais sobre blocos de personalização](personalization-blocks.md)

   ![](assets/mirror-page-insert.png)

1. Especifique o usuário que receberá o email. Como esse usuário terá que abrir o email e clicar nos links que ele contém, verifique se foi selecionado um endereço de recipient de teste de controle. [Saiba mais sobre perfis de teste](../audiences/test-profiles.md)

## Etapa 2: enviar o delivery de teste {#send-test}

1. Verifique se o rastreamento está ativado nas configurações de delivery:
   * Abra o **[!UICONTROL Properties]** da sua entrega
   * Ir para a seção **[!UICONTROL Tracking & Images]**
   * Verifique se **[!UICONTROL Activate tracking]** está marcado
   * Certifique-se de que **[!UICONTROL Opens tracking]** esteja marcado se você deseja rastrear aberturas

   ![](assets/s_ncs_user_email_del_tracking_param.png)

[Saiba mais sobre as opções de rastreamento de URL](url-tracking.md)

1. Envie o delivery para o recipient de teste. [Saiba mais sobre o envio de entregas](configure-and-send.md)

## Etapa 3: verificar a funcionalidade de rastreamento {#verify-tracking}

1. Depois de receber o email, abra-o e clique no link da mirror page. [Saiba mais sobre mirror pages](mirror-page.md)
1. Clique em vários links no email para gerar dados de rastreamento.
1. Depois de ser redirecionado corretamente para a mirror page, acesse a pasta **[!UICONTROL Administration > Production > Technical workflows]**. [Saiba mais sobre fluxos de trabalho](../config/workflows.md)
1. Abra o fluxo de trabalho **[!UICONTROL Tracking]**.
1. Inicie o fluxo de trabalho ou clique com o botão direito do mouse na atividade **[!UICONTROL Scheduler]** e selecione **[!UICONTROL Execute pending task now]**.
1. Aguarde 30 segundos para que o workflow processe os logs de rastreamento.
1. Selecione a guia **[!UICONTROL Audit]** do fluxo de trabalho. Verifique se pelo menos um registro de log de rastreamento é encontrado. Clique em **[!UICONTROL Refresh]** se não visualizar novos logs.

1. Verifique os logs de rastreamento no delivery:
   * Voltar para a entrega
   * Selecione a guia **[!UICONTROL Tracking]**
   * Verifique se a lista de logs de rastreamento é exibida com os URLs clicados e outros eventos de rastreamento

   ![](assets/s_ncs_user_delivery_tracking_tab.png)

## Etapa 4: verificar a guia de rastreamento do recipient {#check-recipient-tracking}

1. Vá para a página de perfil do recipient usado para o teste. [Saiba mais sobre a exibição de perfis](../audiences/view-profiles.md)
   * Por padrão, a página de perfil do destinatário está localizada na pasta **[!UICONTROL Profiles and Targets > Recipients]**.

1. Selecione a guia **[!UICONTROL Tracking]**. [Saiba mais sobre logs de rastreamento](tracking-logs.md)

   ![](assets/s_ncs_user_select_tracking_tab_from_recipient.png)

1. Verifique se os registros de rastreamento aparecem com:
   * O valor **[!UICONTROL Mirror Page]** na coluna **[!UICONTROL Type]**
   * **[!UICONTROL Open]** valores na coluna **[!UICONTROL Type]** para aberturas de email
   * **[!UICONTROL Email click]** valores na coluna **[!UICONTROL Type]** para cliques em links

## Solução de problemas do teste de rastreamento {#troubleshooting-tracking-test}

Se os logs de rastreamento não forem exibidos:

1. **Verificar configurações de entrega**: vá para a entrega e acesse **[!UICONTROL Properties]** para verificar se as opções **[!UICONTROL Activate tracking]** e **[!UICONTROL Opens tracking]** estão habilitadas. [Saiba mais sobre as opções de rastreamento de URL](url-tracking.md)

1. **Verificar o fluxo de trabalho de Rastreamento**: verifique se o fluxo de trabalho técnico **[!UICONTROL Tracking]** está em execução sem erros. [Saiba mais sobre a solução de problemas do fluxo de trabalho de rastreamento](tracking-logs.md#check-tracking-workflow)

1. **Verificar formato de URL**: verifique se as URLs estão formatadas corretamente e delimitadas. [Saiba mais sobre como configurar links rastreados](tracked-links.md)

1. **Revisar comportamento do cliente de email**: alguns clientes de email podem bloquear o rastreamento de pixels ou modificar links. Tente testar com clientes de email diferentes. [Saiba mais sobre as práticas recomendadas de entrega](../start/delivery-best-practices.md)

1. **Aguardar processamento**: o fluxo de trabalho de Rastreamento é executado por hora, por padrão. Se você acioná-lo manualmente, aguarde tempo suficiente para o processamento antes de verificar os resultados. [Saiba mais sobre logs de rastreamento](tracking-logs.md)

## Tópicos relacionados {#related-topics}

* [Saiba como configurar links rastreados](tracked-links.md)
* [Saiba como acessar logs de rastreamento](tracking-logs.md)
* [Entender os relatórios de rastreamento](../reporting/delivery-reports.md#tracking-indicators)

