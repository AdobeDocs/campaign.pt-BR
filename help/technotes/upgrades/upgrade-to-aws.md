---
title: Atualização da infraestrutura de envio de email do Campaign
description: Atualização da infraestrutura de envio de email do Campaign
exl-id: f01e38ad-490e-4389-af5e-87beef533eb0
source-git-commit: 4f9183c7f1d12feb255a0050da423647f0fce85e
workflow-type: tm+mt
source-wordcount: '331'
ht-degree: 5%

---

# Atualização da infraestrutura de envio de email do Campaign {#migrate-infra-to-aws}

## O que será atualizado?{#aws-changes}

Como parte de nosso esforço contínuo para fornecer a melhor experiência de usuário do setor, estamos atualizando nosso serviço de delivery de email.

## Você será afetado?{#aws-impact}

Essa alteração afeta:

* Clientes do Adobe Campaign Classic Managed Services
* Clientes do Adobe Campaign Managed Cloud Services
* Clientes do Adobe Campaign Standard On-demand

## Quando essa atualização ocorrerá?{#aws-timeline}

As atualizações dos ambientes de preparo e desenvolvimento iniciaram em **outubro de 2023**.

As atualizações de ambientes de produção começaram em **janeiro de 2024**.

## O que esperar?{#impact}

* A duração de cada onda de atualização varia de acordo com o número de instâncias do Campaign afetadas. Quando uma onda de atualização de produção for agendada, a notificação incluirá a duração estimada.

* As instâncias do Campaign, em ambientes de preparo e produção, não poderão enviar emails durante a janela de atualização. Não é esperado que outra funcionalidade do Campaign seja afetada.

## Perguntas frequentes {#aws-faq}

* **Esta atualização é obrigatória?**

  Sim. Como cliente do Campaign, sua funcionalidade de envio de email requer o uso de uma infraestrutura de envio de email.

* **Quais clientes são direcionados para esta atualização?**

  Todos os clientes do Campaign mencionados acima terão seus ambientes atualizados.

* **Qual é o tempo de inatividade esperado?**

  A duração de cada onda de atualização pode variar dependendo do número de instâncias do Campaign afetadas. Quando uma onda de atualização de produção for agendada, a notificação incluirá uma duração estimada.

* **O cliente precisa realizar alguma ação para a atualização?**

  Nenhuma ação é necessária. O Adobe gerenciará o processo de atualização, que será executado automaticamente.

* **Quais testes são exigidos pelos clientes?**

  Não esperamos nenhum teste por parte dos clientes em conexão com esse evento de atualização. Caso algum problema seja observado, entre em contato com o [Atendimento ao cliente da Adobe](https://experienceleague.adobe.com/?support-solution=Campaign#support){target="_blank"}.


* **É possível solicitar uma alteração em Data/Hora no slot de atualização de segurança agendado?**

  Não. Não é possível acomodar as modificações solicitadas à programação existente, pois isso provavelmente interromperá o evento de atualização atribuído para outro cliente.

Para qualquer outra pergunta, entre em contato com o [Atendimento ao cliente da Adobe](https://experienceleague.adobe.com/?support-solution=Campaign#support){target="_blank"}.
