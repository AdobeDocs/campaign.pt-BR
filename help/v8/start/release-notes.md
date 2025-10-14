---
title: Notas de versão do Campaign v8
description: Versão mais recente do Campaign v8
feature: Release Notes
exl-id: 7cf8111d-9f3a-46a4-813a-d4e43a1d1471
source-git-commit: d31368428fc7d5b982bb5fc67d0369bb17ea0b2c
workflow-type: tm+mt
source-wordcount: '388'
ht-degree: 23%

---

# Versões mais recentes {#latest-release}

Esta página lista novos recursos, melhorias e correções das **últimas versões** do Campaign v8 (console). Saiba mais sobre lançamentos, versões e atualizações do Campaign [nesta página](upgrades.md). Outras versões estão listadas na seção Versões anteriores desta documentação.

## Versão 8.8.2 {#release-8-8-2}

_9 de outubro de 2025_

>[!AVAILABILITY]
>
>Esta versão está em **disponibilidade limitada** (LA). 

### Novos recursos {#features-8-8-2}

O **novo conector de envio de SMS** agora está disponível para [implantações do FFDA do Campaign](../architecture/enterprise-deployment.md). Consulte a [documentação detalhada](../send/sms/sms.md).

Esta versão também vem com um conjunto de funcionalidades disponíveis com a interface da Web do Campaign:

* [Enriquecimento de Perfil em Mensagens Transacionais](https://experienceleague.adobe.com/docs/campaign-web/v8/msg/transactional-messages/profile-enrichment.html){target="_blank"}
* [Recursos Multilíngues para Mensagens Transacionais, Notificações por Push e SMS](https://experienceleague.adobe.com/docs/campaign-web/v8/msg/multilingual.html){target="_blank"}

Consulte as [notas de versão](https://experienceleague.adobe.com/docs/campaign-web/v8/release-notes/release-notes.html?lang=pt-BR){target="_blank"} da interface da Web do Campaign

### Correções {#fixes-8-8-2}

<!--
* Fixed an issue which prevented dynamic reporting from being available for transactional messages.
-->
* Correção de um problema que poderia resultar na falha do fluxo de trabalho de limpeza do banco de dados. (NEO-87949)
* Correção de um problema no Marketing distribuído em que os dados de rastreamento não eram registrados para deliveries de campanha colaborativa. (NEO-86836)
<!--
* Issue SMS2.0 with FFDA Continuous Deliveries (NEO-88785)
-->
* Correção de um problema que impedia o funcionamento correto da personalização em fragmentos. (NEO-88161)
* Correção de um problema após a migração para o novo conector ODBC do Redshift, que poderia resultar na falha da atividade de fluxo de trabalho Split com erros SQL. (NEO-87466)
* Correção de um problema que poderia causar contagens de exclusão imprecisas em workflows. (NEO-89207)
* Correção de um problema que poderia causar indicadores de clique imprecisos para notificações por push. (NEO-89503)
* Correção de um problema em que os logs do delivery do SMS não eram atualizados corretamente, impedindo a geração de relatórios de status precisos no Adobe Campaign. (NEO-88479)
* Correção de um problema em que as aspas francesas eram convertidas incorretamente em aspas inglesas no conteúdo de delivery. (NEO-89631)
* Correção de um problema em que o Servidor em tempo real retornava um código de resposta incorreto para tokens IMS inválidos. (NEO-87428)
* Correção de um problema em que as estatísticas de delivery de email e SMS não eram totalmente recalculadas, causando indicadores de sucesso imprecisos. (NEO-88106)
* Correção de um problema com o novo conector de envio de SMS em que os logs de entrega atribuíam incorretamente o status de entrega a um pequeno subconjunto de mensagens. (NEO-89581)
* Correção de um problema com o novo conector de envio de SMS em que os deliveries de métricas de sucesso não eram atualizados corretamente em servidores de marketing e mid. (NEO-89850)
* Correção de um problema de sincronização entre as instâncias de Tempo real e Marketing que causava a ausência de logs de rastreamento e relatórios incorretos. (NEO-90247)
* Correção de um problema de enriquecimento do fluxo de trabalho que causava erros ao selecionar campos em dois links 1-N consecutivos em esquemas personalizados. (NEO-87682)

