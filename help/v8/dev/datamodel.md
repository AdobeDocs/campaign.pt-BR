---
title: 'Introdução ao modelo de dados do Campaign '
description: 'Introdução ao modelo de dados do Campaign '
feature: Overview
role: Data Engineer
level: Beginner
exl-id: 200b60f1-04ae-4c3e-892f-3dd2bd22b896
source-git-commit: 6de5c93453ffa7761cf185dcbb9f1210abd26a0c
workflow-type: tm+mt
source-wordcount: '655'
ht-degree: 4%

---

# Introdução ao modelo de dados do Campaign {#gs-ac-datamodel}

O Adobe Campaign vem com um modelo de dados predefinido. Esta seção fornece alguns detalhes sobre as tabelas integradas do modelo de dados do Adobe Campaign e sua interação. O Adobe Campaign depende de um banco de dados do Cloud contendo tabelas vinculadas.

A estrutura básica do modelo de dados Adobe Campaign pode ser descrita da seguinte maneira:

* **Tabela de recipients**: O modelo de dados depende de uma tabela principal que é, por padrão, a tabela Recipient (nmsRecipient). Essa tabela armazena todos os perfis de marketing.

   ![](../assets/do-not-localize/glass.png) Para obter mais informações sobre a tabela Recipient, consulte [esta seção](#ootb-profiles).

* **Tabela de delivery**: O modelo de dados também inclui uma parte dedicada ao armazenamento de todas as atividades de marketing. Geralmente é a tabela Delivery (NmsDelivery). Cada registro nesta tabela representa uma ação de delivery ou um template de delivery. Ele contém todos os parâmetros necessários para executar deliveries, como target, conteúdo, etc.

* **Tabelas de logs**: Essas tabelas armazenam todos os logs associados à execução das campanhas.

   Todos os logs do delivery são mensagens enviadas a recipients ou dispositivos em todos os canais. A tabela principal Delivery logs (NmsBroadLogRcp) contém os logs de delivery para todos os recipients.
A tabela principal Tracking logs (NmsTrackingLogRcp) armazena os logs de rastreamento para todos os recipients. Os logs de rastreamento se referem a reações de recipients, como aberturas de email e cliques. Cada reação corresponde a um log de rastreamento.
Os logs de delivery e de rastreamento são excluídos após um determinado período, que é especificado no Adobe Campaign e pode ser modificado. Portanto, é altamente recomendável exportar os logs regularmente.

* **Tabelas técnicas**: Colete dados técnicos usados para o processo do aplicativo, incluindo operadores e direitos do usuário (xtkGroup), pastas (XtkFolder).

>[!NOTE]
>
>Para acessar a descrição de cada tabela, vá para Admin > Configuração > Esquemas de dados, selecione um recurso na lista e clique no link **Documentação** guia .

Ao começar com o Adobe Campaign, é necessário avaliar o modelo de dados padrão para verificar qual tabela é a mais adequada para armazenar seus dados de marketing.

Você pode usar a tabela Recipient padrão com os campos prontos para uso, como descrito em [esta seção](#ootb-profiles). Se necessário, você pode estendê-lo com dois mecanismos:

* [Estender uma tabela existente](extend-schema.md) com novos campos. Por exemplo, você pode adicionar um novo campo &quot;Fidelidade&quot; à tabela Recipient .
* [Criar uma nova tabela](create-schema.md), por exemplo, uma tabela &quot;Purchase&quot; que lista todas as compras feitas por cada perfil do banco de dados e a vincula à tabela Recipient.

![](../assets/do-not-localize/glass.png) Descubra as práticas recomendadas ao trabalhar com o modelo de dados do Campaign em [esta seção](datamodel-best-practices.md).

## Tabela de perfil integrada {#ootb-profiles}

A tabela de recipient integrada (nmsrecipient) no Adobe Campaign fornece um bom ponto de partida para criar seu modelo de dados. Ela tem vários campos predefinidos e links de tabela que podem ser facilmente estendidos. Isso é particularmente útil quando você está direcionando recipients principalmente porque se encaixa em um modelo de dados simples centrado em recipients.

Os benefícios de usar a tabela de recipients padrão são:

* Trabalhar pronto para uso com funcionalidades-chave como assinaturas, listas de propagação e muito mais
* Fornecimento de um banco de dados de marketing com um modelo de dados centrado no recipient
* Implementação mais rápida
* Manutenção fácil por suporte e parceiros

É possível estender a tabela de recipients, mas não para reduzir o número de campos ou links na tabela.

![](../assets/do-not-localize/glass.png) Saiba como estender um esquema existente no [esta seção](extend-schema.md).

![](../assets/do-not-localize/book.png) Descubra exemplos de extensões internas da tabela de destinatários em [Documentação do Campaign Classic v7](https://experienceleague.adobe.com/docs/campaign-classic/using/configuring-campaign-classic/editing-schemas/examples-of-schemas-edition.html?lang=en#extending-a-table){target=&quot;_blank&quot;}

Você também pode usar uma tabela de recipients diferente para se adequar melhor às suas necessidades comerciais ou funcionais. Este método vem com limitações e é descrito em [esta seção](custom-recipient.md).

## Tabelas do Campaign e banco de dados do Cloud

Para entender melhor o gerenciamento de tabela no Campaign v8, observe que, no contexto de um [Implantação empresarial (FDA)](../architecture/enterprise-deployment.md), as tabelas são replicadas entre o Campaign e seu banco de dados do Snowflake Cloud.

![](../assets/do-not-localize/glass.png) Saiba mais sobre a estratégia e os mecanismos de replicação no [esta seção](../architecture/replication.md).

**Tópicos relacionados**

![](../assets/do-not-localize/glass.png) Saiba como importar perfis no [esta seção](../start/import.md)
![](../assets/do-not-localize/glass.png) Saiba mais sobre públicos-alvo do Campaign em [esta seção](../start/audiences.md)
