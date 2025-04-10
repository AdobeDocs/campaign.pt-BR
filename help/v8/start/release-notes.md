---
title: Notas de versão do Campaign v8
description: Versão mais recente do Campaign v8
feature: Release Notes
exl-id: 7cf8111d-9f3a-46a4-813a-d4e43a1d1471
source-git-commit: ff874a8e06303625b4c96f49fdf4f303b50fb908
workflow-type: tm+mt
source-wordcount: '597'
ht-degree: 17%

---

# Versões mais recentes {#latest-release}

Esta página lista novos recursos, melhorias e correções que vêm com o Campaign v8 (console) **versões mais recentes**. Saiba mais sobre lançamentos, versões e atualizações do Campaign em [esta página](upgrades.md). Outras versões estão listadas na seção Versões anteriores desta documentação.

>[!BEGINSHADEBOX]

**Nesta página**

* [Versão 8.7.4](#release-8-7-4)
* [Versão 8.7.3](#release-8-7-3)
* [Versão 8.6.4](#release-8-6-4)

>[!ENDSHADEBOX]

## Versão 8.7.4 {#release-8-7-4}

_sexta-feira, 10 de abril de 2025_

>[!AVAILABILITY]
>
>Esta versão está em **Disponibilidade limitada** (LA). É restrita aos clientes que estão migrando **do Adobe Campaign Standard para o Adobe Campaign v8** e não pode ser implantada em nenhum outro ambiente.
>
>Como um usuário do Campaign Standard em transição para o Campaign v8, saiba mais sobre essa transição na [documentação da interface do usuário da Web do Campaign v8](https://experienceleague.adobe.com/pt-br/docs/campaign-web/v8/start/acs-migration).

### Novos recursos {#features-8-7-4}

* **Suporte à API REST de SMS** - A API REST de Mensagens Transacionais agora está disponível para o canal de SMS. Quando email e mobilePhone estão presentes na carga, você pode usar o campo &quot;wishedChannel&quot; para especificar o canal. Se não for fornecido, o e-mail será usado por padrão, a menos que wishedChannel solicite explicitamente SMS.

* **Entregas multilíngues** - A partir da versão de abril da interface da Web do Campaign, você poderá enviar vários emails em diferentes idiomas e acessar os relatórios dinâmicos relacionados. Esse recurso só estará disponível na interface da Web do Adobe Campaign no final de abril e exigirá uma atualização do servidor para o Campaign v8.7.4.

### Correções {#fixes-8-7-4}

Os seguintes problemas foram corrigidos nesta versão:

NEO80245, NEO83559

## Versão 8.6.4 {#release-8-6-4}

_15 de janeiro de 2025_

### Melhorias gerais {#improvements-8-6-4}

* A estabilidade do aplicativo do Campaign foi aprimorada durante a análise de entrega no contexto de uma [implantação corporativa (FFDA)](../../v8/architecture/enterprise-deployment.md).
* Essa versão vem com mecanismos de arquitetura FFDA aprimorados e fortalecidos, incluindo gerenciamento de chaves, armazenamento temporário e replicação de dados.
* Novos fluxos de trabalho técnicos foram introduzidos para a [implantação corporativa (FFDA)](../../v8/architecture/enterprise-deployment.md). Esses workflows replicam o delivery e dados relacionados centralizando solicitações de replicação paralela em tabelas correspondentes. Estes fluxos de trabalho começam com `Replicate nms`. [Leia mais](../architecture/replication.md)
* Uma nova opção **Habilitar supervisor de watchdog para manter o fluxo de trabalho em execução permanentemente** agora está disponível nas propriedades do fluxo de trabalho. Quando essa opção está habilitada, os workflows são reiniciados automaticamente após um erro. A reinicialização ocorre a cada 30 segundos por padrão se o workflow ainda estiver com erro. Para ajustar esse intervalo, você pode criar uma nova opção `XtkWorkflow_WatchdogRestartTimerTimeout` e definir um tipo de dados Integer para especificar o novo atraso. Essa opção só deve ser habilitada em workflows técnicos. [Leia mais](../../automation/workflow/workflow-properties.md#execution)

### Melhorias de segurança {#security-8-6-4}

A conexão com soluções e aplicativos da Adobe por meio da conta externa da **[!UICONTROL Adobe Experience Cloud]** foi atualizada para reforçar a segurança.

<!--
### Connection to Campaign {#ims-8-6-4}

**(Limited availability)** For a restricted list of customers, Campaign v8.6.4 can allow native authentication mode instead of Adobe Identity Management System (IMS). Note that if you are using Campaign native authentication, you cannot access to [Campaign Web User Interface](../start/campaign-ui.md#campaign-web-user-interface).-->

### Atualizações de compatibilidade {#comp-8-6-4}

Os seguintes conectores FDA foram adicionados. Consulte esta [página](compatibility-matrix.md#FederatedDataAccessFDA).

* Os databricks agora são compatíveis como um banco de dados externo com o FDA (Federated Data Access — Acesso a Dados Federados) do Adobe Campaign.

* Um novo conector ODBC do Amazon Redshift FDA está disponível. Ele oferece conectividade aprimorada, manutenção mais fácil e compatibilidade aprimorada. Essa nova versão traz as seguintes melhorias:

   * O novo conector é baseado na interface ODBC que se alinha aos conectores FDA mais recentes. Isso garante suporte a longo prazo.
   * Ele também introduz um novo mecanismo de carregamento de dados usando buckets s3, melhorando significativamente o desempenho.

  O conector herdado ainda pode ser usado. Se quiser experimentar o novo, entre em contato com o representante da Adobe.

### Correções {#fixes-8-6-4}

Os seguintes problemas foram corrigidos nesta versão:

NEO48232, NEO67814, NEO71388, NEO74855, NEO75643, NEO75962, NEO76132, NEO76958, NEO76986, NEO77162, NEO77452, NEO78946, NEO79373, NEO80243, NEO80314, NEO81127, NEO81209, NEO81223, NEO81287, NEO81290, NEO8133 NEO81512, NEO81520, NEO81566, NEO81704, NEO81908, NEO82195, NEO82591, NEO82592, NEO82640, NEO82665, NEO8277 NEO82920, NEO83081, NEO83096, NEO83137, NEO83143.

