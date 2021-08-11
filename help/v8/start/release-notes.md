---
product: Adobe Campaign
title: Notas de versão do Campaign v8
description: Versão mais recente do Campaign v8
feature: Visão geral
role: Data Engineer
level: Beginner
hidefromtoc: false
exl-id: 7cf8111d-9f3a-46a4-813a-d4e43a1d1471,a9d18e75-18e7-491e-bfc4-671c3600396e
source-git-commit: 328f1bca11f8554def6ad4ccb741a86695481e98
workflow-type: ht
source-wordcount: '312'
ht-degree: 100%

---

# Versão mais recente{#latest-release}

Esta página lista novos recursos, melhorias e correções que vêm com a **versão mais recente do Campaign v8**.

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
