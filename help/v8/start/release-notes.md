---
title: Notas de versão do Campaign v8
description: Versão mais recente do Campaign v8
feature: Overview
role: Data Engineer
level: Beginner
hidefromtoc: false
exl-id: 7cf8111d-9f3a-46a4-813a-d4e43a1d1471,a9d18e75-18e7-491e-bfc4-671c3600396e
source-git-commit: 0061c536ff309d86061548b98d2c6e1124e01a0e
workflow-type: tm+mt
source-wordcount: '1597'
ht-degree: 50%

---

# Versão mais recente{#latest-release}

Esta página lista novos recursos, melhorias e correções que vêm com a **versão mais recente do Campaign v8**.

## Versão 8.2.1 {#release-8-2-1}

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
<p>O gerenciamento de interação em tempo real agora está disponível para canais de entrada. Use o módulo de Interação de entrada do Campaign para apresentar a melhor oferta aos clientes enquanto eles visitam seu site ou chegam à sua central de atendimento. Esse recurso vem com o Campaign v8 como uma opção e requer configuração específica em sua instância. Entre em contato com o representante do Adobe para ter acesso ao módulo de Interação de entrada.</p>
<p>Para obter mais informações, consulte a <a href="../send/interaction-architecture.md">documentação detalhada</a>.</p>
</td>
</tr>
</tbody>
</table>

<table> 
<thead>
<tr> 
<th> <strong>Otimização de campanha</strong><br /> </th> 
</tr> 
</thead> 
<tbody> 
<tr> 
<td> <p>O módulo Otimização de Campanha está disponível. Esse módulo permite controlar, filtrar e monitorar o envio de deliveries. Para evitar conflitos entre campanhas, o Adobe Campaign pode testar várias combinações aplicando regras de restrição específicas. Isso garante que as mensagens enviadas atendam melhor às necessidades e expectativas dos clientes, de acordo com as políticas de comunicação da empresa.</p>
<p>Para obter mais informações, consulte os <a href="https://experienceleague.adobe.com/docs/campaign-classic/using/orchestrating-campaigns/campaign-optimization/about-campaign-typologies.html">Documentação do Campaign Classic v7</a>.</p>
</td> 
</tr> 
</tbody> 
</table>
<table> 
<thead>
<tr> 
<th> <strong>Serviço de Unicidade</strong><br /> </th> 
</tr> 
</thead> 
<tbody> 
<tr> 
<td> <p>O Unicity Service é um novo componente do Cloud Database Manager. Ajuda os usuários a preservar e monitorar a integridade de restrições de chave exclusivas nas tabelas do banco de dados da nuvem. Isso permite reduzir o risco de inserir chaves duplicadas.
<p>Como o banco de dados da nuvem não impõe restrições de unicidade, o Unicity Service introduz no nível do aplicativo, <b>um conjunto de novas medidas de proteção</b> reduza o risco de inserir duplicatas ao gerenciar os dados com o Adobe Campaign.</p> 
<p>O Unicity Service inicia um novo fluxo de trabalho interno chamado <b>ffdaUnicity</b> para monitorar as restrições de unicidade e alertar quando forem detectadas duplicatas.</p></td> </tr> 
</tbody> 
</table>

**Aprimoramentos**

* O conector de Snowflake foi aprimorado em termos de desempenho.
* No arquivo de configuração do servidor (serverConf.xml), agora é possível definir um tempo de espera, por esquema, entre atualizações e replicações de confirmação em tempo real.
* Para fins de monitoramento e teste, os logs de auditoria do **[!UICONTROL Replicate Staging data]** O fluxo de trabalho agora inclui o número de registros que foram enviados para o banco de dados FDA (Full Federated Data Access).
* A atividade do código SQL agora permite escolher em qual banco de dados o script SQL será armazenado: a fonte de dados padrão ou uma conta externa FDA ativa escolhida.
* Um conjunto de depósitos predefinidos agora está disponível e pode ser usado para executar várias consultas em paralelo, como segmentação, ETL ou picos. [Leia mais](../config/workflows.md)

**Outras alterações**

* O **[!UICONTROL Encrypted identifier]** foi adicionado ao esquema do visitante (`nms:visitor`). Este campo é calculado e deve ser usado para aplicações web.
* Correção de um problema que causava a falha da análise de delivery quando algumas afinidades de IP existiam em alguns contêineres de mid-sourcing, mas não em todos. Agora, as afinidades de IP são todas armazenadas no banco de dados, para que qualquer contêiner possa acessar as afinidades presentes em todos os outros contêineres. (NEO-37564)
* Agora é possível importar um pacote com vários schemas e nós de árvore de navegação.

**Correções**

* Depois que um usuário removia, em um schema de dados, a variável `<autoStg>` atributo de um elemento de definição de tabela ou alterado seu valor de `true` para `false`, a tabela de preparo relacionada não foi excluída. Esse problema foi corrigido.
* Correção de um problema que causava um erro ao criar registros com um formulário dedicado devido ao gerenciamento de ID com uma fonte de dados FFDA.
* Correção de um problema que impedia a inserção de ofertas em um delivery se as ofertas fossem gerenciadas por uma atividade de enriquecimento em um workflow.
* Correção de um problema que poderia atrasar a importação de pacotes.
* Correção de um problema que impedia o envio de deliveries de email com seed addresses.
* Correção de um problema que impedia que apresentações fossem salvas na tabela de apresentações de oferta.
* Correção de um problema que fazia com que os problemas de tempo limite da rede fossem registrados incorretamente como problemas de interrupção de script em vez de erros de rede. Esse problema ocorria no caso de solicitações HTTP incluídas em atividades JavaScript.
* Correção de um problema que impedia a replicação de ofertas para o ambiente de oferta ao vivo no Snowflake.
* Correção de um problema que ignorava o atributo &quot;autoStg&quot; para esquemas internos não estendidos.
* Correção de um problema que impedia os usuários de selecionar o **[!UICONTROL Country/Region]** ao visualizar um perfil.
* Correção de um problema que fazia com que o datepicker em relatórios personalizados resultasse em um erro de script. (NEO-36345)
* Correção de um problema que resultava em falha do sistema ao gerar novamente a configuração em caso de arquivos de configuração inválidos.
* Correção de um problema que impedia que as instâncias de marketing e de controle fossem atualizadas com êxito.
* Correção de um problema que resultava em falha do workflow de cobrança em instâncias de marketing.
* Correção de um problema que poderia resultar em chaves duplicadas em tabelas predefinidas do Snowflake FDA. (NEO-38583)
* Correção de um problema que poderia resultar na perda de esquemas temporários de workflow ao editar duas atividades de desduplicação, uma após a outra. (NEO-34063)
* Correção de um problema que retornava resultados incorretos ao executar as funções Amazon Redshift HoursDiff e MinutesDiff ao tentar extrair o componente de tempo.(NEO-31673)
* Correção de um problema que impedia usuários de fazer logon no console devido a um problema de configuração de proxy. (NEO-38388)
* Correção de um problema de regressão que impedia o **Pasta de limpeza** funcionasse corretamente. (NEO-37459)
* Correção de um problema que impedia a visualização de deliveries de dispositivos móveis anexados a um workflow.
* Correção de um problema que poderia impedir que a variável **Lista de leitura** A atividade do workflow não funciona quando a lista foi identificada no banco de dados com uma ID negativa. (NEO-39607)

## Versão 8.1.20 {#release-8-1-20}

_7 de setembro de 2021_

**Melhorias de segurança**

* Correção de um problema de segurança para reforçar a proteção contra ataques de travessia de diretórios. (NEO-28547)

**Aprimoramentos**

* Após o fim da vida útil, o Flash foi removido de todos os recursos e componentes relacionados do Campaign e substituído pelo HTML5. O tipo de gráfico **Medição** foi removido. (NEO-30330) [Leia mais](https://experienceleague.adobe.com/docs/campaign-classic/using/reporting/creating-new-reports/creating-a-chart.html?lang=pt-BR)
* Ao instalar o console do cliente no Windows, o instalador agora verifica se há um nó de registro pai e cria um se estiver ausente. Isso evita possíveis problemas ao iniciar o console. (NEO-34854)
* O recurso de assinatura de rastreamento foi aprimorado para evitar erros vinculados à forma como as ferramentas de terceiros (clientes de email, navegadores de Internet etc.) lidam com caracteres especiais. Os parâmetros de URL agora são codificados.

**Outras alterações**

* Os conectores do Microsoft CRM obsoletos anteriormente (implantações do Office 365 e no local) foram removidos da interface. [Leia mais](https://experienceleague.adobe.com/docs/campaign-classic/using/getting-started/connectors/crm-connectors/crm-ms-dynamics.html?lang=pt-BR#configure-acc-for-microsoft)
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
