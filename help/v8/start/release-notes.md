---
product: Adobe Campaign
title: Notas de versão do Campaign v8
description: Versão mais recente do Campaign v8
feature: Overview
role: Data Engineer
level: Beginner
hidefromtoc: false
exl-id: 7cf8111d-9f3a-46a4-813a-d4e43a1d1471,a9d18e75-18e7-491e-bfc4-671c3600396e
source-git-commit: 5b81c8e9e391ea1a9ad1825e5102b66c7926c204
workflow-type: ht
source-wordcount: '756'
ht-degree: 100%

---

# Versão mais recente{#latest-release}

Esta página lista novos recursos, melhorias e correções que vêm com a **versão mais recente do Campaign v8**.

## Versão 8.1.20 {#release-8-1-20}

_7 de setembro de 2021_

**Melhorias de segurança**

* Correção de um problema de segurança para reforçar a proteção contra ataques de travessia de diretórios. (NEO-28547)

**Melhorias**

* Após o fim da vida útil, o Flash foi removido de todos os recursos e componentes relacionados do Campaign e substituído pelo HTML5. O gráfico do tipo **Medidor** foi removido. (NEO-30330) [Leia mais](https://experienceleague.adobe.com/docs/campaign-classic/using/reporting/creating-new-reports/creating-a-chart.html?lang=pt-BR)
* Ao instalar o console do cliente no Windows, o instalador agora verifica se há um nó de registro pai, criando-o caso seja necessário. Isso evita possíveis problemas ao iniciar o console. (NEO-34854)
* O recurso de assinatura de rastreamento foi aprimorado para evitar que erros vinculados às ferramentas de terceiros (clientes de email, navegadores de Internet etc.) manipulem caracteres especiais. Os parâmetros de URL agora são codificados.

**Outras alterações**

* Os conectores do CRM da Microsoft, que já tinham sido descontinuados (implementações no local e do Office 365), foram removidos da interface. [Leia mais](https://experienceleague.adobe.com/docs/campaign-classic/using/getting-started/connectors/crm-connectors/crm-ms-dynamics.html?lang=pt-BR#configure-acc-for-microsoft)
* Após a migração para o Tomcat 8, o script de configuração do IIS foi atualizado para corrigir problemas de integração do IIS. (NEO-31019)
* Uma proteção foi adicionada para permitir que apenas o [fluxo de trabalho técnico de faturamento](https://experienceleague.adobe.com/docs/campaign-classic/using/monitoring-campaign-classic/production-procedures/monitoring-processes.html?lang=pt-BR#billing-report) seja executado na instância de marketing.
* A identificação da fonte de dados foi aprimorada nas guias de dados e esquema da janela **Exibir população** das transições do fluxo de trabalho.
* Os índices de banco de dados ausentes foram adicionados aos seguintes esquemas para evitar problemas de atualização do banco de dados: xtk:rights, nms:dlvExclusion, nms:seedMember, nms:trackingUrl

**Correções**

* Correção de um problema que impedia o funcionamento do relatório **Hot clicks** quando as ofertas eram vinculadas à entrega. (NEO-26295)
* Correção de um problema na atividade **Sub-workflow** quando sua execução não gerava uma tabela de saída. (NEO-36242)
* Correção de vários problemas ao exportar o relatório de **Análise descritiva** para PDF. (NEO-25847)
* Correção de um problema que podia resultar em falha de entrega ao ser usada uma entrega de email externo. (NEO-37435)
* Correção de um erro ao se conectar ao Microsoft CRM usando a API da Web. A mensagem de erro foi removida, pois as funcionalidades não foram afetadas.
* Correção de um problema de desduplicação de log de rastreamento quando o servidor mid era definido como uma retransmissão entre servidores de rastreamento e de marketing. (NEO-36285)
* Correção de uma regressão que impedia o Vault de ser usado como um armazenamento de código específico.
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
