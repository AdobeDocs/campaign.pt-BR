---
solution: Campaign
product: Adobe Campaign
title: Alterar a tabela de destinatários padrão
description: Saiba como usar uma tabela de recipient personalizada
feature: Visão geral
role: Data Engineer
level: Beginner
exl-id: 0b71c76b-03d9-4023-84fc-3ecc0df9261b
translation-type: tm+mt
source-git-commit: 84ee7eb2bf2e15d30c81f32f6b25c9801b3b12b1
workflow-type: tm+mt
source-wordcount: '253'
ht-degree: 2%

---

# Usar tabela de recipient personalizada{#gs-ac-custom-recipient}

O Adobe Campaign vem com uma tabela de perfil integrada: **nmsRecipient**. Essa tabela tem vários campos e tabelas predefinidos que podem ser facilmente estendidos. Saiba mais sobre esta tabela em [this page](datamodel.md#ootb-profiles).

A extensão de tabela integrada oferece flexibilidade, mas não permite remover alguns campos ou links não utilizados. Como consequência, usar uma tabela de recipient personalizada pode ser uma boa opção quando o modelo de dados for diferente drasticamente da estrutura da tabela de recipients integrada do Campaign ou se você tiver um grande número de perfis.  No entanto, este método exige determinadas precauções ao implementá-lo.

Essa funcionalidade permite que o Adobe Campaign processe dados de um banco de dados externo: esses dados serão usados como um conjunto de perfis para deliveries. A implementação desse processo envolve limitações, como:

* Nenhum fluxo de atualização de e para o banco de dados da Campaign Cloud: os dados desta tabela podem ser atualizados diretamente pelo mecanismo de banco de dados que os hospeda.
* Os processos que operam no banco de dados existente precisam ser estáveis.
* Uso de um banco de dados de perfil com uma estrutura não padrão: possibilidade de delivery em perfis salvos em várias tabelas com várias estruturas, usando uma única instância.

Esta seção descreve os pontos principais para mapear tabelas existentes no Adobe Campaign e as configurações a serem aplicadas para executar deliveries com base em qualquer tabela. Ele também descreve como projetar interfaces de consulta para usuários finais.

>[!CAUTION]
>
>A personalização do Adobe Campaign é reservada somente para usuários especialistas. Ela requer experiência em formulários de entrada e design de esquema.

