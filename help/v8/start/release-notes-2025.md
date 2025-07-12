---
title: Notas de versão do Campaign v8 (console) de 2025
description: Lista de recursos e melhorias disponíveis nas versões 2025 do Campaign v8
feature: Release Notes
exl-id: 3f91d83e-594e-49ee-a898-606e3de00bf3
source-git-commit: b52308bcbe68a7c382918fe28f8166e3bfcb6cde
workflow-type: tm+mt
source-wordcount: '931'
ht-degree: 96%

---

# Notas de versão de 2025 {#2025-rn}

Esta página lista novos recursos, melhorias e correções incluídos nas **versões do Campaign v8 de 2025**.  Para obter a versão mais recente, consulte [esta página](release-notes.md).

Para qualquer nova implementação ou atualização para um ambiente existente, instale a [versão mais recente](release-notes.md).

>[!BEGINSHADEBOX]

**Nesta página**

* [Versão 8.6.5](#release-8-6-5)
* [Versão 8.6.4](#release-8-6-4)
* [Versão 8.7.4](#release-8-7-4)
* [Versão 8.7.3](#release-8-7-3)


>[!ENDSHADEBOX]

## Versão 8.6.5 {#release-8-6-5}

_25 de abril de 2025_

>[!AVAILABILITY]
>
>Esta versão está em **disponibilidade limitada** (LA). 

### Novos recursos {#features-8-6-5}

**Novo conector de envio de SMS**: o conector de envio de SMS foi modernizado e aprimorado para permitir conexões SMPP no modo transceptor, permitir conexões SMPP persistentes e garantir uma melhor compatibilidade para ambientes em transição do Adobe Campaign Standard. Uma nova conta externa de SMS agora está disponível para todas as novas implementações de SMS. A implementação atual ainda é compatível, mas é recomendável mudar para esse novo conector moderno e estendido. [Leia mais](../send/sms/sms.md).

### Melhorias gerais {#improvements-8-6-5}

* O desempenho global do aplicativo foi aprimorado no contexto de uma implantação corporativa (FFDA), incluindo o envio de provas de entrega e limpeza do banco de dados.

* Para aumentar a segurança de todas as comunicações entre aplicativos, o mTLS agora é compatível com chamadas de API externas.

* Agente de transferência de correspondência (MTA): correção do MTA derivado órfão, que ficava preso no status **[!UICONTROL Start pending]**.

### Correções {#fixes-8-6-5}

Os seguintes problemas também foram corrigidos nesta versão:

NEO-67620, NEO-71534, NEO-80245, NEO-81105, NEO-81758, NEO-81908, NEO-82351, NEO-82742, NEO-83044, NEO-83138, NEO-83350, NEO-83729, NEO-83793, NEO-83809, NEO-84038, NEO-84108, NEO-85269, NEO-86121, NEO-86556, NEO-86739

## Versão 8.7.4 {#release-8-7-4}

_10 de abril de 2025_

>[!AVAILABILITY]
>
>Esta versão está em **Disponibilidade limitada** (LA). É restrita aos clientes que estão migrando **do Adobe Campaign Standard para o Adobe Campaign v8** e não pode ser implantada em nenhum outro ambiente.
>
>Como usuário do Campaign Standard em transição para o Campaign v8, saiba mais sobre essa migração na [documentação da interface do Campaign Web v8](https://experienceleague.adobe.com/pt-br/docs/campaign-web/v8/start/acs-migration){target="_blank"}.

### Novos recursos {#features-8-7-4}

* **Suporte à API REST de SMS**: a API REST de mensagens transacionais agora está disponível para o canal de SMS. Quando email e mobilePhone estão presentes no conteúdo, você pode usar o campo “wishedChannel” para especificar o canal. Se não for fornecido, o email será usado por padrão, a menos que wishedChannel solicite o SMS explicitamente. 

* **Entregas multilíngues**: a partir da versão de abril da interface do Campaign Web, você poderá enviar vários emails em diferentes idiomas e acessar os relatórios dinâmicos relacionados. Esse recurso só estará disponível na interface do Adobe Campaign Web no final de abril e exigirá uma atualização do servidor para o Campaign v8.7.4.

### Correções {#fixes-8-7-4}

Os seguintes problemas foram corrigidos nesta versão:

NEO-80245, NEO-83559

## Versão 8.7.3 {#release-8-7-3}

_14 de fevereiro de 2025_

>[!AVAILABILITY]
>
>Esta versão está em **Disponibilidade limitada** (LA). É restrita aos clientes que estão migrando **do Adobe Campaign Standard para o Adobe Campaign v8** e não pode ser implantada em nenhum outro ambiente.
>
>Como usuário do Campaign Standard em transição para o Campaign v8, saiba mais sobre essa migração na [documentação da interface do Campaign Web v8](https://experienceleague.adobe.com/pt-br/docs/campaign-web/v8/start/acs-migration){target="_blank"}.

### Novos recursos {#features-8-7-3}

* **Relatórios dinâmicos para mensagens transacionais**: agora você pode monitorar as mensagens transacionais na interface de relatórios dinâmicos. Esses relatórios oferecem a profissionais de marketing a capacidade de visualizar todas as métricas e dimensões de relatórios de mensagens transacionais, além de detalhar entregas enviadas por meio de um modelo em tempo real. [Leia mais](https://experienceleague.adobe.com/docs/campaign-web/v8/reports/dynamic-reporting/get-started-reporting.html?lang=pt-BR){target="_blank"}

* **APIs REST de mensagens transacionais**: as APIs transacionais baseadas em eventos agora estão disponíveis para emails. [Leia mais](../dev/api/get-started-apis.md)

### Correções {#fixes-8-7-3}

Os seguintes problemas foram corrigidos nesta versão:

NEO-79373, NEO-81908, NEO-83081

## Versão 8.6.4 {#release-8-6-4}

_15 de janeiro de 2025_

### Melhorias gerais {#improvements-8-6-4}

* A estabilidade do aplicativo do Campaign foi aprimorada durante a análise de entrega no contexto de [implantação corporativa (FFDA)](../../v8/architecture/enterprise-deployment.md).
* Essa versão inclui mecanismos de arquitetura FFDA aprimorados e fortalecidos, incluindo gerenciamento de chaves, preparo e replicação de dados.
* Novos fluxos de trabalho técnicos foram introduzidos para a [implantação corporativa (FFDA)](../../v8/architecture/enterprise-deployment.md). Esses fluxos de trabalho replicam a entrega e dados relacionados centralizando solicitações de replicação paralelas em tabelas correspondentes. Esse fluxo de trabalho começa com `Replicate nms`. [Leia mais](../architecture/replication.md)
* Uma nova opção **Habilitar supervisor de watchdog para manter o fluxo de trabalho em execução permanente** agora está disponível nas propriedades do fluxo de trabalho. Quando essa opção está habilitada, os fluxos de trabalho são reiniciados automaticamente após um erro. A reinicialização ocorre a cada 30 segundos por padrão se o fluxo de trabalho ainda estiver com erro. Para ajustar esse intervalo, você pode criar uma nova opção `XtkWorkflow_WatchdogRestartTimerTimeout` e utilizar o tipo de dados “Inteiro” para especificar o novo atraso. Essa opção só deve ser habilitada em fluxos de trabalho técnicos. [Leia mais](../../automation/workflow/workflow-properties.md#execution)

### Melhorias de segurança {#security-8-6-4}

A conexão com soluções e aplicativos da Adobe por meio da conta externa da **[!UICONTROL Adobe Experience Cloud]** foi atualizada para reforçar a segurança.

<!--
### Connection to Campaign {#ims-8-6-4}

**(Limited availability)** For a restricted list of customers, Campaign v8.6.4 can allow native authentication mode instead of Adobe Identity Management System (IMS). Note that if you are using Campaign native authentication, you cannot access to [Campaign Web User Interface](../start/campaign-ui.md#campaign-web-user-interface).-->

### Atualizações de compatibilidade {#comp-8-6-4}

Os seguintes conectores FDA foram adicionados. Consulte esta [página](compatibility-matrix.md#FederatedDataAccessFDA).

* Os databricks agora são compatíveis como um banco de dados externo no Federated Data Access (FDA) do Adobe Campaign. 

* Agora há um novo conector ODBC de FDA do Amazon Redshift disponível. Ele oferece conectividade aprimorada, manutenção mais fácil e compatibilidade aprimorada. Essa nova versão traz as seguintes melhorias:

   * O novo conector é baseado na interface ODBC que se alinha aos conectores FDA mais recentes. Isso garante suporte a longo prazo.
   * Ele também introduz um novo mecanismo de carregamento de dados usando buckets s3, melhorando significativamente o desempenho.

  O conector legado ainda pode ser usado. Se quiser experimentar o novo, entre em contato com um(a) representante da Adobe.

### Correções {#fixes-8-6-4}

Os seguintes problemas foram corrigidos nesta versão:

NEO-48232, NEO-67814, NEO-71388, NEO-74855, NEO-75643, NEO-75962, NEO-76132, NEO-76958, NEO-76986, NEO-77162, NEO-77452, NEO-78946, NEO-79373, NEO-80243, NEO-80314, NEO-81127, NEO-81209, NEO-81223, NEO-81287, NEO-81290, NEO-81312, NEO-81512, NEO-81520, NEO-81566, NEO-81704, NEO-81908, NEO-82195, NEO-82591, NEO-82592, NEO-82640, NEO-82665, NEO-82781, NEO-82920, NEO-83081, NEO-83096, NEO-83137, NEO-83143.

