---
title: Notas de versão do Campaign v8 2022
description: Lista de recursos e melhorias disponíveis com as versões do Campaign v8 de 2022
feature: Release Notes
role: User
level: Beginner
exl-id: 76473fa5-48ba-42cf-8664-0dd197833a86
source-git-commit: 43994eb29af2b85272de0ce4dc34cc66aba2e04a
workflow-type: tm+mt
source-wordcount: '1919'
ht-degree: 91%

---

# Notas de versão de 2022{#2022-rn}

Esta página lista novos recursos, melhorias e correções que vêm com as **versões do Campaign v8 2022**.

## Versão 8.4.2 {#release-8-4-2}

_28 de outubro de 2022_

**Correções**

* Correção de um problema que impedia que o indicador de Entrega bem-sucedida fosse atualizado corretamente ao usar o MTA aprimorado do Adobe Campaign. (NEO-50462)

## Versão 8.4.1 {#release-8-4-1}

_30 de setembro de 2022_

**Novidades**

<table> 
<thead>
<tr> 
<th> <strong>Integração do Adobe Campaign com a Adobe Experience Platform</strong><br /> </th> 
</tr> 
</thead> 
<tbody> 
<tr> 
<td><p>Agora novos conectores de destino e de origem estão disponíveis para permitir uma integração perfeita entre o Adobe Campaign e a Adobe Experience Platform:</p>
<ul><li>Use o conector de destinos do Adobe Campaign Managed Cloud Services para enviar segmentos da Experience Platform para ativação no Adobe Campaign,</li>
<li>Use o conector de origem do Adobe Campaign Managed Cloud Service para entregas e envios de logs de rastreamento do Adobe Campaign para a Adobe Experience Platform.</li>
</ul>
<p>Para obter mais informações, consulte a <a href="../connect/ac-aep.md">documentação detalhada</a>.</p>
</td> 
</tr> 
</tbody> 
</table>

<table> 
<thead>
<tr> 
<th> <strong>Disponibilidade do canal X (anteriormente conhecido como Twitter)</strong><br /> </th> 
</tr> 
</thead> 
<tbody> 
<tr> 
<td> <p>A variável <a href="../send/twitter.md">Canal social X</a> O agora está disponível com o Campaign v8. Você pode:</p>
<ul> 
<li><p>Enviar mensagens no X (antigo Twitter): o Adobe Campaign permite postar mensagens diretamente na sua conta do X. Você também pode enviar mensagens diretas a todos os seus seguidores.
</p></li>
<li><p>Coletar novos contatos: o Adobe Campaign pode recuperar automaticamente os dados do perfil, o que permite realizar campanhas de direcionamento e implementar estratégias entre canais.
</p></li>
</ul>
<p>Saiba como conectar o Campaign e o X no <a href="../connect/ac-tw.md">documentação detalhada</a>.</p>
<p>Saiba como criar publicações e enviar mensagens diretas com o Campaign no <a href="../connect/ac-tw.md">esta página</a>.</p>
</td> 
</tr> 
</tbody> 
</table>

**Aprimoramento de segurança**

Para otimizar a segurança, os tokens de segurança foram removidos dos URLs gerados pelo Campaign:

* Essa alteração se aplica somente aos URLs GET. Outros tipos, incluindo URLs POST, não são afetados.
* Se você usa código personalizado, os tokens de segurança não são mais recuperados do parâmetro securitytoken do URL GET. Você precisa gerar um novo token de segurança usando o seguinte código JSSP:

  ```getNewSecurityToken(jsspContext.getSessionToken(), jsspContext.getSecurityToken(), true);```

  Você também pode usar a API de logon para buscar tokens de segurança.
* Não há alterações no gerenciamento de token de sessão.

**Aprimoramentos**

* Após o fim da vida útil do Microsoft Internet Explorer 11, o mecanismo de renderização de HTML no console passou a usar o **Microsoft Edge Chromium**. Além disso, a instalação do **Webview 2 runtime do Microsoft Edge** agora é necessária para qualquer instalação do console do cliente.
* Melhoria na execução do fluxo de trabalho com alta disponibilidade do fluxo de trabalho, o que permite executar fluxos de trabalho simultâneos em diferentes contêineres para evitar a perda do serviço de fluxo de trabalho e erros de execução relacionados. **Observação**: esse novo recurso foi lançado com disponibilidade limitada somente para um conjunto de clientes.
* As solicitações de privacidade agora são executadas em lote para um determinado namespace de privacidade. Essa melhoria aumenta o tempo de execução das solicitações de exclusão de GDPR/privacidade.

**Atualizações de compatibilidade**

* O SDK do Campaign v8 agora é compatível com notificações por push no iOS 16.

Consulte a [Matriz de compatibilidade do Campaign](compatibility-matrix.md).

**Correções**

* Correção de um problema que afetava as atualizações de status do log de entrega na instância MID quando a opção FeatureFlag_GZIP_Compression era habilitada. (NEO-49183)
* Correção de um problema que poderia fazer com que as entregas ficassem no status **Pendente** mesmo que a data de contato tivesse sido alcançada. (NEO-48079)
* Correção de um problema em fluxos de trabalho que poderia impedir a atualização de arquivos no servidor ao usar a atividade **Carregamento de dados (arquivo)**. O processo parou em 100%, mas nunca terminou. (NEO-47269)
* Correção de um problema durante a pós-atualização em ambientes japoneses. (NEO-46640)
* Correção de um problema que poderia ocorrer se uma entrega atingisse um tamanho específico durante o processo de MTA. (NEO-46097)
* Correção de um problema que impedia que os logs de rastreamento retornassem dados relacionados ao navegador do recipient. (NEO-46612)
* Correção de um problema que resultava em problemas de personalização ao enviar mensagens SMS usando um modo de entrega externo. (NEO-46415)
* Correção de um problema que poderia gerar duplicatas em logs de rastreamento. (NEO-46409)
* Correção de um problema que impedia que o fluxo de trabalho técnico do **[!UICONTROL Replicate Staging data]** (ffdaReplicateStagingData) fosse interrompido mesmo quando um erro ocorresse durante sua execução. (NEO-46280)
* Para evitar a lentidão ao enviar provas para os seed addresses, todas as replicações consecutivas de membros de seed agora são agrupadas em uma solicitação de replicação. (NEO-44844)
* Correção de um problema que exibia um erro ao tentar visualizar uma entrega em qualquer evento arquivado do Centro de mensagens. (NEO-43620)
* Correção de um problema ao inserir dados no banco de dados de nuvem do Snowflake com uma atividade de **Consulta** do Campaign e uma atividade **Alterar fonte de dados**: o processo falhava quando um caractere de barra invertida estava presente nos dados. A string de origem não tinha escape e os dados não eram processados corretamente no Snowflake. (NEO-45549)
* Correção de um problema ao usar a atividade de **Consulta** e filtrar uma tabela. Quando um nome de coluna continha a palavra &quot;Atualizar&quot;, ocorria um erro de compilação com um identificador inválido e a seguinte mensagem: &quot;número de linhas atualizado&quot;. (NEO-46485)
* O fluxo de trabalho técnico de **Limpeza do banco de dados** agora também lida com esquemas de preparo personalizados. (NEO-48974)
* Correção de um problema que poderia retardar a análise de entrega, durante a etapa de exclusão de incluir na lista de bloqueios de destinatários, ao direcionar grandes volumes de destinatários. (NEO-48019)
* Estabilidade aprimorada ao manipular strings XML inválidas durante chamadas SOAP. (NEO-48027)
* Correção de um problema que resultava na criação de DeliveryParts desnecessárias quando a entrega usava os modos de calendário e divisão. (NEO-48634)
* Correção de um problema de desempenho ao usar ondas baseadas em calendário. (NEO-48451)
* Correção de um problema que poderia resultar em uma mensagem de erro na tela da lista de entrega após criar um novo target mapping em um esquema personalizado. (NEO-49237)
* Correção de um problema que poderia causar perda de dados se o fluxo de trabalho de preparo estivesse com erro e o período de retenção fosse totalmente passado. (NEO-48975)

## Versão 8.3.9 {#release-8-3-9}

>[!CAUTION]
>
> a atualização do console do cliente é obrigatória. Saiba como atualizar seu console do cliente nesta [página](../start/connect.md#download-ac-console).

_7 de outubro de 2022_

**Correções**

* Correção de um problema que afetava as atualizações de status do log de entrega na instância MID quando a opção FeatureFlag_GZIP_Compression era habilitada. (NEO-49183)
* O fluxo de trabalho técnico de **Limpeza do banco de dados** agora também lida com esquemas de preparo personalizados. (NEO-48974)
* Correção de um problema que poderia fazer com que as entregas ficassem no status **Pendente** mesmo que a data de contato tivesse sido alcançada. (NEO-48079, NEO-48251)
* Estabilidade aprimorada ao manipular strings XML inválidas durante chamadas SOAP. (NEO-48027)
* Correção de um problema que poderia retardar a análise de entrega, durante a etapa de exclusão de incluir na lista de bloqueios de destinatários, ao direcionar grandes volumes de destinatários. (NEO-48019)
* Para evitar a lentidão ao enviar provas para os seed addresses, todas as replicações consecutivas de membros de seed agora são agrupadas em uma solicitação de replicação. (NEO-44844)
* Correção de um problema que resultava em problemas de personalização ao enviar mensagens SMS usando um modo de entrega externo. (NEO-46415)
* Correção de um problema que exibia um erro ao tentar visualizar uma entrega em qualquer evento arquivado do Centro de mensagens. (NEO-43620)
* Correção de um problema em fluxos de trabalho que poderia impedir a atualização de arquivos no servidor ao usar a atividade **Carregamento de dados (arquivo)**. O processo parou em 100%, mas nunca terminou. (NEO-47269)
* Correção de um problema que resultava na criação de DeliveryParts desnecessárias quando a entrega usava os modos de calendário e divisão. (NEO-48634)
* Correção de um problema de desempenho ao usar ondas baseadas em calendário. (NEO-48451)
* Correção de um problema que poderia resultar em uma mensagem de erro na tela da lista de entrega após criar um novo target mapping em um esquema personalizado. (NEO-49237)
* Correção de um problema que poderia ocorrer se uma entrega atingisse um tamanho específico durante o processo de MTA. (NEO-46097)
* Correção de um problema que impedia que os logs de rastreamento retornassem dados relacionados ao navegador do recipient. (NEO-46612)
* Correção de um problema durante a pós-atualização em ambientes japoneses. (NEO-46640)
* Correção de um problema ao usar a atividade de **Consulta** e filtrar uma tabela. Quando um nome de coluna continha a palavra &quot;Atualizar&quot;, ocorria um erro de compilação com um identificador inválido e a seguinte mensagem: &quot;número de linhas atualizado&quot;. (NEO-46485)
* Correção de um problema que impedia que o fluxo de trabalho técnico do **[!UICONTROL Replicate Staging data]** (ffdaReplicateStagingData) fosse interrompido mesmo quando um erro ocorresse durante sua execução. (NEO-46280)
* Correção de um problema que poderia causar perda de dados se o fluxo de trabalho de preparo estivesse com erro e o período de retenção fosse totalmente passado. (NEO-48975)
* Correção de um problema ao inserir dados no banco de dados de nuvem do Snowflake com uma atividade de **Consulta** do Campaign e uma atividade **Alterar fonte de dados**: o processo falhava quando um caractere de barra invertida estava presente nos dados. A string de origem não tinha escape e os dados não eram processados corretamente no Snowflake. (NEO-45549)

## Versão 8.3.8 {#release-8-3-8}

_18 de maio de 2022_

**Novidades**

<table> 
<thead>
<tr> 
<th> <strong>Notificações sensíveis ao tempo</strong><br /> </th> 
</tr> 
</thead> 
<tbody> 
<tr> 
<td> <p>Com o iOS 15, a Apple adicionou uma noção de notificação relevante, que dá controle ao desenvolvedor do aplicativo para ignorar o modo de Foco quando uma notificação é considerada relevante e precisa ser entregue ao usuário em tempo real.</p>
<p>Para obter mais informações, consulte a <a href="../send/push.md#send-notifications-on-ios">documentação detalhada</a>.</p>
</td> 
</tr> 
</tbody> 
</table>

<table> 
<thead>
<tr> 
<th> <strong>Integração do Privacy Core Service</strong><br /> </th> 
</tr> 
</thead> 
<tbody> 
<tr> 
<td> <p>O Campaign v8 agora se integra ao Adobe Privacy Core Service. As solicitações de privacidade transmitidas pelo Privacy Core Service para todas as soluções da Experience Cloud são tratadas automaticamente pelo Campaign, por meio de um fluxo de trabalho específico.</p>
<p>Para obter mais informações, consulte a <a href="privacy.md">documentação detalhada</a>.</p>
</td> 
</tr> 
</tbody> 
</table>

<table>
<thead>
<tr>
<th><strong>Gestor de Resposta</strong><br/></th>
</tr>
</thead>
<tbody>
<tr>
<td>
<p>O gestor de resposta do Campaign permite medir o sucesso e o ROI de suas campanhas de marketing ou apresentações de ofertas em todos os canais: email, celular, correspondência direta, etc.</p>
<p>Para obter mais informações, consulte a <a href="../start/campaigns.md#response-manager-add-on">documentação detalhada</a>.</p>
</td>
</tr>
</tbody>
</table>

<table> 
<thead>
<tr> 
<th> <strong>Marketing distribuído</strong><br /> </th> 
</tr> 
</thead> 
<tbody> 
<tr> 
<td> <p>O marketing distribuído do Campaign permite implementar campanhas colaborativas entre entidades centrais (sede, departamentos de marketing etc.) e entidades locais (pontos de vendas, agências regionais etc.). Por meio de um espaço de trabalho compartilhado (pacotes de campanha), você pode criar modelos de campanha e propô-los às entidades locais.</p>
<p>Para obter mais informações, consulte a <a href="../start/campaigns.md#distributed-marketing-add-on">documentação detalhada</a>.</p>
</td> 
</tr> 
</tbody> 
</table>

**Atualizações de compatibilidade**

* O SDK do Campaign v8 agora é compatível com notificações por push no Android 12 e iOS 15.
* O Campaign v8 agora é compatível com o Windows 11.

Consulte a [Matriz de compatibilidade do Campaign](compatibility-matrix.md).

**Aprimoramentos**

* A autenticação OAuth 2.0 do Microsoft Exchange Online para POP3 agora é compatível com o Campaign. [Leia mais](../config/external-accounts.md#bounce-mails-external-account)
* Correções críticas foram aplicadas em relação à API da web do Microsoft Dynamics Connector.
* O novo direito nomeado de operador e gravação de esquema de grupo (operatorWrite) foi adicionado para permitir que os usuários insiram, atualizem e excluam os esquemas de operadores (xtk:operator) e de grupos de operadores (xtk:group).
  <!--* You can now enable the Email BCC (blind carbon copy) capability to store emails sent by Campaign at the delivery level, through the dedicated option in the delivery properties. [Read more](../config/email-settings.md#email-bcc)-->
  <!--* To ensure better performances, a new "Split" option is now activated by default in the Routing external account. This option allows messages to be automatically split across your mid-sourcing instances in order to be delivered faster to the recipients.-->
* Agora, várias contas LINE ativas podem ser configuradas em um único mid-sourcing.
* O número de conexões padrão para o processo da web foi aumentado de 50 para 150.
* O Campaign vem com um conjunto de novas medidas de proteção para impedir a inserção de chaves duplicadas no banco de dados do Snowflake. [Leia mais](../architecture/keys.md)

**Correções**

* Correção de um problema que ocorria ao usar seeds e grupos de controle na mesma entrega recorrente. (NEO-41197)
* Correção de um problema no FFDA que resultava no bloqueio do envio de email para todos os destinatários pertencentes ao mesmo deliveryPart durante o processo de envio (até 256) quando os blocos de personalização continham um dos seguintes caracteres: `' & < > "`. Esses caracteres agora são permitidos em blocos de personalização (por exemplo: firstname=&quot;Brian O&#39;Neil&quot;). (NEO-43184)
* Correção de um problema que poderia causar falha no fluxo de trabalho de rastreamento ao usar um esquema personalizado como target mapping. Agora, garantimos que o tipo de link externo para um esquema de direcionamento personalizado esteja correto ao gerar o esquema broadLog por meio do assistente de target mapping. (NEO-43506)
* Correção de um problema que poderia causar falha nos fluxos de trabalho de implantação do FFDA ao usar idiomas diferentes do inglês. (NEO-44561)

## Versão 8.2.10 {#release-8-2-10}

_2 de fevereiro de 2022_

**Correções**

* Correção de um problema que causava falha na preparação da entrega se o número máximo de mensagens, definido na regra de tipologia, fosse atingido.
* Correção de um problema que ocorria durante a configuração do conector do Adobe Analytics quando o endereço de email continha um caractere “s”.
* Correção de um problema durante a pós-atualização que poderia fazer com que a tabela deliveryMapping perdesse dados de um mapeamento de entrega personalizada.
* Correção de um problema que poderia fazer com que destinatários recebessem a mesma mensagem várias vezes para a mesma entrega quando o endereço de email continha um caractere de aspas simples (&#39;). Esse caractere agora é escapado. (NEO-41198)
* Correção de um problema na geração de ID ao enviar provas com seeds ou endereços de substituição. (NEO-42637)
* Correção de um problema que impedia o envio de provas usando o método de substituição de endereço. (NEO-40417)
* Correção de um problema que impedia a instalação do pacote LINE. (NEO-42503)
