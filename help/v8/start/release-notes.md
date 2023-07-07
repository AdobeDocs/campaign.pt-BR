---
title: Notas de versão do Campaign v8
description: Versão mais recente do Campaign v8
feature: Overview
role: Admin, Developer, User
level: Beginner, Intermediate, Experienced
exl-id: 7cf8111d-9f3a-46a4-813a-d4e43a1d1471
source-git-commit: dc2ccd7092fd31f043b338868762440ae0394991
workflow-type: tm+mt
source-wordcount: '1319'
ht-degree: 57%

---

# Versão mais recente{#latest-release}

O Adobe Campaign é atualizado regularmente. Essa frequência regular de atualizações tem como objetivo disponibilizar a você o que há de melhor e mais recente, mantendo seu ambiente seguro e melhorando sua experiência com nosso produto. A Adobe recomenda que todos os clientes atualizem para a versão mais recente.

Como usuário do Managed Cloud Services, sua instância é atualizada pela Adobe a cada nova versão. O Adobe entrará em contato com você e atualizará seus ambientes. Console do cliente do Campaign **deve ser atualizado para a mesma versão** como servidores do Campaign. Saiba como atualizar seu console do cliente nesta [página](../start/connect.md#upgrade-ac-console).

Além disso, como cliente, verifique se você está usando as versões mais recentes compatíveis dos sistemas listados na [Matriz de compatibilidade](compatibility-matrix.md).

## Versão 8.5.1 {#release-8-5}

_30 de junho de 2023_

**Novidades**

<table> 
<thead>
<tr> 
<th> <strong>Serviço aprimorado de notificação por push</strong><br /> </th> 
</tr> 
</thead> 
<tbody> 
<tr> 
<td><p>O Campaign v8.5.1 está apresentando nosso serviço de notificação por push mais recente, viabilizado por uma estrutura robusta criada em uma tecnologia de ponta moderna. Este serviço foi projetado para desbloquear novos níveis de escalabilidade, garantindo que suas notificações possam alcançar um público maior com eficiência contínua. Com nossa infraestrutura aprimorada e nossos processos otimizados, você pode esperar maior escala e confiabilidade, permitindo que você interaja e se conecte com seus usuários de aplicativos móveis como nunca. Esse recurso só está disponível para um grupo selecionado de clientes (disponibilidade limitada).</p>
<p>Para obter mais informações, consulte a <a href="../send/push-data-collection.md">documentação detalhada</a>.</p>

</td> 
</tr> 
</tbody> 
</table>

**Aprimoramentos**




* A taxa de transferência do SMS foi significativamente aprimorada com a implementação de uma variedade de otimizações, resultando em maior velocidade e eficiência para a comunicação por SMS.
* Agora você pode aproveitar a conexão de Destino do Adobe Experience Platform para sincronizar atributos de perfil, como dados de recusa entre o Adobe Experience Platform e o banco de dados do Campaign v8.
* A preparação da entrega foi otimizada.
* Uma nova opção de autenticação baseada em chave foi adicionada para a conta externa SFTP, juntamente com o método de autenticação de usuário/senha existente. Agora os usuários podem se autenticar com segurança usando uma chave privada, melhorando a segurança e fornecendo um mecanismo de autenticação alternativo para o acesso SFTP. Saiba mais [nesta seção](../config/external-accounts.md).

**Melhorias de segurança**

* A partir do Campaign v8.5.1, o processo de autenticação para o Campaign v8 foi aprimorado. Os operadores técnicos devem usar o Adobe Identity Management System (IMS) para se conectarem ao Campaign. Saiba como migrar as contas técnicas existentes no [esta nota técnica](../../technotes/upgrades/ims-migration.md).
* Não é possível mais criar operadores no Console do cliente do Campaign. A interface do usuário do foi atualizada adequadamente. Agora você deve usar o Adobe Admin Console. [Saiba mais](../start/gs-permissions.md).
* Várias ferramentas de terceiros foram atualizadas para otimizar a segurança.

**Atualizações de compatibilidade**

* A versão de 32 bits do console do cliente agora está obsoleta. A partir da versão 8.6, o Console do cliente só estará disponível em 64 bits. A atualização para a versão de 64 bits do console do cliente é perfeita. Para obter mais informações sobre como atualizar seu sistema operacional, consulte esta [nota técnica](../../technotes/upgrades/console.md).
* Agora você pode conectar a instância do Campaign v8 ao banco de dados externo do Azure synapse. Essa conexão é gerenciada por meio de uma nova conta externa. Saiba mais em [Matriz de compatibilidade do Campaign](../start/compatibility-matrix.md#federated-data-access-fdafederateddataaccessfda).



**Correções**

* Correção de um problema que poderia resultar na codificação incorreta de caracteres especiais no conteúdo HTML de um delivery em vários navegadores. (NEO-60081)
* Correção de um problema que impedia salvar um relatório em uma implantação corporativa (FFDA) do Campaign v8. (NEO-56836)
* Correção de um problema ao inserir ou atualizar dados em um esquema FFDA personalizado por meio de uma atividade de fluxo de trabalho Atualizar dados. (NEO-54708)
* Correção de um problema que impedia que o workflow de limpeza do banco de dados removesse endereços na tabela nms:address no FFDA. (NEO-54460)
* Correção de um problema com o fluxo de trabalho de faturamento que poderia falhar com um erro &quot;Compilação de memória esgotada&quot;. (NEO-51137)
* Correção de um problema que impedia que a descriptografia GPG funcionasse corretamente na atividade de workflow Carregamento de dados (arquivo). (NEO-50257)
* Corrigido um problema que impedia o funcionamento da função `JSPContext.sqlExecWithOneParam`. (NEO-50066)
* Correção de um problema que resultava em falhas de delivery ao usar caracteres não imprimíveis em campos de personalização. (NEO-48588)
* Correção de um problema que poderia causar erros de entrega ao inserir imagens dinâmicas do Adobe Target. (NEO-62689)
* Correção de um problema para impedir que os navegadores adicionassem espaços extras ao usar conteúdo condicional em uma entrega. (NEO-62132)
* Correção de um problema que fazia com que uma janela pop-up fosse aberta ao clicar em uma imagem no editor de conteúdo de email. (NEO-60752)
* Correção de um problema que poderia resultar em erro e impedir a rolagem ao editar o conteúdo de um delivery. (NEO-61364)
* O Adobe Analytics Connector agora exporta as métricas com o tipo de canal correto. Anteriormente, ele sempre era definido como canal de &quot;email&quot;. (NEO-26340)


## Versão 8.4.5 {#release-8-4-5}

_3 de abril de 2023_

**Correções**

* Correção de um problema que poderia resultar em um erro de restrição de chave duplicada se vários fluxos de trabalho de aprovação fossem definidos com a mesma programação. (NEO-48968)
* Correção de um problema de regressão introduzido pelo código NEO-54474 (8.4.4) que fazia com que o atributo de estilo da tag do corpo fosse alterado ao fazer upload de uma imagem no editor de conteúdo digital (DCE). (NEO-57697)
* Correção de um problema que poderia resultar em um erro ao exportar dados usando um conector CRM se a tabela temporária tivesse uma chave primária definida como “long” em vez de “uuid”. (NEO-54153)
* Correção de um problema de regressão introduzido na versão 8.4.1 que poderia causar erros na exportação de pacotes, no FDA sobre HTTP e nos relatórios. (NEO-57731)
* Correção de um problema de regressão introduzido na versão 8.3.8 que poderia impedir que o status da entrega fosse atualizado corretamente em entregas com IDs negativas. (NEO-54675)
* Correção de um problema com campos booleanos ao importar dados usando o conector Big Query (NEO-49181)


## Versão 8.4.4 {#release-8-4-4}

_8 de março de 2023_

**Aprimoramento de segurança**

* Para melhorar a segurança, o Tomcat foi atualizado da versão 8.5.81 para a 8.5.85. (NEO-50530)

**Correções**

* Correção de um problema que impedia a rolagem na guia **Editar** do editor de conteúdo digital (DCE). (NEO-54474)
* Correção de um problema durante a replicação que poderia resultar em uma falha do servidor da web. (NEO-53670)


## Versão 8.4.3 {#release-8-4-3}


_27 de janeiro de 2023_

**Aprimoramentos**

* Correção de um problema de sincronização de indicador de entrega entre o servidor de marketing e o servidor mid-sourcing. (NEO-50724) <!--OKKKK-->
* Correção de um problema que poderia causar um erro ao exportar um fluxo de trabalho. (NEO-50555) <!--OKKKK-->
* Correção de um problema ao estender um esquema que foi estendido anteriormente. (NEO-49118) <!--OKKKK-->
* Correção de um problema ao usar duas atividades de enriquecimento com o mesmo identificador na definição do link. (NEO-48851)
* Correção de dois problemas de falha de preparação de entrega. A preparação da entrega pode falhar quando o número de possíveis ofertas que estão sendo manipuladas é muito alto. O segundo problema ocorria quando os URLs de imagem eram definidos como URLs para serem rastreados em uma entrega de formato de texto. (NEO-48807) <!--OKKKK-->
* Correção de um problema que poderia resultar em uma falha de fluxo de trabalho, em que um fluxo de trabalho substituiria o nome do warehouse definido na conta externa para contas não FFDA. (NEO-43209) <!--OKKKK-->
* Segurança aprimorada em aplicativos da Web para evitar ataques de DDoS. (NEO-50757) <!--OKKKK-->
* O gerenciamento de dados de rastreamento consolidados foi aprimorado na Tabela FFDA (nms:trackingStats) do **[!UICONTROL Consolidated tracking]** para evitar duplicatas. (NEO-46409)
* Correção de um problema de operador lógico em consultas de fluxo de trabalho ao usar um `enableIf` em uma condição de operador lógico. A condição lógica anterior foi substituída. (NEO-45815)  <!--OKKKK-->
* A geração de perfis ativos foi otimizada no fluxo de trabalho de faturamento para melhorar o desempenho. (NEO-47658) <!--OKKKK-->
* Corrigido um problema com a importação de arquivos HTML no qual os nós de imagem (img) continham URLs com campos de personalização. (NEO-48396)
* Correção de um problema com o Snowflake (todas as implantações) ao usar o parâmetro de classificação em uma atividade de fluxo de trabalho de **Divisão**. (NEO-45899) <!--OKKKK-->
* Corrigido um problema que resultava em erro quando um usuário com direitos de acesso de leitura para a pasta nmsDeliveryMapping tentava executar uma campanha ou fluxo de trabalho. (NEO-48230)
* Corrigido um problema de desempenho na guia HTML de uma entrega que poderia ocorrer ao usar um código HTML grande. (NEO-47440)
<!-- * Fixed an issue which could lead to a "Character set mismatch" error when using certain functions such as `to_nclob` with an Oracle unicode database where NChar was not enabled. (NEO-49361)
* Fixed an issue which prevented users from inserting a Time datatype in a **Data Update** workflow activity on MSSQL. (NEO-47763)-->
* Correção de um problema que impedia a utilização da opção de fluxo de trabalho **Mesclar linhas selecionadas**. (NEO-48488)
* Correção de um problema no conector Snowflake FDA que fazia com que os registros fossem descartados ao usar a opção “Junção simples de cardinalidade 0 ou 1” durante o enriquecimento. (NEO-48737)
* As referências restantes à biblioteca log4j foram removidas da instalação do Campaign no Windows. (NEO-44851)
* Corrigido um problema que poderia resultar em erro ao adicionar o indicador **Destinatários que abriram** (estimatedRecipientOpen) nos dados adicionais de uma atividade de fluxo de trabalho de **Consulta**. (NEO-46665)
* O gerenciamento de URLs de rastreamento foi aprimorado em workflows com várias entregas para melhorar o desempenho. (NEO-50894) <!--OKKKK-->
* Correção de um problema que poderia causar falha na replicação de esquemas que usam a pasta Xtkfolder. (NEO-46787) <!--OKKKK-->
* Correção de uma causa de problema que poderia fazer com que a coluna personalizada “lastModified” fosse descartada na tabela NmsSubscription. (NEO-48402)


