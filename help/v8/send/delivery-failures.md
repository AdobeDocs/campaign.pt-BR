---
title: Falhas de entrega no Campaign
description: Entender possíveis falhas ao enviar mensagens com o Adobe Campaign
feature: Profiles, Monitoring
role: User
level: Beginner, Intermediate
exl-id: 9c83ebeb-e923-4d09-9d95-0e86e0b80dcc
source-git-commit: 338013ac999ae0fedac132adf730c6f9477d73ca
workflow-type: tm+mt
source-wordcount: '2976'
ht-degree: 64%

---

# Entender as falhas de entrega {#delivery-failures}

As rejeições são o resultado de uma tentativa de entrega e falha em que o ISP fornece avisos de falha. O processamento do tratamento de rejeição é uma parte essencial da higiene das listas. Depois que um determinado email é rejeitado várias vezes consecutivas, esse processo o sinaliza para supressão.

Esse processo impede que os sistemas continuem enviando endereços de email inválidos. As rejeições são um dos dados principais que os ISPs usam para determinar a reputação do IP. É importante acompanhar essa métrica. &quot;Entregue&quot; versus &quot;rejeitado&quot; é provavelmente a maneira mais comum de medir a entrega de mensagens de marketing: quanto maior a porcentagem entregue, melhor.

Se uma mensagem não puder ser enviada a um perfil, o servidor remoto enviará automaticamente uma mensagem de erro ao Adobe Campaign. Esse erro é qualificado para determinar se o endereço de email, o número de telefone ou o dispositivo deve ir para a quarentena. Consulte [Gerenciamento de emails de devolução](#bounce-mail-qualification).

Depois que uma mensagem for enviada, você poderá visualizar o status do delivery para cada perfil, o tipo de falha e o motivo associados nos logs do delivery.

Quando um endereço de email está em quarentena ou se um perfil está na inclui na lista de bloqueios, o recipient é excluído na etapa de preparação do delivery. As mensagens excluídas são listadas no painel de entrega.

## Por que a entrega da mensagem falhou? {#delivery-failure-reasons}

Há dois tipos de erros quando uma mensagem falha. Cada tipo de falha de entrega determina se um endereço será enviado para a [quarentena](quarantines.md#quarantine-reason) ou não.

* **Devoluções permanentes**
As rejeições permanentes são falhas permanentes geradas depois que um ISP determina uma tentativa de envio por email para um endereço de assinante como não entregue. No Adobe Campaign, as rejeições permanentes categorizadas como não entregues são adicionadas à lista de quarentena, o que significa que elas não terão nova tentativa. Há alguns casos em que uma rejeição permanente é ignorada se a causa da falha for desconhecida.

  Estes são alguns exemplos comuns de rejeições permanentes: Endereço não existe, Conta desabilitada, Sintaxe incorreta, Domínio inválido

* **Rejeições temporárias**
As rejeições temporárias são falhas temporárias que os ISPs geram quando têm dificuldade em entregar emails. As falhas leves serão [repetidas](#retries) várias vezes (com variação dependendo do uso de configurações de entrega personalizadas ou predefinidas) para tentar uma entrega bem-sucedida. Os endereços que continuamente emitem rejeição não serão adicionados à quarentena até que o número máximo de tentativas tenha sido atingido (o que novamente varia de acordo com as configurações).

  Algumas causas comuns de rejeições temporárias incluem: Caixa de entrada cheia, Servidor de email de recebimento inativo, Problemas de reputação do remetente

O tipo de erro **Ignorado** é conhecido como temporário, como &quot;Ausente&quot;, ou um erro técnico, por exemplo, se o tipo de remetente for &quot;postmaster&quot;.

O loop de feedback funciona como emails de devolução: quando um usuário qualifica um email como spam, você pode configurar regras de email no Adobe Campaign para bloquear todos os deliveries a esse usuário. Incluir na lista de bloqueios Os endereços desses usuários são classificados mesmo que não tenham clicado no link de cancelamento de subscrição. Os endereços são adicionados à tabela de quarentena (**NmsAddress**) e não à tabela de recipient (**NmsRecipient**) com o status **[!UICONTROL Denylisted]**. Saiba mais sobre o mecanismo de loop de comentários no [Manual de práticas recomendadas de capacidade de entrega do Adobe](https://experienceleague.adobe.com/docs/deliverability-learn/deliverability-best-practice-guide/transition-process/infrastructure.html?lang=pt-BR#feedback-loops){target="_blank"}.

## Erros síncronos e assíncronos {#synchronous-and-asynchronous-errors}

Um delivery de mensagem pode falhar imediatamente, nesse caso, qualificamos isso como um erro síncrono. Se o envio da mensagem falhar ou depois, depois de ter sido enviado, o erro será assíncrono.

Esses tipos de erros são gerenciados da seguinte maneira:

* **Erro síncrono**: o servidor remoto contatado pelo servidor de entrega do Adobe Campaign retorna imediatamente uma mensagem de erro. O delivery não tem permissão para ser enviado ao servidor do perfil. O Mail Transfer Agent (MTA) determina o tipo de rejeição e qualifica o erro e envia essas informações para o Campaign para determinar se os endereços de email devem ser colocados em quarentena. Consulte [Qualificação de email de devolução](#bounce-mail-qualification).

* **Erro assíncrono**: um email de devolução ou um Relatório de Status será reenviado posteriormente pelo servidor receptor. Esse erro é qualificado com um rótulo relacionado ao erro. Podem ocorrer erros assíncronos até uma semana depois da entrega.

>[!NOTE]
>
>Como usuário do Managed Cloud Services, a configuração da caixa de entrada de devolução é executada pela Adobe.

## Qualificação de email de rejeição {#bounce-mail-qualification}

<!--NO LONGER WITH MOMENTUM - Rules used by Campaign to qualify delivery failures are listed in the **[!UICONTROL Administration > Campaign Management > Non deliverables Management > Delivery log qualification]** node. It is non-exhaustive, and is regularly updated by Adobe Campaign and can also be managed by the user.

![](assets/delivery-log-qualification.png)-->

A maneira como a qualificação de emails rejeitados é tratada no Adobe Campaign depende do tipo de erro:

* **Erros síncronos**: o MTA determina o tipo de rejeição e a qualificação e retorna essas informações ao Campaign. As qualificações de rejeição na tabela **[!UICONTROL Delivery log qualification]** não são usadas para mensagens de erro de falha de entrega **síncrona**.

* **Erros assíncronos**: as regras usadas pelo Campaign para qualificar falhas de entrega assíncronas estão listadas no nó **[!UICONTROL Administration > Campaign Management > Non deliverables Management > Delivery log qualification]**. As rejeições assíncronas são qualificadas pelo processo do InMail por meio das regras **[!UICONTROL Inbound email]**. Para obter mais informações, consulte a [documentação do Adobe Campaign Classic v7](https://experienceleague.adobe.com/docs/campaign-classic/using/sending-messages/monitoring-deliveries/understanding-delivery-failures.html#bounce-mail-qualification){target="_blank"}.

<!--NO LONGER WITH MOMENTUM - The message returned by the remote server on the first occurrence of this error type is displayed in the **[!UICONTROL First text]** column of the **[!UICONTROL Audit]** tab.

![](assets/delivery-log-first-txt.png)

Adobe Campaign filters this message to delete the variable content (such as IDs, dates, email addresses, phone numbers, etc.) and displays the filtered result in the **[!UICONTROL Text]** column. The variables are replaced with **`#xxx#`**, except addresses that are replaced with **`*`**.

This process allows to bring together all failures of the same type and avoid multiple entries for similar errors in the Delivery log qualification table.
  
>[!NOTE]
>
>The **[!UICONTROL Number of occurrences]** field displays the number of occurrences of the message in the list. It is limited to 100 000 occurrences. You can edit the field, if you want, for example, to reset it.

Bounce mails can have the following qualification status:

* **[!UICONTROL To qualify]**: the bounce mail could not be qualified. Qualification must be assigned to the Deliverability team to guarantee efficient platform deliverability. As long as it is not qualified, the bounce mail is not used to enrich the list of email management rules.
* **[!UICONTROL Keep]**: the bounce mail was qualified and will be used by the **Refresh for deliverability** workflow to be compared to existing email management rules and enrich the list.
* **[!UICONTROL Ignore]**: the bounce mail is ignored, meaning that this bounce will never cause the recipient's address to be quarantined. It will not be used by the **Refresh for deliverability** workflow and it will not be sent to client instances.

![](assets/delivery-log-status.png)

>[!NOTE]
>
>In case of an outage of an ISP, emails sent through Campaign will be wrongly marked as bounces. To correct this, you need to update bounce qualification.-->


## Gerenciamento de tentativas {#retries}

Se a entrega da mensagem falhar após um erro temporário (**Soft** ou **Ignored**), o Campaign tentará enviar novamente. Essas tentativas podem ser executadas até o final da duração do delivery.

As tentativas de rejeição temporária e o tempo entre elas são determinados pelo MTA com base no tipo e na gravidade das respostas de rejeição que retornam do domínio de email da mensagem.

>[!NOTE]
>
>As configurações de nova tentativa nas propriedades de entrega não são usadas pelo Campaign.

## Período de validade {#valid-period}

A configuração do período de validade em seus deliveries do Campaign é limitada a **3,5 dias ou menos**. Para um delivery, se você definir um valor superior a 3,5 dias no Campaign, ele não será considerado.

Por exemplo, se o período de validade for definido como o valor padrão de 5 dias no Campaign, as mensagens com rejeição temporária entrarão na fila de tentativas do MTA e serão repetidas apenas por até 3,5 dias a partir do momento em que a mensagem chegar ao MTA. Nesse caso, o valor definido no Campaign não será usado.

Quando uma mensagem estiver na fila do MTA por 3,5 dias e não for entregue, o tempo limite expirará, e seu status será atualizado de **[!UICONTROL Sent]** para **[!UICONTROL Failed]** nos logs de entrega.

<!--For more on the validity period, see the [Adobe Campaign Classic v7 documentation](https://experienceleague.adobe.com/docs/campaign-classic/using/sending-messages/key-steps-when-creating-a-delivery/steps-sending-the-delivery.html#defining-validity-period){target="_blank"}.-->


## Tipos de erro de email {#email-error-types}

Para o canal de email, os possíveis motivos para uma falha de delivery estão listados abaixo.

<table> 
 <tbody> 
  <tr> 
   <td> Rótulo de erro </td> 
   <td> Tipo de erro </td> 
   <td> Valor técnico </td> 
   <td> Descrição </td> 
  </tr> 
  <tr> 
   <td> Conta desabilitada </td> 
   <td> Suave/Grave </td> 
   <td> 4 </td> 
   <td> A conta vinculada ao endereço não está mais ativa. Quando o Fornecedor de Acesso à Internet (IAP) detecta um longo período de inatividade, ele pode fechar a conta do usuário. As entregas ao endereço do usuário serão impossíveis. Se a conta estiver temporariamente desabilitada devido a seis meses de inatividade e ainda puder ser ativada, o status Com erros será atribuído e a conta terá nova tentativa até que o contador de erro atinja 5. Se o erro indicar que a conta está desativada permanentemente, ela será enviada diretamente à quarentena.<br /> </td> 
  </tr> 
  <tr> 
   <td> Endereço em quarentena </td> 
   <td> Grave </td> 
   <td> 9 </td> 
   <td> O endereço foi colocado em quarentena.<br /> </td> 
  </tr> 
  <tr> 
   <td> Endereço não especificado </td> 
   <td> Grave </td> 
   <td> 7 </td> 
   <td> Nenhum endereço é fornecido para o destinatário.<br /> </td> 
  </tr> 
  <tr> 
   <td> Endereço Bad-quality </td> 
   <td> Ignored </td> 
   <td> 14 </td> 
   <td> A classificação de qualidade deste endereço é muito baixa.<br /> </td> 
  </tr> 
  <tr> 
   <td> Endereço na lista de bloqueios </td> 
   <td> Grave </td> 
   <td> 8 </td> 
   <td> O endereço foi adicionado à lista de bloqueios no momento do envio. Esse status é usado para importar dados de listas externas e sistemas externos para a lista de quarentena do Adobe Campaign.<br /> </td> 
  </tr> 
  <tr> 
   <td> Endereço de controle </td> 
   <td> Ignored </td> 
   <td> 127 </td> 
   <td> O endereço do destinatário faz parte do grupo de controle.<br /> </td> 
  </tr> 
  <tr> 
   <td> Duplo </td> 
   <td> Ignored </td> 
   <td> 10 </td> 
   <td> O endereço do destinatário já estava nessa entrega.<br /> </td> 
  </tr> 
  <tr> 
   <td> Erro ignorado </td> 
   <td> Ignored </td> 
   <td> 25 </td> 
   <td> O endereço está na lista de permissões. O erro é então ignorado e um email será enviado.<br /> </td> 
  </tr> 
  <tr> 
   <td> Excluído após arbitragem </td> 
   <td> Ignored </td> 
   <td> 12 </td> 
   <td> O destinatário foi excluído por uma regra de tipologia de 'arbitragem' de campanha.<br /> </td> 
  </tr> 
  <tr> 
   <td> Excluído por uma regra SQL </td> 
   <td> Ignored </td> 
   <td> 11 </td> 
   <td> O destinatário foi excluído por uma regra de tipologia de campanha do tipo "SQL".<br /> </td> 
  </tr> 
  <tr> 
   <td> Domínio inválido </td> 
   <td> Suave </td> 
   <td> 2 </td> 
   <td> O domínio do endereço de email está incorreto ou não existe mais. Este perfil será alvo novamente até que a contagem de erros chegue a 5. Após isso, o registro será definido como Status de Quarentena e não haverá nenhuma tentativa nova.<br /> </td> 
  </tr> 
  <tr> 
   <td> Caixa de entrada cheia </td> 
   <td> Suave </td> 
   <td> 5 </td> 
   <td> A caixa de entrada deste usuário está cheia e não pode receber mais mensagens. Este perfil será alvo novamente até que a contagem de erros chegue a 5. Após isso, o registro será definido como Status de Quarentena e não haverá nenhuma tentativa nova.<br /> Esse tipo de erro é gerenciado por um processo de limpeza, o endereço é definido como um status válido após 30 dias.<br /> Aviso: para que o endereço seja removido automaticamente da lista de endereços em quarentena, o fluxo de trabalho técnico de Limpeza do banco de dados deve ser iniciado.<br /> </td> 
  </tr> 
  <tr> 
   <td> Não conectado </td> 
   <td> Ignored </td> 
   <td> 6 </td> 
   <td> O telefone celular do destinatário está desligado ou não conectado à rede quando a mensagem é enviada.<br /> </td> 
  </tr> 
  <tr> 
   <td> Não definido </td> 
   <td> Não definido </td> 
   <td> 0 </td> 
   <td> O endereço está em qualificação porque o erro ainda não foi incrementado. Esse tipo de erro ocorre quando uma nova mensagem de erro é enviada pelo servidor: pode ser um erro isolado, mas se ocorrer novamente, o contador de erros aumentará, o que alertará as equipes técnicas. Em seguida, eles podem realizar a análise de mensagens e qualificar esse erro, por meio do nó <span class="uicontrol">Administration</span> / <span class="uicontrol">Campainha Management</span> / <span class="uicontrol">Non deliverables Management</span> na estrutura da árvore.<br /> </td> 
  </tr> 
  <tr> 
   <td> Não se qualifica para as ofertas </td> 
   <td> Ignored </td> 
   <td> 16 </td> 
   <td> O destinatário não foi qualificado para as ofertas na entrega.<br /> </td> 
  </tr> 
  <tr> 
   <td> Recusado </td> 
   <td> Suave/Grave </td> 
   <td> 20 </td> 
   <td> O endereço foi colocado em quarentena devido a um feedback de segurança como um relatório de spam. De acordo com o erro, haverá nova tentativa ao endereço até que o contador de erros atinja 5, ou ele será enviado diretamente para a quarentena.<br /> </td> 
  </tr> 
  <tr> 
   <td> Target limitado em tamanho </td> 
   <td> Ignored </td> 
   <td> 17 </td> 
   <td> O tamanho máximo de entrega foi atingido para o destinatário.<br /> </td> 
  </tr> 
  <tr> 
   <td> Endereço não qualificado </td> 
   <td> Ignored </td> 
   <td> 15 </td> 
   <td> O endereço postal não foi qualificado.<br /> </td> 
  </tr> 
  <tr> 
   <td> Inacessível </td> 
   <td> Suave/Grave </td> 
   <td> 3 </td> 
   <td> Ocorreu um erro na cadeia de entrega de mensagens. Pode ser um incidente na retransmissão SMTP, um domínio que está temporariamente inacessível, etc. De acordo com o erro, haverá nova tentativa ao endereço até que o contador de erros atinja 5, ou ele será enviado diretamente para a quarentena.<br /> </td> 
  </tr> 
  <tr> 
   <td> Usuário desconhecido </td> 
   <td> Grave </td> 
   <td> 1 </td> 
   <td> O endereço não existe. Não haverá mais tentativas de entrega para este perfil.<br /> </td> 
  </tr> 
 </tbody> 
</table>



## Tipos de erro de notificações por push {#push-error-types}

Para o canal de aplicativo móvel, os possíveis motivos para uma falha de delivery estão listados abaixo.

### Quarentena do iOS {#ios-quarantine}

O protocolo HTTP/V2 permite um feedback e status direto para cada entrega por push. Se o conector do protocolo HTTP/V2 for usado, o serviço de feedback não será mais chamado pelo workflow **[!UICONTROL mobileAppOptOutMgt]**. Um token é considerado não registrado quando um aplicativo móvel é desinstalado ou reinstalado.

Em sincronia, se o APNs retornar um status &quot;não registrado&quot; para uma mensagem, o token do público alvo será colocado imediatamente em quarentena.

<table> 
 <tbody> 
  <tr> 
   <td> <strong>Cenário</strong><br /> </td> 
   <td> <strong>Status</strong><br /> </td> 
   <td> <strong>Mensagem de erro</strong><br /> </td> 
   <td> <strong>Tipo de falha</strong><br /> </td> 
   <td> <strong>Motivo da falha</strong><br /> </td> 
   <td> <strong>Tentativa</strong><br /> </td> 
  </tr> 
  <tr> 
   <td> Dispositivo alvo ligado<br /> </td> 
   <td> Ok<br /> </td> 
   <td> </td> 
   <td> </td> 
   <td> </td> 
   <td> </td> 
  </tr> 
  <tr> 
   <td> Dispositivo alvo desligado<br /> </td> 
   <td> Ok<br /> </td> 
   <td> </td> 
   <td> </td> 
   <td> </td> 
   <td> </td> 
  </tr> 
  <tr> 
   <td> O usuário desabilita notificações para o aplicativo<br /> </td> 
   <td> Ok<br /> </td> 
   <td> </td> 
   <td> </td> 
   <td> </td> 
   <td> </td> 
  </tr> 
  <tr> 
   <td> Fase de análise/criação de mensagens - carga muito grande<br /> </td> 
   <td> Falha<br /> </td> 
   <td> Carga muito longa<br /> </td> 
   <td> Suave<br /> </td> 
   <td> Recusado<br /> </td> 
   <td> Não<br /> </td> 
  </tr> 
  <tr> 
   <td> Fase de análise/criação de mensagens – problema inesperado de formato de conteúdo<br /> </td> 
   <td> Falha<br /> </td> 
   <td> Várias mensagens de erro de acordo com o erro<br /> </td> 
   <td> Suave<br /> </td> 
   <td> Indefinido<br /> </td> 
   <td> Não<br /> </td> 
  </tr> 
  <tr> 
   <td> Problema de certificado (senha, corrupção, etc.) e teste de conexão para problema APNs<br /> </td> 
   <td> Falha<br /> </td> 
   <td> Várias mensagens de erro de acordo com o erro<br /> </td> 
   <td> Suave<br /> </td> 
   <td> Recusado<br /> </td> 
   <td> Não<br /> </td> 
  </tr> 
  <tr> 
   <td> Conexão de rede perdida durante o envio<br /> </td> 
   <td> Falha<br /> </td> 
   <td> Erro de conexão<br /> </td> 
   <td> Indefinido<br /> </td> 
   <td> Inacessível<br /> </td> 
   <td> Sim<br /> </td> 
  </tr> 
  <tr> 
   <td> Rejeição da mensagem APNs: cancelamento de registro<br /> o usuário removeu o aplicativo ou o token expirou<br /> </td> 
   <td> Falha<br /> </td> 
   <td> Registro cancelado<br /> </td> 
   <td> Grave<br /> </td> 
   <td> Usuário desconhecido<br /> </td> 
   <td> Não<br /> </td> 
  </tr> 
  <tr> 
   <td> Rejeição de mensagem APNs: todos os outros erros<br /> </td> 
   <td> Falha<br /> </td> 
   <td> A causa de rejeição do erro será exibida na mensagem de erro<br /> </td> 
   <td> Suave<br /> </td> 
   <td> Recusado<br /> </td> 
   <td> Não<br /> </td> 
  </tr> 
 </tbody> 
</table>

### Quarentena do Android {#android-quarantine}

**Para Android V1**

A cada notificação, o Adobe Campaign recebe os erros síncronos diretamente do servidor FCM. O Adobe Campaign os trata dinamicamente e gera erros graves ou suaves, de acordo com a gravidade do erro, e tentativas podem ser executadas:

* Comprimento de carga excedido, problema de conexão, problema de disponibilidade de serviço: tentativa executava, erro leve, o motivo da falha é **[!UICONTROL Refused]**.
* Cota de dispositivo excedida: sem tentativa, erro leve, o motivo da falha é **[!UICONTROL Refused]**.
* Token inválido ou não registrado, erro inesperado, problema da conta do remetente: sem tentativa, erro grave, o motivo de falha é **[!UICONTROL Refused]**.

O workflow **[!UICONTROL mobileAppOptOutMgt]** é executado a cada 6 horas para atualizar a tabela **AppSubscriptionRcp**. Para os tokens declarados não registrados ou inválidos, o campo **Desabilitado** é definido como **Verdadeiro** e a subscrição vinculada a esse token de dispositivo será excluída automaticamente das entregas futuras.

Durante a análise de entrega, todos os dispositivos excluídos do target são automaticamente adicionados à tabela **excludeLogAppSubRcp** .

>[!NOTE]
>
>Para clientes que usam o conector Baidu, aqui estão os diferentes tipos de erros:
>
>* Problema de conexão no início da entrega: falha do tipo **[!UICONTROL Undefined]**, razão da falha **[!UICONTROL Unreachable]**, a tentativa é executada.
>* Perda de conexão durante uma entrega: erro leve, razão da falha **[!UICONTROL Refused]**, a tentativa é executada.
>* Erro síncrono retornado pelo Baidu durante o envio: erro grave, motivo da falha **[!UICONTROL Refused]**, não haverá nova tentativa.
>
>O Adobe Campaign contata o servidor Baidu a cada 10 minutos para recuperar o status da mensagem enviada e atualiza os broadlogs. Se uma mensagem for declarada como enviada, o status da mensagem nos broadlogs será definido como **[!UICONTROL Received]**. Se o Baidu declarar um erro, o status será definido como **[!UICONTROL Failed]**.

**Para Android V2**

O mecanismo de quarentena do Android V2 usa o mesmo processo que o Android V1, o mesmo se aplica à atualização de assinaturas e exclusões. Para obter mais informações, consulte a seção [Android V1](#android-quarantine)

<table> 
 <tbody> 
  <tr> 
   <td> <strong>Cenário</strong><br /> </td> 
   <td> <strong>Status</strong><br /> </td> 
   <td> <strong>Mensagem de erro</strong><br /> </td> 
   <td> <strong>Tipo de falha</strong><br /> </td> 
   <td> <strong>Motivo da falha</strong><br /> </td> 
   <td> <strong>Tentativa</strong><br /> </td> 
  </tr> 
  <tr> 
   <td> Fase de análise/criação de mensagens: palavras-chave ilegais usadas nos campos personalizados<br /> </td> 
   <td> Falha<br /> </td> 
   <td> As seguintes palavras-chave não podem ser usadas: {1}<br /> </td> 
   <td> Suave<br /> </td> 
   <td> </td> 
   <td> Não<br /> </td> 
  </tr> 
  <tr> 
   <td> Fase de análise/criação de mensagens: carga muito grande<br /> </td> 
   <td> Falha<br /> </td> 
   <td> A notificação é muito pesada: {1} bits, enquanto apenas {2} estão autorizados<br /> </td> 
   <td> Suave<br /> </td> 
   <td> Recusado<br /> </td> 
   <td> Não<br /> </td> 
  </tr> 
  <tr> 
   <td> Conexão de rede perdida durante o envio<br /> </td> 
   <td> Falha<br /> </td> 
   <td> Nenhuma resposta do serviço Firebase Cloud Messaging no endereço: {1}<br /> </td> 
   <td> Suave<br /> </td> 
   <td> Inacessível<br /> </td> 
   <td> Sim<br /> </td> 
  </tr> 
  <tr> 
   <td> Rejeição da mensagem FCM: o servidor FCM está temporariamente indisponível (por exemplo, com tempos limites). <br /> </td> 
   <td> Falha<br /> </td> 
   <td> O serviço Firebase Cloud Messaging está temporariamente indisponível<br /> </td> 
   <td> Suave<br /> </td> 
   <td> Inacessível<br /> </td> 
   <td> Sim<br /> </td> 
  </tr> 
  <tr> 
   <td> Rejeição da mensagem FCM: erro ao autenticar a conta do remetente<br /> </td> 
   <td> Falha<br /> </td> 
   <td> Falha ao identificar a conta do desenvolvedor, verifique seu ID e senha<br /> </td> 
   <td> Suave<br /> </td> 
   <td> Recusado<br /> </td> 
   <td> Não<br /> </td> 
  </tr> 
  <tr> 
   <td> Rejeição da mensagem FCM: cota do dispositivo excedida<br /> </td> 
   <td> Falha<br /> </td> 
   <td> </td> 
   <td> Suave<br /> </td> 
   <td> Recusado<br /> </td> 
   <td> Sim<br /> </td> 
  </tr> 
  <tr> 
   <td> Rejeição da mensagem FCM: registro inválido/não registrado<br /> </td> 
   <td> Falha<br /> </td> 
   <td> </td> 
   <td> Grave<br /> </td> 
   <td> Usuário desconhecido<br /> </td> 
   <td> Não<br /> </td> 
  </tr> 
  <tr> 
   <td> Rejeição da mensagem FCM: todos os outros erros<br /> </td> 
   <td> Falha<br /> </td> 
   <td> O servidor Firebase Cloud Messaging retornou um código de erro inesperado: {1} </td> 
   <td> </td> 
   <td> Recusado<br /> </td> 
   <td> Não<br /> </td> 
  </tr> 
    <tr> 
   <td> Rejeição da mensagem FCM: argumento inválido<br /> </td> 
   <td> Falha<br /> </td> 
   <td> INVALID_ARGUMENT </td> 
   <td> Ignorado</td> 
   <td> Indefinido<br /> </td> 
   <td> Não<br /> </td> 
  </tr>
    <tr> 
   <td> Rejeição da mensagem FCM: erro de autenticação de terceiros<br /> </td> 
   <td> Falha<br /> </td> 
   <td> THIRD_PARTY_AUTH_ERROR </td> 
   <td> Ignorado</td>
   <td> Recusado<br /> </td> 
   <td> Sim<br /> </td> 
  </tr>
    <tr> 
   <td> Rejeição da mensagem FCM: incompatibilidade de ID do remetente<br /> </td> 
   <td> Falha<br /> </td> 
   <td> SENDER_ID_MISMATCH </td> 
   <td> Suave</td>
   <td> Usuário desconhecido<br /> </td> 
   <td> Não<br /> </td> 
  </tr>
    <tr> 
   <td> Rejeição da mensagem FCM: não registrado<br /> </td> 
   <td> Falha<br /> </td>
   <td> REGISTRO CANCELADO </td> 
   <td> Grave</td> 
   <td> Usuário desconhecido<br /> </td> 
   <td> Não<br /> </td> 
  </tr>
    <tr> 
   <td> Rejeição da mensagem FCM: interno<br /> </td> 
   <td> Falha<br /> </td> 
   <td> INTERNO </td> 
   <td> Ignorado</td> 
   <td> Recusado<br /> </td> 
   <td> Sim<br /> </td> 
  </tr>
    <tr> 
   <td> Rejeição da mensagem FCM: indisponível<br /> </td> 
   <td> Falha<br /> </td> 
   <td> INDISPONÍVEL</td> 
   <td> Ignorado</td> 
   <td> Recusado<br /> </td> 
   <td> Sim<br /> </td> 
  </tr>
    <tr> 
   <td> Rejeição da mensagem FCM: código de erro inesperado<br /> </td> 
   <td> Falha<br /> </td> 
   <td> código de erro inesperado</td> 
   <td> Ignorado</td> 
   <td> Recusado<br /> </td> 
   <td> Não<br /> </td> 
  </tr>
  <tr> 
   <td> Autenticação: problema de conexão<br /> </td> 
   <td> Falha<br /> </td> 
   <td> Impossível conectar-se ao servidor de autenticação </td> 
   <td> Ignorado</td>
   <td> Recusado<br /> </td> 
   <td> Sim<br /> </td> 
  </tr>
    <tr> 
   <td> Autenticação: cliente ou escopo não autorizado na solicitação.<br /> </td> 
   <td> Falha<br /> </td> 
   <td> unauthorized_client </td> 
   <td> Ignorado</td>
   <td> Recusado<br /> </td> 
   <td> Não<br /> </td> 
  </tr>
    <tr> 
   <td> Autenticação: o cliente não está autorizado a recuperar tokens de acesso usando este método ou o cliente não está autorizado para nenhum dos escopos solicitados.<br /> </td> 
   <td> Falha<br /> </td> 
   <td> unauthorized_client </td> 
   <td> Ignorado</td>
   <td> Recusado<br /> </td> 
   <td> Não<br /> </td> 
  </tr>
    <tr> 
   <td> Autenticação: acesso negado<br /> </td> 
   <td> Falha<br /> </td>
   <td> access_denied</td> 
   <td> Ignorado</td>
   <td> Recusado<br /> </td> 
   <td> Não<br /> </td> 
  </tr>
    <tr> 
   <td> Autenticação: email inválido<br /> </td> 
   <td> Falha<br /> </td> 
   <td> invalid_grant </td> 
   <td> Ignorado</td> 
   <td> Recusado<br /> </td> 
   <td> Não<br /> </td> 
  </tr>
    <tr> 
   <td> Autenticação: JWT inválido<br /> </td> 
   <td> Falha<br /> </td> 
   <td> invalid_grant </td> 
   <td> Ignorado</td> 
   <td> Recusado<br /> </td> 
   <td> Não<br /> </td> 
  </tr>
    <tr> 
   <td> Autenticação: assinatura JWT inválida<br /> </td> 
   <td> Falha<br /> </td> 
   <td> invalid_grant </td> 
   <td> Ignorado</td> 
   <td> Recusado<br /> </td> 
   <td> Não<br /> </td> 
  </tr>
    <tr> 
   <td> Autenticação: escopo Oauth inválido ou público de token de ID fornecido<br /> </td> 
   <td> Falha<br /> </td> 
   <td> unauthorized_client</td> 
   <td> Ignorado</td> 
   <td> Recusado<br /> </td> 
   <td> Não<br /> </td> 
  </tr>
    <tr> 
   <td> Autenticação: cliente OAuth desabilitado<br /> </td> 
   <td> Falha<br /> </td> 
   <td> disabled_client</td> 
   <td> Ignorado</td> 
   <td> Recusado<br /> </td> 
   <td> Não<br /> </td> 
  </tr>
 </tbody> 
</table>

## Quarentenas de SMS {#sms-quarantines}

**Para conectores padrão**

As especificidades do canal SMS estão listadas abaixo.

>[!NOTE]
>
>A tabela **[!UICONTROL Delivery log qualification]** não se aplica ao conector **SMPP genérico estendido**.

<table> 
 <tbody> 
  <tr> 
   <td> <strong>Cenário</strong><br /> </td> 
   <td> <strong>Status</strong><br /> </td> 
   <td> <strong>Mensagem de erro</strong><br /> </td> 
   <td> <strong>Tipo de falha</strong><br /> </td> 
   <td> <strong>Motivo da falha</strong><br /> </td> 
  </tr> 
  <tr> 
   <td> Enviado para o provedor<br /> </td> 
   <td> Sent<br /> </td> 
   <td> </td> 
   <td> </td> 
   <td> </td> 
  </tr> 
  <tr> 
   <td> Recebido no celular<br /> </td> 
   <td> Recebido<br /> </td> 
   <td> </td> 
   <td> </td> 
   <td> </td> 
  </tr> 
  <tr> 
   <td> Erro retornado pelo provedor<br /> </td> 
   <td> Falha<br /> </td> 
   <td> Erro ao receber dados (SR ou MO)<br /> </td> 
   <td> Suave<br /> </td> 
   <td> Inacessível<br /> </td> 
  </tr> 
  <tr> 
   <td> Confirmação MT inválida<br /> </td> 
   <td> Falha<br /> </td> 
   <td> Erro '{1}' ao processar quadro de confirmação para enviar query<br /> </td> 
   <td> Suave<br /> </td> 
   <td> Inacessível<br /> </td> 
  </tr> 
  <tr> 
   <td> Erro ao enviar o MT<br /> </td> 
   <td> Falha<br /> </td> 
   <td> Erro ao enviar mensagens<br /> </td> 
   <td> Suave<br /> </td> 
   <td> Inacessível<br /> </td> 
  </tr> 
 </tbody> 
</table>

**Para o conector SMPP genérico estendido**

Ao usar o protocolo SMPP para enviar mensagens SMS, a gestão de erros é tratada de forma diferente.

O conector SMPP recupera dados da mensagem SR (Relatório do Status) que é retornada usando expressões regulares (regexes) para filtrar seu conteúdo. Esses dados são comparados com as informações encontradas na tabela **[!UICONTROL Delivery log qualification]** (disponível no menu **[!UICONTROL Administration]** > **[!UICONTROL Campaign Management]** > **[!UICONTROL Non deliverables Management]**).

Antes de um novo tipo de erro ser qualificado, o motivo da falha é sempre definido como **Refused** por padrão.

>[!NOTE]
>
>Os tipos de falha e os motivos para falha são os mesmos dos emails.
>
>Peça ao seu provedor uma lista de códigos e status de erros para definir os tipos apropriados de falhas e os motivos para falha na tabela de qualificação de log de entrega.

Exemplo de uma mensagem gerada:

```
SR Generic DELIVRD 000|#MESSAGE#
```

* Todas as mensagens de erro começam com **SR** para distinguir códigos de erro de SMS de códigos de erro de email.
* A segunda parte (**Generic** neste exemplo) da mensagem de erro refere-se ao nome da implementação SMSC, como definido no campo **[!UICONTROL SMSC implementation name]** da conta externa do SMS.

  Como o mesmo código de erro pode ter um significado diferente para cada provedor, esse campo permite que você saiba qual provedor gerou o código de erro. Você pode então encontrar o erro na documentação do provedor relevante.

* A terceira parte (**DELIVRD** neste exemplo) da mensagem de erro corresponde ao código de status recuperado do SR usando a extração de status regex definido na conta externa do SMS.

  Este regex está especificado na guia **[!UICONTROL SMSC specificities]** da conta externa.
Por padrão, o regex extrai o campo **stat:** conforme definido pela seção **Apêndice B** da **especificação 3.4 SMPP**.

* A quarta parte (**000** neste exemplo) da mensagem de erro corresponde ao código de erro extraído do SR usando a extração de código de erro regex definida na conta externa do SMS.

  Este regex está especificado na guia **[!UICONTROL SMSC specificities]** da conta externa.

  Por padrão, o regex extrai o campo **err:** conforme definido pela seção **Apêndice B** da **especificação 3.4 SMPP**.

* Tudo que vem após o símbolo da barra vertical (|) é exibido somente na coluna **[!UICONTROL First text]** da tabela **[!UICONTROL Delivery log qualification]**. Este conteúdo é sempre substituído por **#MESSAGE#** após a mensagem ser normalizada. Esse processo evita ter várias entradas para erros semelhantes e é igual ao dos emails.

O conector SMPP genérico estendido aplica uma heurística para encontrar valores padrão adequados: se o status começar com **DELIV**, é considerado um sucesso porque ele corresponde aos status comuns **DELIVRD** ou **DELIVERED** usados pela maioria dos provedores. Qualquer outro status gera uma falha grave.
