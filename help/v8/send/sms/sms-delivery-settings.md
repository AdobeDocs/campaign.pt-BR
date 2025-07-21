---
title: Configurações de entrega de SMS
description: Saiba como configurar uma entrega de SMS
feature: SMS
role: User
level: Beginner, Intermediate
exl-id: c4d500ef-2339-491f-9ae2-9bfaf72088a9
source-git-commit: ea51863bdbc22489af35b2b3c81259b327380be4
workflow-type: tm+mt
source-wordcount: '817'
ht-degree: 15%

---

# Configurações de entrega de SMS {#sms-settings}

>[!AVAILABILITY]
>
>Esse recurso está disponível para todos os ambientes FDA do Campaign. **não** disponível para implantações do FFDA do Campaign. Esta documentação se aplica ao Adobe Campaign v8.7.2 e posterior. Para alternar do conector herdado para o novo conector SMS, consulte esta [nota técnica](https://experienceleague.adobe.com/docs/campaign/technotes-ac/tn-new/sms-migration){target="_blank"}
>
>Para versões mais antigas, leia a [documentação do Campaign Classic v7](https://experienceleague.adobe.com/en/docs/campaign-classic/using/sending-messages/sending-messages-on-mobiles/sms-set-up/sms-set-up){target="_blank"}.

As configurações técnicas necessárias para um delivery de SMS são:

* A conta externa SMPP para o roteamento de mensagens. [Saiba mais](smpp-external-account.md#smpp-connection-settings)
* Configure a guia SMS. [Saiba como](#sms-tab)

Você pode configurar tudo isso em um template do delivery para evitar a execução das configurações de cada criação de delivery de SMS.

## Configurar a guia SMS {#sms-tab}

![](assets/send_settings.png){zoomable="yes"}

Estas são as informações necessárias para preencher este formulário. Cada campo é explicado abaixo:

* **[!UICONTROL Sender address]**

  Este campo é opcional. Permite substituir o endereço do remetente (oADC). O conteúdo desse campo é colocado no campo *source_addr* da PDU SUBMIT_SM.

  O campo é limitado a 21 caracteres pela especificação SMPP, mas alguns provedores podem permitir valores mais longos. Observe também que restrições muito rigorosas podem ser aplicadas em alguns países (comprimento, conteúdo, caracteres permitidos...), portanto, talvez seja necessário verificar novamente se o conteúdo inserido aqui é legal. Tenha cuidado especial ao usar campos personalizados.

  Se esse campo ficar vazio, o valor do campo de número do Source definido na conta externa será usado. Se ambos os valores estiverem vazios, o campo *source_addr* ficará vazio.

* **[!UICONTROL Service or program ID]**

  >[!NOTE]
  >
  >Não é recomendável usar esse recurso. Os parâmetros SMPP opcionais fornecem uma implementação muito mais flexível.
  >
  >Ambos os recursos não podem ser usados ao mesmo tempo.

  Em combinação com a configuração correspondente da conta externa, permite enviar um parâmetro opcional com cada MT. Esse campo define a parte do valor do TLV.

* **[!UICONTROL Transmission mode]**

  Esse campo indica o tipo de SMS que você deseja transferir: mensagens normais ou em flash, armazenando no celular ou no cartão SIM. Essa configuração é transmitida no campo opcional dest_addr_subunit na PDU SUBMIT_SM.

   * **Flash** define o valor como 1. Ele envia uma mensagem flash que é exibida no dispositivo móvel e não é armazenada na memória.
   * **Normal** define o valor como 0. Envia uma mensagem normal.
   * **Salvar no dispositivo móvel** define o valor como 2. Ele instrui o telefone a armazenar o SMS na memória interna.
   * **Salvar no terminal** define o valor como 3. Ele instrui o telefone a armazenar o SMS no cartão SIM.

* **[!UICONTROL Priority, Communication type]**

  Esses campos são ignorados pelo conector SMPP estendido.

* **[!UICONTROL Maximum number of SMS per message]**

  Essa configuração só funcionará se a configuração Carga da mensagem estiver desativada (consulte nas configurações da conta externa para obter mais informações). Se a mensagem exigir mais SMS do que esse valor, um erro será acionado.

  O protocolo SMS limita o SMS a 255 partes, mas alguns telefones celulares têm dificuldade em reunir mensagens longas com mais de 10 partes (o limite depende do modelo exato). Se quiser estar seguro, não exceda cinco partes por mensagem.

  Devido ao modo como as mensagens personalizadas funcionam no Adobe Campaign, o tamanho das mensagens pode variar, portanto, ter muitas mensagens muito longas pode aumentar muito os custos de envio: definir isso como um valor razoável ajuda a controlar esses custos.

  Especificar 0 desativa o limite.

* **[!UICONTROL Optional SMPP parameters (TLV)]**
Você pode especificar campos extras para enviar como parâmetros SMPP opcionais (TLV). Esses campos extras são enviados com cada MT e os campos personalizados permitem ter valores diferentes para cada MT.
A tabela lista os parâmetros opcionais a serem enviados com cada mensagem. As colunas contêm as seguintes informações:
   * **Rótulo**: este é um rótulo opcional de forma livre. Ele não é transmitido ao provedor. Você pode fornecer uma descrição textual do parâmetro.
   * **Marca**: o valor da marca em formato decimal (por exemplo, 12345) ou hexadecimal com o prefixo 0x (por exemplo, 0x12ab). As tags podem ficar entre 0 e 65535. Peça ao provedor de serviços SMPP as tags que ele aceita.
   * **Valor**: valor a ser enviado no parâmetro opcional. Este é um campo personalizado.
   * **Formato**: codificação usada para o parâmetro. Você pode selecionar qualquer codificação de texto compatível ou os formatos binários mais comuns. Peça o formato necessário ao provedor de serviços SMPP.
   * **Comprimento máximo**: número máximo de bytes para este parâmetro. Isso é ignorado para campos binários, pois os campos binários têm um tamanho fixo.

* **[!UICONTROL Using binary formats for TLV]**

  O Campaign oferece suporte ao envio de TLV em formato binário. O binário está limitado ao envio de números.

  Como os campos personalizados sempre geram texto, o campo personalizado deve conter uma representação decimal do número (qualquer string pode ser usada, desde que contenha apenas dígitos). Os valores podem ser assinados ou não, o mecanismo de personalização apenas os converte para a representação binária correta.

  Ao usar formatos binários, os valores especiais &#39;&#39; (cadeia de caracteres vazia), &#39;null&#39; e &#39;undefined&#39; desativam completamente o campo sem gerar um erro. Nesses 3 casos especiais, a tag não é passada. Isso permite transmitir um TLV específico somente para algumas mensagens ao usar JavaScript cuidadosamente criado no campo de personalização.

  >[!NOTE]
  >
  >Os formatos binários são sempre codificados na forma big-endian.

