---
title: Migração para o novo conector SMS v2
description: Saiba como migrar para o novo conector SMS v2
feature: Technote
role: Admin
exl-id: 61a5a3e8-59f8-47ea-afc9-66ec243b8265
product_v2:
  - id: dfc56824-e8b9-499e-85d4-21aedb507314
    internal-label: Campaign
  - id: d0e9f0b2-1f2b-4134-9844-49cd4e950f27
    internal-label: Campaign v8
feature_v2:
  - id: ab81f6c3-9317-564f-af92-6670a8784294
    internal-label: Technote
role_v2:
  - id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
    internal-label: Admin
source-git-commit: 7fd43a8d3d6afe9f4d3fb000d925cc6185ba9f40
workflow-type: tm+mt
source-wordcount: '225'
ht-degree: 0%
---
# Migração para o novo conector SMS v2

O Adobe Campaign v8 apresenta um novo **conector de processo de SMS dedicado** (v2), que oferece desempenho e confiabilidade aprimorados em comparação ao conector de SMS baseado em MTA herdado.

## Por que alternar para o conector v2

O processo SMS dedicado apresenta suporte para o modo transceptor SMPP, reduzindo a contagem de conexões e melhorando a eficiência dos recursos, enquanto ainda oferece suporte às configurações de transmissor/receptor, se necessário. Ele oferece estabilidade significativamente maior, com recuperação mais rápida de erros, conexões persistentes e sem dependência de arquivos locais ou comunicação entre processos. O desempenho também é aprimorado, com latência mais baixa, throughput mais alta e microlotes inteligentes para equilibrar a velocidade e a confiabilidade. Além disso, o isolamento do processo de SMS simplifica a solução de problemas e minimiza o impacto entre canais. Esses aprimoramentos tornam o conector dedicado uma solução mais robusta e escalável para entrega de SMS.

## Configuração

Com o Adobe Campaign Managed Cloud Services, a configuração do servidor e a migração do conector SMS são gerenciadas pelo Adobe. Este procedimento técnico requer acesso direto aos arquivos de configuração do servidor e às operações do banco de dados.

Se precisar migrar para o novo conector SMS v2, entre em contato com o representante da Adobe ou com o Atendimento ao cliente da Adobe. Eles agendarão e executarão as atualizações necessárias para sua instância.

Para obter mais informações sobre o canal de SMS no Campaign v8, consulte a [documentação de SMS](../../v8/send/sms/sms.md).
