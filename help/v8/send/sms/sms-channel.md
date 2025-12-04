---
title: Características do canal de SMS
description: Saiba mais sobre as características do canal de SMS
feature: SMS
role: User
level: Intermediate
exl-id: abab6f15-43ea-42fc-817b-8dbd88df82f7
source-git-commit: 00d9c3229b7bbabfec3b1750ae84978545fdc218
workflow-type: tm+mt
source-wordcount: '1395'
ht-degree: 22%

---

# Características do canal de SMS {#sms-channel}

>[!AVAILABILITY]
>
>Esse recurso está disponível para todos os ambientes FDA do Campaign. **não** disponível para implantações do FFDA do Campaign. Esta documentação se aplica ao Adobe Campaign v8.7.2 e posterior. Para alternar do conector herdado para o novo conector SMS, consulte esta [nota técnica](https://experienceleague.adobe.com/docs/campaign/technotes-ac/tn-new/sms-migration){target="_blank"}
>
>Para versões mais antigas, leia a [documentação do Campaign Classic v7](https://experienceleague.adobe.com/pt-br/docs/campaign-classic/using/sending-messages/sending-messages-on-mobiles/sms-set-up/sms-set-up){target="_blank"}.

## Tipos de SMS {#sms-types}

Ao enviar SMS por um provedor SMS, você encontrará três tipos diferentes de SMS:

* **SMS MT (Encerrado por Dispositivo Móvel)**: este é um SMS emitido pela Adobe Campaign para telefones celulares por meio do provedor SMPP.
* **SMS MO (Originado por dispositivo móvel)**: este é um SMS enviado por um dispositivo móvel para o Adobe Campaign por meio do provedor SMPP.
* **SMS SR (Relatório de Status) ou DR ou DLR (Recibo de Entrega)**: é um recibo de retorno enviado pelo dispositivo móvel ao Adobe Campaign por meio do provedor SMPP, indicando que o SMS foi recebido com êxito. O Adobe Campaign também pode receber um SR indicando que a mensagem não pôde ser entregue, geralmente com uma descrição do erro.

Você precisa distinguir entre confirmações (RESP PDU, parte do protocolo SMPP) e SR. Um SR é um tipo de SMS enviado pela rede de ponta a ponta, enquanto uma confirmação é apenas uma confirmação de que uma transferência foi bem-sucedida.

As confirmações e o SR podem acionar erros. A diferenciação dos dois ajudará na solução de problemas.

### Informações transportadas por um SMS  {#sms-info}

Um SMS transporta mais informações do que texto. Aqui está uma lista do que você pode encontrar em um SMS:

* O texto, que é limitado a 140 bytes, o que significa entre 70 e 160 caracteres, dependendo da codificação. Consulte [Codificação de texto SMS](#sms-text-encoding) abaixo para ver os detalhes e as limitações.
* Um endereço de recipient, às vezes chamado de ADC ou MSISDN (o nome técnico para &quot;número de telefone&quot;). Esse é o número do dispositivo móvel que receberá o SMS.
* Um endereço de remetente, que pode ser chamado de oADC ou, às vezes, id do remetente. Pode ser um número de telefone (no dia a dia), um código curto (quando enviado por um provedor) ou um nome (esse é um recurso opcional, nesse caso, você não pode responder ao SMS).
* Um sinalizador para indicar se a mensagem é uma mensagem flash (uma mensagem flash é um pop-up que não é armazenado na memória)
* Um sinalizador para indicar se um SR é esperado ou não.
* Uma data de validade, após a qual nenhum equipamento de rede poderá tentar novamente (nem sempre presente ou respeitado).
* Um campo data_coding, que indica a codificação do texto.

## Codificação de texto SMS {#sms-text-encoding}

>[!IMPORTANT]
>
>A codificação de SMS é um assunto vasto e complexo com muitas armadilhas e implementações não conformes!

A primeira regra é **sempre contatar o provedor SMPP em caso de problemas de codificação**. Somente eles têm um conhecimento preciso da codificação à qual dão suporte e das regras especiais que podem ser aplicáveis devido a limitações na plataforma técnica. Faça com que eles verifiquem o que você envia a eles e o que eles enviam de volta, esse é o único caminho para uma interconexão bem-sucedida e estável.

As mensagens SMS usam uma codificação especial de 7 bits, geralmente chamada de codificação GSM7.  A Wikipédia tem [um bom artigo sobre ela (GSM 03.38 em inglês)](https://en.wikipedia.org/wiki/GSM_03.38).

No protocolo SMPP, o texto GSM7 será expandido para oito bits por caractere para facilitar a solução de problemas. O SMSC o compactará em sete bits por caractere antes que seja enviado ao dispositivo móvel. Isso significa que o campo short_message do SMS pode ter até 160 bytes de comprimento no quadro SMPP, enquanto está limitado a 140 bytes quando enviado na rede móvel (o bit mais significativo é simplesmente descartado).

Em caso de problemas de codificação, veja alguns itens importantes a serem verificados:
* Primeiro, saiba quais caracteres pertencem a qual codificação. O GSM7 é famoso por seu apoio parcial a marcas diacríticas (acentos). Especialmente em francês, em que &quot;é&quot; e &quot;è&quot; fazem parte do GSM7, mas &quot;ê&quot;, &quot;â&quot; ou &quot;ï&quot; não fazem parte. O mesmo se aplica ao espanhol.
* O C com cedilha (ç) está presente apenas em maiúsculas no alfabeto GSM7, mas alguns telefones o renderizam em minúsculas ou em letras maiúsculas &quot;inteligentes&quot;: a recomendação geral é evitá-lo completamente e remover o cedilha (ainda é bem legível em francês) ou alternar para UCS-2.
* **Não use ASCII em SMS!** a menos que solicitado explicitamente pelo provedor SMPP: essa codificação desperdiça espaço porque tem caracteres de 8 bits e menos cobertura do que o GSM7. Essa codificação pode ser necessária para redes CDMA (usadas na América do Norte).
* O Latin-1 nem sempre é compatível. Verifique a compatibilidade com seu provedor SMPP antes de tentar usar o Latin-1.
* As tabelas de correspondência de idiomas nacionais não são compatíveis com o conector do Adobe Campaign. Em vez disso, você deve usar UCS-2 ou outro data_coding.
* UCS-2 e UTF-16 são frequentemente misturados por telefones. Esse é um problema para as pessoas que enviam emojis e outros caracteres raramente usados que não estão presentes no UCS-2.
* Os telefones exclusivos mais antigos não têm glifos de fonte para todos os caracteres UCS-2. Os smartphones mais recentes tendem a ser capazes de exibir caracteres raros com bastante facilidade, os smartphones mais antigos muitas vezes não têm muitos emojis, e telefones com recursos muito antigos geralmente têm suporte limitado ao que é útil na língua nativa do país em que foram comprados. Se você quiser usar emoji ou ASCII-art de algum tipo, teste-o em uma grande variedade de telefones antes de enviar. A visualização do Campaign não simula glifos ausentes e exibirá os símbolos disponíveis no navegador da Web que exibe a visualização.

O campo *data_coding* informa qual codificação é usada. Um grande problema é que o valor 0 significa *codificação SMSC padrão* na especificação; em geral, significa GSM7, mas nem sempre é esse o caso. Verifique com o provedor SMPP qual codificação está associada a data_coding = 0. Outros valores data_coding tendem a seguir a especificação, mas a única maneira de ter certeza é verificar com o provedor SMPP.

O tamanho máximo de uma mensagem depende de sua codificação. Esta tabela resume todas as informações relevantes:

| Codificação | data_coding comum | Tamanho da mensagem (caracteres) | Tamanho da parte para SMS multiparte | Caracteres disponíveis |
|:-:|:-:|:-:|:-:|:-:|
| GSM7 | 0 | 160 | 152 | Conjunto de caracteres básicos GSM7 + extensão (caracteres estendidos usam dois caracteres) |
| Latino-1 | 3 | 140 | 134 | ISO-8859-1 |
| UCS-2 UTF-16 | 8 | 70 | 67 | Unicode (varia de telefone para telefone) |

## SMS multiparte (SMS longo) {#multipart-sms}

O SMS multiparte (geralmente chamado de SMS longo) é um SMS enviado em várias partes. Devido a limitações técnicas no protocolo de rede móvel, um SMS não pode ter mais de 140 bytes (consulte a seção codificação de texto SMS abaixo para saber o número de caracteres que um SMS pode conter), portanto, mensagens mais longas precisam ser divididas.

Cada parte de uma mensagem longa é um SMS individual. Essas partes viajam independentemente na rede e são montadas pelo telefone celular receptor. Para lidar com tentativas e problemas de conectividade normalmente, o Campaign envia partes em ordem inversa e solicita um SR somente na primeira parte da mensagem (aquele enviado por último); como o telefone celular exibe apenas uma mensagem quando recebeu sua primeira parte, as tentativas de partes adicionais não produzirão duplicatas no telefone celular.

O número máximo de SMS por mensagem pode ser definido por delivery usando a configuração Número máximo de SMS por mensagem no template do delivery. As mensagens que ultrapassarem esse limite terão falha durante o envio, com o motivo de falha de SMS muito longo.

Há duas maneiras de enviar SMS longos:

* UDH
* message_payload

UDH é a maneira padrão e recomendada de enviar mensagens longas. Nesse modo, o conector divide a mensagem em várias PDUs SUBMIT_SM com informações UDH. Esse protocolo é o usado pelos próprios celulares, o que significa que o Campaign tem mais controle sobre a geração de mensagens, tornando-a capaz de calcular exatamente quantas partes foram enviadas e como foram divididas.

*message_payload* é uma maneira de enviar toda a mensagem longa em uma única PDU SUBMIT_SM. O provedor terá que dividi-la, o que significa que é impossível para o Campaign saber exatamente quantas partes foram enviadas. Alguns provedores exigem esse modo, use-o somente se eles não forem compatíveis com UDH.

Consulte a descrição dos campos esm_class, short_message e message_payload do PDU SUBMIT_SM acima para obter mais detalhes sobre o protocolo e os formatos.

>[!NOTE]
>
>Embora o Adobe Campaign seja compatível com UDH e message_payload para envio, somente message_payload é compatível com o SMS de entrada (MO).
