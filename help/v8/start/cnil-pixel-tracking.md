---
title: Pixels de rastreamento de email e orientação da CNIL
description: Noções básicas sobre a orientação atualizada da CNIL sobre pixels de rastreamento de email e os recursos do Adobe Campaign que podem dar suporte aos esforços de conformidade.
feature: Overview
role: User
level: Beginner
hide: true
source-git-commit: 5c27d45ebac8ad300d35ef0ff858fbdaef6ec9fb
workflow-type: tm+mt
source-wordcount: '857'
ht-degree: 2%

---

# Noções básicas sobre a orientação atualizada da CNIL sobre pixels de rastreamento de email

Esta publicação é apenas para fins informativos. Não é um aconselhamento jurídico e não garante a sua conformidade com a legislação aplicável. Os recursos do produto Adobe Campaign descritos abaixo são componentes básicos que, configurados e operados adequadamente, podem oferecer suporte a uma implementação em conformidade. Cada cliente é responsável por determinar e cumprir suas obrigações conforme a legislação aplicável.

## Visão geral

Em 14 de abril de 2026, a Commission nationale de l&#39;informatique et des libertés (CNIL), autoridade de proteção de dados da França, publicou uma [recomendação sobre o uso de pixels de rastreamento em emails](https://www.cnil.fr/sites/default/files/2026-04/recommandation-pixels_de_suivi.pdf). As orientações esclarecem quando o consentimento é necessário e destacam a importância de práticas de consentimento adequadas para o rastreamento de pixels de email. Essa política pode afetar as práticas de envio para qualquer entidade que entregue emails a assinantes com sede na França.

A CNIL forneceu um período de três meses a partir da data da recomendação para que as empresas informassem seus destinatários de email (&quot;usuários&quot;) sobre a presença dos pixels de rastreamento, sua finalidade e o direito dos usuários de recusarem. Durante esse período de transição, espera-se que os clientes notifiquem os usuários sobre o rastreamento de pixels e forneçam uma opção de não participação, se necessário. A CNIL deve iniciar as atividades de fiscalização após 14 de julho de 2026.

À medida que a CNIL e outros reguladores esclarecem as orientações sobre rastreamento de pixels e questões relacionadas, a Adobe continuará a monitorar atualizações e informar os clientes sobre os recursos técnicos dos produtos da Adobe que oferecem suporte ao marketing por email, incluindo o Adobe Campaign.

Os aplicativos de execução de marketing por email do Adobe, incluindo Adobe Journey Optimizer, Journey Optimizer B2B, Adobe Campaign e Marketo Engage, fornecem controles que podem ajudar os clientes a gerenciar o rastreamento aberto no nível do delivery ou do email. Os clientes são responsáveis por determinar suas próprias obrigações de conformidade de acordo com as orientações da CNIL e outras leis aplicáveis, mas esses recursos podem apoiar os esforços de conformidade do cliente.

## O que é um pixel de rastreamento de email

Um pixel de rastreamento de email é uma imagem transparente 1x1 inserida na HTML de um email. Quando o cliente de email do recipient carrega essa imagem, o pixel faz o ping em um servidor que registra dados, como carimbo de data e hora, tipo de dispositivo, cliente de email e, às vezes, um endereço IP para localização aproximada. Esse log é vinculado ao registro de um recipient, permitindo que os profissionais de marketing vejam se um email está aberto.

## Suporte ao cliente

Os clientes que buscam assistência para implementar as alterações descritas acima podem interagir com o ecossistema existente do Adobe. Para perguntas técnicas sobre os recursos da Adobe mencionados, entre em contato com o Gerente de sucesso do cliente ou gerente de conta técnica.

## Funcionalidade do Adobe Campaign relacionada ao rastreamento de email

Os clientes podem usar o rastreamento nativo, o esquema e os mecanismos de personalização da Adobe Campaign para abordar determinados elementos ao configurar a arquitetura para abordar a orientação da CNIL:

* **Classificação da entrega.** Estenda o nms:delivery com um atributo emailType (autenticação, somente entrega, transacional, marketing, serviço público, prospecção B2B). A classificação direciona quais pixels são permitidos sem consentimento.
* **Captura de consentimento.** Estenda o nms:recipient com uma estrutura de consentimento por finalidade contendo versão de texto, carimbo de data/hora, fonte de captura e expiração. Estenda os formulários de inscrição e os centros de preferências para coletar o consentimento em pixels separadamente da aceitação de email.
* **Emissão de pixels.** Defina um NmsTracking_OpenFormula por finalidade de pixel (autenticação, entregabilidade, desempenho, criação de perfil, detecção de fraude). Uma regra de tipologia de delivery seleciona quais fórmulas emitir com base no emailType e no consentimento por finalidade do recipient. Os blocos de personalização encapsulam a lógica de modo que ela não conste de criações individuais.
* **Retirada.** Adicione um link Gerenciar preferências do rastreador a cada rodapé de email, diferente do link de cancelamento de inscrição. O link aponta para uma página de aterrissagem nms:webApp autenticada por idTracking; o recipient retira o consentimento em um clique, sem inserir novamente seu endereço de email. Uma etapa de filtro adicionada ao workflow de Rastreamento padrão impede que reaberturas de emails entregues anteriormente sejam exploradas após a retirada.
* **Prova de consentimento.** Capture cada evento de consentimento em um log somente acréscimo (um namespace de extensão pix:consentLog, por exemplo), com a versão do texto armazenada separadamente para recuperação após alterações de texto. Exiba o log por meio do explorador do Adobe Campaign e como uma exportação periódica.
* **Governança de solicitação novamente.** Um campo lastPixelRefusalDate e uma regra de tipologia de filtragem impedem a solicitação de nova solicitação por pelo menos seis meses após uma recusa. Um fluxo de trabalho periódico pode ajudar a gerenciar a expiração do consentimento.
* **Relatórios.** Os relatórios existentes do Adobe Campaign continuam a operar em relação aos novos campos (urlCategory, emailType, os sinalizadores de consentimento) sem alterações de código.

Para obter mais informações sobre o rastreamento de email nos aplicativos de execução de marketing por email do Adobe, consulte a documentação aqui:

| Produto | Referência da documentação |
|---|---|
| Campaign v8 | [Acompanhamento de Mensagens](https://experienceleague.adobe.com/pt-br/docs/campaign/campaign-v8/analytics/tracking/url-tracking){target="_blank"} |
| Campaign Classic | [Introdução ao rastreamento de mensagens](https://experienceleague.adobe.com/en/docs/campaign-classic/using/sending-messages/monitoring-deliveries/about-message-tracking){target="_blank"} |
| Campaign Standard | [Configurando canal de email](https://experienceleague.adobe.com/en/docs/campaign-standard/using/administrating/configuring-channels/configuring-email-channel){target="_blank"} |
| Journey Optimizer | [Documentação de rastreamento de mensagens](https://experienceleague.adobe.com/en/docs/journey-optimizer/using/channels/email/design-email/add-content/message-tracking){target="_blank"} |
| Marketo Engage | [Desabilitar rastreamento para um link de email](https://experienceleague.adobe.com/en/docs/marketo/using/product-docs/email-marketing/general/functions-in-the-editor/disable-tracking-for-an-email-link){target="_blank"} |
| Journey Optimizer B2B | [Documentação de configurações de email](https://experienceleague.adobe.com/en/docs/journey-optimizer-b2b/user/journey-content/email-channel/add-email){target="_blank"} |
