---
title: Introdução ao modelo de dados do Campaign
description: Comece a usar o modelo de dados do Campaign e aproveite os dados de suas fontes para beneficiar as comunicações e saídas de marketing.
feature: Data Model
role: Data Engineer
level: Beginner
exl-id: 200b60f1-04ae-4c3e-892f-3dd2bd22b896
source-git-commit: 65f4da979f0c5884797af0c3a835d948672b4a7c
workflow-type: tm+mt
source-wordcount: '665'
ht-degree: 6%

---

# Introdução ao modelo de dados do Campaign {#gs-ac-datamodel}

O Adobe Campaign vem com um modelo de dados predefinido. Esta seção fornece alguns detalhes sobre as tabelas integradas do modelo de dados do Adobe Campaign e suas interações. O Adobe Campaign depende de um banco de dados na nuvem que contém tabelas vinculadas.

A estrutura básica do modelo de dados do Adobe Campaign pode ser descrita da seguinte maneira:

* **Tabela de destinatários**: o modelo de dados depende de uma tabela principal que é, por padrão, a tabela Recipient (nmsRecipient). Esta tabela armazena todos os perfis de marketing.

   ![](../assets/do-not-localize/glass.png) Para obter mais informações sobre a tabela Recipient, consulte [nesta seção](#ootb-profiles).

* **Tabela de entrega**: o modelo de dados também inclui uma parte dedicada ao armazenamento de todas as atividades de marketing. Normalmente, é a tabela Delivery (NmsDelivery). Cada registro nessa tabela representa uma ação de entrega ou um modelo de entrega. Ele contém todos os parâmetros necessários para executar deliveries, como target, conteúdo etc.

* **Registra tabelas**: essas tabelas armazenam todos os logs associados à execução das campanhas.

   Os logs do delivery são todas as mensagens enviadas aos recipients ou dispositivos em todos os canais. A tabela principal Delivery logs (NmsBroadLogRcp) contém os logs do delivery para todos os recipients.
A tabela principal de Logs de rastreamento (NmsTrackingLogRcp) armazena os logs de rastreamento para todos os destinatários. Os logs de rastreamento se referem às reações dos recipients, como aberturas e cliques de email. Cada reação corresponde a um log de rastreamento.
Os logs do delivery e os logs de rastreamento são excluídos após um determinado período, que é especificado no Adobe Campaign e pode ser modificado. Portanto, é altamente recomendável exportar os logs regularmente.

* **Tabelas técnicas**: colete dados técnicos usados para o processo do aplicativo, incluindo operadores e direitos de usuário (xtkGroup), pastas (XtkFolder).

>[!NOTE]
>
>Para acessar a descrição de cada tabela, vá para Admin > Configuração > Esquemas de dados, selecione um recurso na lista e clique no link **Documentação** guia.

Ao começar com o Adobe Campaign, é necessário avaliar o modelo de dados padrão para verificar qual tabela é a mais adequada para armazenar seus dados de marketing.

Você pode usar a tabela Recipient padrão com os campos prontos para uso, como descrito em [nesta seção](#ootb-profiles). Se necessário, você pode estendê-lo com dois mecanismos:

* [Estender uma tabela existente](extend-schema.md) com novos campos. Por exemplo, é possível adicionar um novo campo &quot;Fidelidade&quot; à tabela Recipient.
* [Criar uma nova tabela](create-schema.md), por exemplo, uma tabela &quot;Purchase&quot; listando todas as compras feitas por cada perfil do banco de dados e vinculá-la à tabela Recipient.

![](../assets/do-not-localize/glass.png) Descubra as práticas recomendadas ao trabalhar com o modelo de dados do Campaign no [nesta seção](datamodel-best-practices.md).

## Tabela de perfil interna {#ootb-profiles}

A tabela de recipients integrada (nmsrecipient) no Adobe Campaign fornece um bom ponto de partida para criar seu modelo de dados. Ele tem vários campos predefinidos e links de tabela que podem ser facilmente estendidos. Isso é particularmente útil quando você está direcionando principalmente recipients, pois se encaixa em um modelo de dados simples centrado no recipient.

Os benefícios de usar a tabela de recipients padrão são:

* Trabalhar pronto para uso com funcionalidades importantes, como assinaturas, listas de propagação e muito mais
* Fornecer um banco de dados de marketing com um modelo de dados centrado no recipient
* Implementação mais rápida
* Fácil manutenção pelo suporte e pelos parceiros

É possível estender a tabela do recipient, mas não reduzir o número de campos ou links na tabela.

![](../assets/do-not-localize/glass.png) Saiba como estender um esquema existente no [nesta seção](extend-schema.md).

![](../assets/do-not-localize/book.png) Descubra exemplos de extensões de tabela de recipients integradas no [Documentação do Campaign Classic v7](https://experienceleague.adobe.com/docs/campaign-classic/using/configuring-campaign-classic/editing-schemas/examples-of-schemas-edition.html#extending-a-table){target="_blank"}

Você também pode usar uma tabela de recipients diferente para se adequar melhor aos requisitos comerciais ou funcionais. Este método vem com limitações e está descrito em [nesta seção](custom-recipient.md).

## Tabelas do Campaign e banco de dados na nuvem

Para obter uma melhor compreensão do gerenciamento de tabelas no Campaign v8, observe que, no contexto de uma [Implantação corporativa (FFDA)](../architecture/enterprise-deployment.md), as tabelas são replicadas entre o Campaign e seu banco de dados do Snowflake Cloud.

![](../assets/do-not-localize/glass.png) Saiba mais sobre a estratégia e os mecanismos de replicação em [nesta seção](../architecture/replication.md).

**Tópicos relacionados**

![](../assets/do-not-localize/glass.png) Saiba como importar perfis no [nesta seção](../start/import.md)
![](../assets/do-not-localize/glass.png) Saiba mais sobre os públicos do Campaign em [nesta seção](../start/audiences.md)
