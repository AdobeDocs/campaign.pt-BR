---
title: Gerenciamento de quarentenas no Campaign
description: Entender o gerenciamento de quarentenas no Adobe Campaign
feature: Profiles, Monitoring
role: User, Data Engineer
level: Beginner
exl-id: 220b7a88-bd42-494b-b55b-b827b4971c9e
source-git-commit: e45799f0f3849d53d2c5f593bc02954b3a55fc28
workflow-type: tm+mt
source-wordcount: '1167'
ht-degree: 35%

---

# Quarentena {#quarantine-management}

O Adobe Campaign gerencia uma lista de endereços em quarentena para canais online (email, SMS, notificação por push). Alguns provedores de acesso à Internet consideram automaticamente emails como spam se a taxa de endereços inválidos for muito alta. A quarentena, portanto, evita que você seja adicionado aos, permitindo que você os inclua na lista de bloqueios por esses provedores. Além disso, a quarentena ajuda a reduzir os custos de envio de SMS, excluindo números de telefone incorretos das entregas.

Quando o endereço ou número de telefone está em quarentena, os recipients são excluídos do target durante a análise de delivery: você não poderá enviar mensagens de marketing, incluindo emails de fluxo de trabalho automatizado, para esses contatos. Se esses endereços em quarentena também estiverem presentes em listas, eles serão excluídos ao enviar para essas listas. Um endereço de email pode ser colocado em quarentena, por exemplo, quando a caixa de entrada estiver cheia, se o endereço não existir ou se o servidor de email não estiver disponível.

<!--For more on best practices to secure and optimize your deliveries, refer to [this page](delivery-best-practices.md).-->

A **Quarentena** se aplica somente a um **endereço**, um **número de telefone** ou um **token de dispositivo**, mas não ao próprio perfil. Por exemplo, um perfil cujo endereço de email esteja em quarentena pode atualizar seu perfil e inserir um novo endereço, podendo então ser direcionado em ações de entrega novamente. Da mesma forma, se dois perfis tiverem o mesmo número de telefone, ambos serão afetados se o número estiver em quarentena. Os endereços em quarentena ou os números de telefone são exibidos nos [logs de exclusão](#delivery-quarantines) (para uma entrega) ou na [lista de quarentena](#non-deliverable-bounces) (para toda a plataforma).

Por outro lado, os perfis podem estar no **incluo na lista de bloqueios** como após um cancelamento de inscrição (recusa) de um determinado canal: isso implica que eles não serão mais direcionados por nenhum. Incluir na lista de bloqueios Como consequência, se um perfil no canal tiver dois endereços de email, ambos os endereços serão excluídos do delivery. Você pode verificar se um perfil está na lista de bloqueios de um ou mais canais na seção **[!UICONTROL No longer contact]** da guia **[!UICONTROL General]** do perfil. [Saiba mais](../audiences/view-profiles.md)

>[!NOTE]
>
>Quando os destinatários relatam sua mensagem como spam ou respondem a uma mensagem SMS com uma palavra-chave como &quot;PARAR&quot;, seu endereço ou número de telefone ficam em quarentena como **[!UICONTROL Denylisted]**. Seu perfil é atualizado adequadamente.

<!--For the email channel, email addresses are quarantined. For the mobile app channel, device tokens are quarantined. For the SMS channel, phone numbers are quarantined.?-->

## Por que um email, telefone ou dispositivo é enviado para quarentena? {#quarantine-reason}

O Adobe Campaign gerencia a quarentena de acordo com o tipo de falha do delivery e seu motivo. Eles são atribuídos durante a qualificação de mensagens de erro. Saiba mais sobre o gerenciamento de falha de entrega [nesta página](delivery-failures.md).

Dois tipos ou erros podem ser capturados:

* **Erro grave**: o endereço de email, o número de telefone ou o dispositivo é enviado imediatamente para quarentena.
* **Erro leve**: erros suaves incrementam um contador de erros e podem colocar em quarentena um email, número de telefone ou token de dispositivo. O Campaign executa [tentativas](delivery-failures.md#retries): quando o contador de erros atinge o limite, o endereço, o número de telefone ou o token do dispositivo são colocados em quarentena. [Saiba mais](delivery-failures.md#retries).

Na lista de endereços em quarentena, o campo **[!UICONTROL Error reason]** indica por que o endereço selecionado foi colocado em quarentena. [Saiba mais](#identifying-quarantined-addresses-for-the-entire-platform).


Se um usuário qualificar um email como spam, a mensagem será automaticamente redirecionada para uma caixa de entrada técnica gerenciada pela Adobe. Em seguida, o endereço de email do usuário será enviado automaticamente para quarentena com o status **[!UICONTROL Denylisted]**. Esse status se refere apenas ao endereço. O perfil não está na inclui na lista de bloqueios, para que o usuário continue recebendo mensagens SMS e notificações por push. Saiba mais sobre loops de comentários no [Guia de práticas recomendadas de entrega](https://experienceleague.adobe.com/docs/deliverability-learn/deliverability-best-practice-guide/transition-process/infrastructure.html?lang=pt-BR#feedback-loops){target="_blank"}.

>[!NOTE]
>
>A quarentena no Adobe Campaign diferencia maiúsculas de minúsculas. Certifique-se de importar endereços de email em letras minúsculas, para que não sejam redirecionados posteriormente.

## Acessar endereços em quarentena {#access-quarantined-addresses}

Os endereços em quarentena podem ser exibidos para um delivery específico ou para a plataforma inteira.

### Quarentenas para uma entrega{#delivery-quarantines}

Os endereços de quarentena são listados durante a fase de preparação do delivery, nos logs do delivery do painel de delivery.

Para cada entrega, você também pode verificar o relatório **[!UICONTROL Delivery summary]**: ele mostra o número de endereços em quarentena no público-alvo da entrega e exibe:

* O número de endereços colocados em quarentena durante a análise de entrega,
* O número de endereços colocados em quarentena após a ação de entrega.

### Endereços não entregues e rejeitados{#non-deliverable-bounces}

Para exibir a lista de endereços em quarentena **para toda a plataforma**, os administradores do Campaign podem navegar até **[!UICONTROL Administration > Campaign Management > Non deliverables Management > Non deliverables and addresses]**. Esta seção lista os elementos colocados em quarentena para os canais de **email**, **SMS** e **Notificação por push**.

![](assets/tech-quarantine.png)

>[!NOTE]
>
>O número de quarentenas aumenta com o tempo. Por exemplo, se o tempo de vida de um endereço de email for considerado três anos e a tabela de destinatários aumentar em 50% todo ano, o aumento da quarentena poderá ser calculado da seguinte maneira:
>
>Fim do Ano 1: (1&#42;0,33)/(1+0,5)=22%.
>
>Fim do ano 2: ((1,22&#42;0,33)+0,33)/(1,5+0,75)=32,5%.

Além disso, o relatório interno **[!UICONTROL Non-deliverables and bounces]**, disponível na seção **Relatórios** desta home page, exibe informações sobre os endereços em quarentena, os tipos de erro encontrados e um detalhamento de falha por domínio. Você pode filtrar os dados de um delivery específico ou personalizar este relatório conforme necessário.

Saiba mais sobre endereços rejeitados no [Manual de práticas recomendadas de capacidade de entrega](https://experienceleague.adobe.com/docs/deliverability-learn/deliverability-best-practice-guide/metrics-for-deliverability/bounces.html){target="_blank"}.

### Endereço de email na quarentena {#quarantined-recipient}

Você pode consultar o status do endereço de email de qualquer recipient.

Para fazer isso, selecione o perfil do destinatário e clique na guia **[!UICONTROL Deliveries]**. Para todos os deliveries para esse recipient, você pode descobrir se o endereço falhou, estava em quarentena durante a análise etc.

Para cada pasta, você pode exibir apenas os recipients cujo endereço de email está em quarentena, com o filtro integrado **[!UICONTROL Quarantined email address]**, conforme abaixo:

![](assets/quarantine-filter.png)


## Remover um endereço em quarentena {#remove-a-quarantined-address}

Os endereços que correspondem a condições específicas são excluídos automaticamente da lista de quarentena pelo fluxo de trabalho interno **Limpeza do banco de dados**.

Os endereços são removidos automaticamente da lista de quarentena nos seguintes casos:

* Os endereços em um status **[!UICONTROL With errors]** serão removidos da lista de quarentena após uma entrega bem-sucedida.
* Os endereços em um status **[!UICONTROL With errors]** serão removidos da lista de quarentena se o último retorno de erro tiver ocorrido há mais de 10 dias. Para obter mais informações sobre o gerenciamento de erros de software, consulte [esta seção](#soft-error-management).
* Os endereços em um status **[!UICONTROL With errors]** que tiverem retornado com o erro **[!UICONTROL Mailbox full]** serão removidos da lista de quarentena após 30 dias.

O status muda então para **[!UICONTROL Valid]**.

>[!CAUTION]
>
>Os destinatários com um endereço em um status **[!UICONTROL Quarantine]** ou **[!UICONTROL Denylisted]** nunca serão removidos, mesmo se receberem um email.

Você também pode remover manualmente um endereço da lista da quarentena. Para remover um endereço da quarentena, você pode:

* Altere seu status para **[!UICONTROL Valid]** a partir do nó **[!UICONTROL Administration > Campaign Management > Non deliverables Management > Non deliverables and addresses]**.

  ![](assets/tech-quarantine-status.png)

Talvez seja necessário executar atualizações em massa na lista de quarentena, por exemplo, no caso de uma interrupção do ISP durante a qual os emails são marcados incorretamente como rejeições porque não podem ser entregues com êxito ao recipient.

Para fazer isso, crie um workflow e adicione uma query à tabela de quarentena para filtrar todos os recipients afetados para que eles possam ser removidos da lista de quarentena e incluídos em futuros deliveries de email do Campaign.

Abaixo estão as diretrizes recomendadas para esta consulta:

* **O texto de erro (texto de quarentena)** contém “Momen_Code10_InvalidRecipient”
* **Domínio de email (@domain)** igual a domain1.com OU **Domínio de email (@domain)** igual a domain2.com OU **Domínio de email (@domain)** igual a domain3.com
* **Atualizar status (@lastModified)** em ou depois de `MM/DD/YYYY HH:MM:SS AM`
* **Atualizar status (@lastModified)** em ou antes de `MM/DD/YYYY HH:MM:SS PM`

Depois de ter a lista de recipients afetados, adicione uma atividade **[!UICONTROL Update data]** para definir seu status como **[!UICONTROL Valid]** para que eles sejam removidos da lista de quarentena pelo fluxo de trabalho **[!UICONTROL Database cleanup]**,. Também é possível excluí-los da tabela de quarentena.

