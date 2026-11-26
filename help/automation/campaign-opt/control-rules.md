---
product: campaign
title: Configurar regras de controle
description: Saiba como configurar regras de controle
feature: Typology Rules
version: Campaign v8, Campaign Classic v7
exl-id: 79e442ea-f856-41bf-b065-25cb2ad2c65b
TQID: 'https://experienceleague.adobe.com/xluD-4nygREOMWZyFT6OrenJvfvFVWTVf7i6-ZoYfTI'
product_v2:
  - id: dfc56824-e8b9-499e-85d4-21aedb507314
    internal-label: Campaign
  - id: d0e9f0b2-1f2b-4134-9844-49cd4e950f27
    internal-label: Campaign v8
feature_v2:
  - id: c858a28b-ea19-49b0-8d48-828717fad89c
    internal-label: Prepare and test messages
subfeature_v2:
  - id: e5fb657f-3c0a-4fcc-9980-3589a23ab4de
    internal-label: Typology rules
topic_v2:
  - id: cdd65e7e-8839-44a2-bc21-0e03623b5dd1
    internal-label: Optimization
source-git-commit: 8839c1717cb026a38987a745ffc080a79f344bce
workflow-type: tm+mt
source-wordcount: '457'
ht-degree: 75%
---
# Regras de controle{#control-rules}

Regras de controle permitem que você garanta a validade e a qualidade das mensagens antes da entrega: exibição de caracteres, tamanho do SMS, formato de endereço etc.

Um conjunto de regras prontas permite que você faça as verificações normais. Essas verificações (mostradas em negrito na interface) são:

* **[!UICONTROL Object approval]** (email): verifica se o objeto e o endereço do remetente não contêm caracteres especiais que podem causar problemas em determinados agentes de email.
* **[!UICONTROL URL label approval]** (email): verifica se cada URL de rastreamento tem um rótulo.
* **[!UICONTROL URL approval]** (email): verifica as URLs de rastreamento (presença do caractere &quot;&amp;&quot;).
* **[!UICONTROL Message size approval]** (dispositivos móveis): verifica o tamanho das mensagens SMS.
* **[!UICONTROL Validity period check]** (email): verifica se o período de validade da entrega é longo o suficiente para enviar todas as mensagens.
* **[!UICONTROL Proof size check]** (todos os canais): gera uma mensagem de erro se a população do target de prova exceder 100 destinatários.
* **[!UICONTROL Wave scheduling check]** (email): verifica se a última onda de entregas está agendada para iniciar antes do fim do período de validade, caso a entrega esteja distribuída em várias ondas.
* **[!UICONTROL Unsubscription link approval]** (email): verifica a presença de pelo menos um URL de cancelamento de subscrição (opt-out) em cada conteúdo (HTML e Text).

## Criar uma regra de controle {#create-a-control-rule}

É possível criar novas regras de controle para atender às suas necessidades. Para fazer isso, crie uma regra de tipologia **[!UICONTROL Control]** e insira a fórmula de controle em SQL na guia **[!UICONTROL Code]**.

**Exemplo:**

No exemplo a seguir, vamos criar uma regra para impedir que uma oferta em SMS seja enviada para mais de 100 destinatários. Essa regra será vinculada a uma tipologia de campanha, em seguida às entregas de SMS para os quais a oferta relacionada estiver disponível.

Siga as etapas abaixo:

1. Crie uma regra de tipologia **[!UICONTROL Control]**. Selecione um nível de alerta **[!UICONTROL Warning]**.

   ![Caixa de diálogo de criação de regra de tipologia, guia Geral: Tipo de regra de controle, canal SMS, menu suspenso Nível com o Aviso realçado.](assets/campaign_opt_create_control_01.png)

1. Na guia **[!UICONTROL Code]**, insira o script para aplicar o limite desejado, conforme mostrado abaixo:

   ![Guia Código da regra de tipologia com o script que registra um aviso quando o destino da entrega excede 100 contatos.](assets/campaign_opt_create_control_02.png)

   Este script acionará um aviso se o target da entrega exceder 100 contatos:

   ```
   if( delivery.FCP == false && delivery.properties.toDeliver > 100 ) { logWarning("Significant number of SMS to deliver (" + delivery.properties.toDeliver + "). Please make sure the target is correct.") return false; } return true
   ```

1. Vincule esta regra a uma tipologia de campanha e faça referência à tipologia na entrega do SMS em questão.

   ![Propriedades de Entrega, guia Tipologia: lista suspensa Tipologia Móvel (Máx. 100) entre as tipologias disponíveis.](assets/campaign_opt_create_control_03.png)

1. Durante a análise da entrega, a regra é aplicada e um aviso é criado se aplicável.

   ![Log de análise de entrega mostrando um aviso de que a regra +100 mensagens detectou um problema; confirme se a entrega está disponível.](assets/campaign_opt_create_control_04.png)

   No entanto, a entrega ainda estará pronta para ser enviada.

   Se você aumentar o nível de alerta, isso impedirá que a entrega seja iniciada.

   ![Guia Geral da regra de tipologia com o menu suspenso Nível aberto e Erro selecionado em vez de Aviso.](assets/campaign_opt_create_control_05.png)

   No final da análise, o botão **[!UICONTROL Confirm delivery]** não estará disponível.

   ![Log de análise de entrega com erro, com o botão Confirmar entrega desabilitado.](assets/campaign_opt_create_control_06.png)
