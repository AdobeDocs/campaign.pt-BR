---
title: Notas de versão do Campaign v8
description: Versão mais recente do Campaign v8
feature: Overview
role: Data Engineer
level: Beginner
hidefromtoc: false
exl-id: 7cf8111d-9f3a-46a4-813a-d4e43a1d1471
source-git-commit: 0a55d947a7646aab64ab2f9d0d09a6f930db576e
workflow-type: tm+mt
source-wordcount: '2160'
ht-degree: 99%

---

# Versão mais recente{#latest-release}

Esta página lista novos recursos, melhorias e correções que vêm com a **versão mais recente do Campaign v8**.

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

* Correção de um problema que causava falha na preparação do delivery se o número máximo de mensagens, definido na regra de tipologia, fosse atingido.
* Correção de um problema que ocorria durante a configuração do conector do Adobe Analytics quando o endereço de email continha um caractere “s”.
* Correção de um problema durante a pós-atualização que poderia fazer com que a tabela deliveryMapping perdesse dados de um mapeamento de delivery personalizado.
* Correção de um problema que poderia fazer com que recipients recebessem a mesma mensagem várias vezes para o mesmo delivery quando o endereço de email continha um caractere de aspas simples (&#39;). Esse caractere agora é escapado. (NEO-41198)
* Correção de um problema na geração de ID ao enviar provas com seeds ou endereços de substituição. (NEO-42637)
* Correção de um problema que impedia o envio de provas usando o método de substituição de endereço. (NEO-40417)
* Correção de um problema que impedia a instalação do pacote LINE. (NEO-42503)

## Versão 8.2.8 {#release-8-2-8}

_28 de outubro de 2021_

<table>
<thead>
<tr>
<th><strong>Interação de entrada</strong><br/></th>
</tr>
</thead>
<tbody>
<tr>
<td>
<p>O gerenciamento de interação em tempo real agora está disponível para canais de entrada. Use o módulo de Interação de entrada do Campaign para apresentar a melhor oferta para seus clientes quando eles visitarem seu site ou procurarem sua central de atendimento. Esse recurso vem como opção no Campaign v8 e exige uma configuração específica na sua instância. Procure seu representante da Adobe para ter acesso ao módulo de Interação de entrada.</p>
<p>Para obter mais informações, consulte a <a href="../interaction/interaction-architecture.md">documentação detalhada</a>.</p>
</td>
</tr>
</tbody>
</table>

<table> 
<thead>
<tr> 
<th> <strong>Campaign Optimization</strong><br /> </th> 
</tr> 
</thead> 
<tbody> 
<tr> 
<td> <p>O módulo de otimização de campanha agora está disponível. Esse módulo permite controlar, filtrar e monitorar o envio de deliveries. Para evitar conflitos entre campanhas, o Adobe Campaign pode testar várias combinações aplicando regras de restrição específicas. Isso garante que as mensagens enviadas atendam melhor às necessidades e expectativas dos clientes, de acordo com as políticas de comunicação da empresa.</p>
<p>Para obter mais informações, consulte a <a href="https://experienceleague.adobe.com/docs/campaign/automation/campaign-optimization/campaign-typologies.html?lang=en#campaign-optimization">documentação detalhada</a>.</p>
</td> 
</tr> 
</tbody> 
</table>

<table> 
<thead>
<tr> 
<th> <strong>Unicity Service</strong><br /> </th> 
</tr> 
</thead> 
<tbody> 
<tr> 
<td> <p>O Unicity Service é um novo componente do Cloud Database Manager. Ele ajuda os usuários a preservar e monitorar a integridade das restrições de chaves únicas dentro de tabelas do Cloud Database. Isso permite reduzir o risco de inserir chaves duplicadas.
<p>Como o Cloud Database não impõe restrições de unicidade, o Unicity Service introduz, no nível do aplicativo, <b>um novo conjunto de medidas de proteção</b> que reduzem o risco de inserir duplicatas ao gerenciar dados com o Adobe Campaign.</p> 
<p>O Unicity Service inicia um novo workflow incorporado chamado <b>ffdaUnicity</b> para monitorar restrições de unicidade e alertar quando duplicatas são detectadas.</p>
<p>Para obter mais informações, consulte a <a href="../architecture/keys.md">documentação detalhada</a>.</p>
</td> </tr> 
</tbody> 
</table>

<!--
<table> 
<thead>
<tr> 
<th> <strong>Twitter channel availability</strong><br /> </th> 
</tr> 
</thead> 
<tbody> 
<tr> 
<td> <p>The <a href="../send/twitter.md">Twitter social channel</a> is now available with Campaign v8. You can:</p>
<ul> 
<li><p>Send messages on Twitter: Adobe Campaign lets you post messages directly to your twitter account. You can also send direct messages to all your followers.
</p></li>
<li><p>Collect new contacts: Adobe Campaign can automatically recovers the profile data, which enables you to carry out targeting campaigns and implement cross-channel strategies.
</p></li>
</ul>
<p>Learn how to connect Campaign and Twitter in the <a href="../connect/ac-tw.md">detailed documentation</a>.</p>
<p>Learn how to post tweets and send direct messages with Campaign in <a href="../connect/ac-tw.md">this page</a>.</p>
</td> 
</tr> 
</tbody> 
</table>
-->

**Aprimoramentos** 

* O conector Snowflake foi aprimorado em termos de desempenho.
* Para propósitos de monitoramento e teste, os logs de auditoria do workflow **[!UICONTROL Replicate Staging data]** agora incluem o número de registros enviados para a base de dados do FFDA (Full Federated Data Access).
* A atividade de código SQL agora permite escolher em qual base de dados o script SQL será armazenado: na fonte de dados padrão ou em uma conta externa de FDA ativo.
* Um conjunto de warehouses predefinidos está agora disponível e pode ser usado para executar várias consultas em paralelo, tais como segmentação, ETL ou picos. [Leia mais](../config/workflows.md)

**Outras alterações**

* O campo **[!UICONTROL Encrypted identifier]** foi adicionado ao esquema de visitante (`nms:visitor`). Esse campo é calculado e deve ser usado para aplicativos web.
* Correção de um problema que causava a falha da análise de delivery quando algumas afinidades de IP existiam em certos contêineres mid-sourcing, mas não em todos eles. Agora as afinidades de IP são armazenadas na base de dados para que qualquer container possa acessar as afinidades presentes em todos os outros contêineres. (NEO-37564)
* Agora você pode importar um pacote com vários esquemas e nós da árvore de navegação.

**Correções**

* Após um usuário ter removido, de um esquema de dados, o atributo `<autoStg>` de um elemento de definição de uma tabela, ou após ter alterado seu valor de `true` para `false`, a tabela de preparo relacionada não foi excluída. Esse problema foi corrigido.
* Correção de um problema que causava um erro ao criar registros com um formulário dedicado devido ao gerenciamento de ID com uma fonte de dados FFDA.
* Correção de um problema que poderia impedir a inserção de ofertas em um delivery caso tais ofertas fossem gerenciadas por uma atividade de enriquecimento em um workflow.
* Correção de um problema que poderia retardar a importação de pacotes.
* Correção de um problema que poderia impedir que deliveries de email com seed addresses fossem enviados.
* Correção de um problema que poderia impedir que apresentações fossem salvas na tabela de apresentação de ofertas.
* Correção de um problema que ocasionava o registro incorreto de complicações de tempo limite como interrupções de script, em vez de erros de rede. Esse problema ocorria no caso de solicitações HTTP que eram incluídas em atividades JavaScript.
* Correção de um problema que evitava que as ofertas fossem replicadas para o ambiente de ofertas em tempo real no Snowflake.
* Correção de um problema que fazia com que o atributo “autoStg” fosse ignorado em esquemas integrados não estendidos.
* Correção de um problema que impedia os usuários de selecionarem o link **[!UICONTROL Country/Region]** durante a pré-visualização de um perfil.
* Correção de um problema que fazia com que o datepicker de um relatório personalizado resultasse em um erro de script. (NEO-36345)
* Correção de um problema que fazia com que o sistema falhasse ao regenerar uma configuração, no caso de arquivos mal configurados.
* Correção de um problema que impedia que as instâncias de marketing e controle fossem atualizadas com sucesso.
* Correção de um problema que podia fazer com que o fluxo de trabalho de faturamento falhasse em instâncias de marketing.
* Correção de um problema que poderia causar a duplicação de chaves em tabelas prontas para uso no FFDA do Snowflake. (NEO-38583)
* Correção de um problema que podia causar a perda de esquemas temporários de fluxos de trabalho ao editar duas atividades de desduplicação em sequência. (NEO-34063)
* Correção de um problema que retornava resultados incorretos ao executar as funções HoursDiff e MinutesDiff do Amazon Redshift para tentar extrair o componente de tempo.(NEO-31673)
* Correção de um problema que podia impedir os usuários de fazerem logon no console em função de um problema de configuração de proxy. (NEO-38388)
* Correção de um problema de regressão que impedia o funcionamento correto da funcionalidade **Limpar pasta**. (NEO-37459)
* Correção de um problema que podia impedir a pré-visualização de deliveries de dispositivos móveis que foram anexados a um fluxo de trabalho.
* Correção de um problema que podia impedir o funcionamento da atividade de fluxo de trabalho **Lista de leitura** quando a lista era identificada com uma ID negativa na base de dados. (NEO-39607)

## Versão 8.1.20 {#release-8-1-20}

_7 de setembro de 2021_

**Melhorias de segurança**

* Correção de um problema de segurança para reforçar a proteção contra ataques de travessia de diretórios. (NEO-28547)

**Aprimoramentos**

* Após o fim da vida útil, o Flash foi removido de todos os recursos e componentes relacionados do Campaign e substituído pelo HTML5. O tipo de gráfico **Medição** foi removido. (NEO-30330) [Leia mais](https://experienceleague.adobe.com/docs/campaign-classic/using/reporting/creating-new-reports/creating-a-chart.html?lang=pt-BR)
* Ao instalar o console do cliente no Windows, o instalador agora verifica se há um nó de registro pai e cria um se estiver ausente. Isso evita possíveis problemas ao iniciar o console. (NEO-34854)
* O recurso de assinatura de rastreamento foi aprimorado para evitar erros vinculados à forma como as ferramentas de terceiros (clientes de email, navegadores de Internet etc.) lidam com caracteres especiais. Os parâmetros de URL agora são codificados.

**Outras alterações**

* Os conectores do Microsoft CRM descontinuados anteriormente (implantações do Office 365 e locais) foram removidos da interface. [Leia mais](https://experienceleague.adobe.com/docs/campaign-classic/using/getting-started/connectors/crm-connectors/crm-ms-dynamics.html?lang=pt-BR#configure-acc-for-microsoft)
* Após a migração para o Tomcat 8, o script de configuração do IIS foi atualizado para corrigir problemas de integração do IIS. (NEO-31019)
* Uma garantia foi adicionada para permitir que o [fluxo de trabalho técnico de faturamento](https://experienceleague.adobe.com/docs/campaign-classic/using/monitoring-campaign-classic/production-procedures/monitoring-processes.html?lang=pt-BR#billing-report) seja executado na instância de marketing.
* A identificação da fonte de dados foi aprimorada nas guias de dados e esquema da janela **Exibir população** das transições do fluxo de trabalho.
* Os índices de banco de dados ausentes foram adicionados aos seguintes esquemas para evitar problemas de atualização do banco de dados: xtk:rights, nms:dlvExclusion, nms:seedMember, nms:trackingUrl

**Correções**

* Correção de um problema que impedia o funcionamento do relatório **Hot clicks** quando as ofertas eram vinculadas à entrega. (NEO-26295)
* Correção de um problema com a atividade **Sub-workflow** quando sua execução não gerava uma tabela de saída. (NEO-36242)
* Correção de vários problemas ao exportar o relatório de **Análise descritiva** para PDF. (NEO-25847)
* Correção de um problema que poderia resultar em falha de entrega ao usar uma entrega de email externa. (NEO-37435)
* Correção de um erro ao se conectar ao Microsoft CRM usando a API da Web. A mensagem de erro foi removida, pois as funcionalidades não foram afetadas.
* Correção de um problema de desduplicação de log de rastreamento quando o servidor mid era definido como uma retransmissão entre servidores de rastreamento e de marketing. (NEO-36285)
* Correção de uma regressão que impedia o Cofre de ser usado como um armazenamento de código específico.
* Correção de um problema que impedia o uso de variáveis em uma atividade de fluxo de trabalho de **Enriquecimento** quando a transição recebida era de uma fonte de dados FDA.
* Correção de um problema com o FFDA que impedia a replicação adequada de grupos e direitos de operadores.
* Correção de um problema que podia resultar no envio de um link de unsubscription incorreto por meio da entrega.
* Correção de um problema no gerenciamento de replicação que afetava a duração da pós-atualização.
* Correção de um problema que podia impedir a exibição do **Hot click**.
* Correção de um problema que podia resultar em URLs inválidos em mensagens de email.

## Versão 8.1.14 {#release-8-1-14}

_23 de julho de 2021_

**Novidades**

<table>
<thead>
<tr>
<th><strong>Nova atividade de fluxo de trabalho: Alterar fonte de dados</strong><br/></th>
</tr>
</thead>
<tbody>
<tr>
<td>
<p>A nova atividade de fluxo de trabalho <b>Alterar fonte de dados</b> permite alterar a fonte de dados de uma tabela de trabalho do fluxo de trabalho. Isso proporciona mais flexibilidade no gerenciamento de dados em diferentes fontes de dados (FDA, FDA e banco de dados local).</p>
<p>Nos workflows do Adobe Campaign, os dados são gerenciados usando tabelas de trabalho (ou temporárias). Conforme o fluxo de trabalho é executado, as tabelas de trabalho compartilham dados entre atividades de fluxo de trabalho. Por padrão, as tabelas de trabalho são criadas no mesmo banco de dados da fonte de dados que consultamos.</p>
<p>Com o Campaign v8, a tabela de perfis principais é armazenada no banco de dados da nuvem diretamente. Assim, consultar a tabela Perfis também criará uma tabela de trabalho no banco de dados da nuvem. Em certos casos, pode fazer sentido mover a tabela de trabalho para outra fonte de dados para executar operações específicas.</p>
<p>Para obter mais informações, consulte a <a href="../config/workflows.md#change-data-source-activity">documentação detalhada</a>.</p>
</td>
</tr>
</tbody>
</table>

<table> 
<thead>
<tr> 
<th> <strong>Disponibilidade do canal LINE</strong><br /> </th> 
</tr> 
</thead> 
<tbody> 
<tr> 
<td> <p>O <a href="../send/line.md">canal LINE</a> agora está disponível com o Campaign v8, incluindo os seguintes aprimoramentos quando combinado com o módulo <a href="../send/transactional.md">mensagens transacionais</a>:
<ul> 
<li><p>Correção de um problema que impedia que visitantes fossem direcionados em uma entrega LINE. 
</p></li>
<li><p>Correção de um problema que poderia causar erros ao recuperar visitantes da instância de execução para a instância de marketing.
</p></li>
<li><p>Correção de problemas durante o processamento de eventos em tempo real.</p></li>
</ul>
</td> 
</tr> 
</tbody> 
</table>


**Outras melhorias**

* Correção de um problema que poderia impedir que o relatório **Hot clicks** fosse exibido para entregas específicas.
* Correção de um problema com a atividade de fluxo de trabalho **Desduplicação** que podia resultar em uma contagem duplicada imprecisa.
* Correção de um problema ao ser usada uma consulta de fluxo de trabalho com o filtro &quot;ID não está vazia&quot; que podia resultar na exibição de um item vazio na população de transição.
* Correção de um problema que impedia a criação de campos adicionais em um novo target mapping.
