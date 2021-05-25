---
solution: Campaign v8
product: Adobe Campaign
title: 'Introdução ao modelo de dados do Campaign '
description: 'Introdução ao modelo de dados do Campaign '
feature: Visão geral
role: Data Engineer
level: Beginner
exl-id: 200b60f1-04ae-4c3e-892f-3dd2bd22b896,b1319b34-ee07-48ed-9ab1-e2d12d3d99f8
source-git-commit: a50a6cc28d9312910668205e528888fae5d0b1aa
workflow-type: tm+mt
source-wordcount: '657'
ht-degree: 4%

---

# Introdução ao modelo de dados do Campaign {#gs-ac-datamodel}

O Adobe Campaign vem com um modelo de dados predefinido. Esta seção fornece alguns detalhes sobre as tabelas integradas do modelo de dados do Adobe Campaign e sua interação. O Adobe Campaign depende de um banco de dados do Cloud contendo tabelas vinculadas.

A estrutura básica do modelo de dados Adobe Campaign pode ser descrita da seguinte maneira:

* **Tabela** de recipients: O modelo de dados depende de uma tabela principal que é, por padrão, a tabela Recipient (nmsRecipient). Essa tabela permite armazenar todos os perfis de marketing.

   :bulb: Para obter mais informações sobre a tabela Recipient, consulte [esta seção](#ootb-profiles).

* **Tabela** de delivery: O modelo de dados também inclui uma parte dedicada ao armazenamento de todas as atividades de marketing. Geralmente é a tabela Delivery (NmsDelivery). Cada registro nesta tabela representa uma ação de delivery ou um template de delivery. Ele contém todos os parâmetros necessários para executar deliveries, como target, conteúdo, etc.

* **Registra tabelas**: Essas tabelas armazenam todos os logs associados à execução das campanhas.

   Todos os logs do delivery são mensagens enviadas a recipients ou dispositivos em todos os canais. A tabela principal Delivery logs (NmsBroadLogRcp) contém os logs de delivery para todos os recipients.
A tabela principal Tracking logs (NmsTrackingLogRcp) armazena os logs de rastreamento para todos os recipients. Os logs de rastreamento se referem a reações de recipients, como aberturas de email e cliques. Cada reação corresponde a um log de rastreamento.
Os logs de delivery e de rastreamento são excluídos após um determinado período, que é especificado no Adobe Campaign e pode ser modificado. Portanto, é altamente recomendável exportar os logs regularmente.

* **Tabelas** técnicas: Colete dados técnicos usados para o processo do aplicativo, incluindo operadores e direitos do usuário (xtkGroup), pastas (XtkFolder).

>[!NOTE]
>
>Para acessar a descrição de cada tabela, vá para Admin > Configuração > Esquemas de dados, selecione um recurso da lista e clique na guia **Documentation**.

Ao começar com o Adobe Campaign, é necessário avaliar o modelo de dados padrão para verificar qual tabela é a mais adequada para armazenar seus dados de marketing.

Você pode usar a tabela Recipient padrão com os campos prontos para uso, como descrito em [this section](#ootb-profiles). Se necessário, você pode estendê-lo com dois mecanismos:

* [Estenda uma ](extend-schema.md) tabela existente com novos campos. Por exemplo, você pode adicionar um novo campo &quot;Fidelidade&quot; à tabela Recipient .
* [Crie uma nova tabela](create-schema.md), por exemplo, uma tabela &quot;Purchase&quot; que lista todas as compras feitas por cada perfil do banco de dados e a vincula à tabela Recipient .

:bulb: Descubra as práticas recomendadas ao trabalhar com o datamodel do Campaign em [esta seção](datamodel-best-practices.md).

## Tabela de perfil integrada {#ootb-profiles}

A tabela de recipient integrada (nmsrecipient) no Adobe Campaign fornece um bom ponto de partida para criar seu modelo de dados. Ela tem vários campos predefinidos e links de tabela que podem ser facilmente estendidos. Isso é particularmente útil quando você está direcionando recipients principalmente porque se encaixa em um modelo de dados simples centrado em recipients.

Os benefícios de usar a tabela de recipients padrão são:

* Trabalhar pronto para uso com funcionalidades-chave como assinaturas, listas de propagação e muito mais
* Fornecimento de um banco de dados de marketing com um modelo de dados centrado no recipient
* Implementação mais rápida
* Manutenção fácil por suporte e parceiros

É possível estender a tabela de recipients, mas não para reduzir o número de campos ou links na tabela.

:bulb: Saiba como estender um schema existente em [esta seção](extend-schema.md).

:seta_upper_right: Descubra exemplos de extensões de tabela de recipient incorporadas na [documentação do Campaign Classic v7](https://experienceleague.adobe.com/docs/campaign-classic/using/configuring-campaign-classic/editing-schemas/examples-of-schemas-edition.html?lang=en#extending-a-table)

Você também pode usar uma tabela de recipients diferente para se adequar melhor às suas necessidades comerciais ou funcionais. Este método vem com limitações e é descrito em [this section](custom-recipient.md).

## Tabelas do Campaign e banco de dados do Cloud

Para entender melhor o gerenciamento de tabela no Campaign v8, observe que as tabelas são replicadas entre o Campaign e seu banco de dados do Snowflake Cloud.

:bulb: Saiba mais sobre estratégia e mecanismos de replicação em [esta seção](../config/replication.md).

**Tópicos relacionados**

:bulb: Descubra como importar perfis em [esta seção](../start/import.md)
:bulb: Saiba mais sobre públicos-alvo do Campaign em [esta seção](../start/audiences.md)
