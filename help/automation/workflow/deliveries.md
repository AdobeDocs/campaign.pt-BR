---
product: campaign
title: Entregas
description: Saiba mais sobre os fluxos de trabalho de entrega padrão
feature: Workflows
role: User, Admin
version: Campaign v8, Campaign Classic v7
product_v2:
  - id: dfc56824-e8b9-499e-85d4-21aedb507314
    internal-label: Campaign
  - id: d0e9f0b2-1f2b-4134-9844-49cd4e950f27
    internal-label: Campaign v8
feature_v2:
  - id: a658c786-869b-4194-a780-2594d663adda
    internal-label: Data management
subfeature_v2:
  - id: fcb46c0f-76e1-48bc-9dd0-fcf9d97526cf
    internal-label: Workflows
role_v2:
  - id: b69b2659-1057-424e-8fc5-ed9e016dc554
    internal-label: User
  - id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
    internal-label: Admin
source-git-commit: 7fd43a8d3d6afe9f4d3fb000d925cc6185ba9f40
workflow-type: tm+mt
source-wordcount: '317'
ht-degree: 97%
---

# Entregas{#deliveries}



Os fluxos de trabalho detalhados abaixo são instalados com o módulo **Entregas** por padrão.

<table> 
 <tbody> 
  <tr> 
   <td> <strong>Rótulo</strong><br /> </td> 
   <td> <strong>Nome interno</strong><br /> </td> 
   <td> <strong>Descrição</strong><br /> </td> 
  </tr> 
  <tr> 
   <td> <span class="uicontrol">Relatórios de agregados</span> <br /> </td> 
   <td> <span class="uicontrol">reportingAggregates</span> <br /> </td> 
   <td> Esse fluxo de trabalho atualiza agregados usados em relatórios. É acionado todos os dias às 2:00 AM por padrão.<br /> </td> 
  </tr> 
  <tr> 
   <td> <span class="uicontrol">Faturamento</span> <br /> </td> 
   <td> <span class="uicontrol">billing</span> <br /> </td> 
   <td> Esse fluxo de trabalho envia o relatório de atividades do sistema para o operador "faturamento" por email. É disparado todo dia 25 de cada mês por padrão.<br /> </td> 
  </tr> 
  <tr> 
   <td> <span class="uicontrol">Limpeza de alias</span> <br /> </td> 
   <td> <span class="uicontrol">aliasCleansing</span> <br /> </td> 
   <td> Esse fluxo de trabalho padroniza os valores de enumeração. É acionado todos os dias às 3:00 AM por padrão.<br /> </td> 
  </tr> 
  <tr> 
   <td> <span class="uicontrol">Atualização para entregabilidade</span><br /> </td> 
   <td> <span class="uicontrol">deliverabilityUpdate</span> <br /> </td> 
   <td> Esse fluxo de trabalho permite criar a lista de regras de qualificação de email de devolução, bem como a lista de domínios e MXs na plataforma. Este fluxo de trabalho funciona somente se a porta HTTPS estiver aberta. Essas listas não são atualizadas a menos que o módulo Deliverability esteja instalado.<br /> </td> 
  </tr> 
  <tr> 
   <td> <span class="uicontrol">Limpeza do banco de dados</span> <br /> </td> 
   <td> <span class="uicontrol">cleanup</span> <br /> </td> 
   <td> <p>Este é o fluxo de trabalho manutenção do banco de dados: faz diferentes cálculos das estatísticas e dos processos e exclui dados obsoletos do banco de dados de acordo com a configuração definida no assistente de implantação. É acionado todos os dias às 4h por padrão.</p></td> 
  </tr> 
  <tr> 
   <td> <span class="uicontrol">Limpeza de fluxos de trabalho pausados</span> <br /> </td> 
   <td> <span class="uicontrol">cleanupPausedWorkflows</span> <br /> </td> 
   <td> <p>Triggers is translated correctly in this case. Esse fluxo de trabalho analisa fluxos de trabalho pausados que têm a severidade definida como normal e emite avisos e notificações quando ficam pausados por muito tempo. Após um mês, os fluxos de trabalho técnicos pausados são interrompidos definitivamente. Por padrão, é acionado toda segunda-feira às 5h.</p> <p>Para obter mais informações, consulte Manuseio de fluxos de trabalho pausados</a>.</p></td> 
  </tr> 
  <tr> 
   <td> <span class="uicontrol">Notificação da oferta</span> <br /> </td> 
   <td> <span class="uicontrol">offerMgt</span> <br /> </td> 
   <td> Esse fluxo de trabalho implanta ofertas aprovadas no ambiente online, bem como todas as categorias contidas no catálogo de oferta.<br /> </td> 
  </tr> 
  <tr> 
   <td> <span class="uicontrol">Previsão</span> <br /> </td> 
   <td> <span class="uicontrol">previsão</span> <br /> </td> 
   <td> Esse fluxo de trabalho analisa as entregas salvas no calendário provisional (cria logs provisionais). É acionado todos os dias às 1:00 AM por padrão.<br /> </td> 
  </tr> 
  <tr> 
   <td> <span class="uicontrol">Rastreamento</span> <br /> </td> 
   <td> <span class="uicontrol">tracking</span> <br /> </td> 
   <td> Esse fluxo de trabalho realiza a recuperação e a consolidação de informações de rastreamento. Também garante o recálculo de rastreamento e estatísticas de entrega, principalmente aqueles usados pelos fluxos de trabalho de arquivamento do Centro de Mensagens. Por padrão, é acionado uma vez por hora. <br /> </td> 
  </tr> 
 </tbody> 
</table>

