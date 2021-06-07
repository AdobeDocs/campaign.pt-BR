---
product: Adobe Campaign
title: Enviar malas diretas com o Adobe Campaign
description: Introdução à correspondência direta no Campaign
feature: Visão geral
role: Data Engineer
level: Beginner
source-git-commit: 67657fa19f3ff4594f7901f30d0d49ac75dcfbe0
workflow-type: tm+mt
source-wordcount: '408'
ht-degree: 24%

---

# Criar deliveries de correspondência direta

Os deliveries de correspondência direta permitem gerar um arquivo de extração que contém dados sobre a população do target. Em seguida, você pode compartilhar esse arquivo com o provedor que enviará mensagens para as populações do target.

As etapas para gerar o arquivo são:

1. Criar o delivery

   Crie um delivery de mala direta com base no template . Você pode duplicar e configurar o template incorporado **[!UICONTROL Deliver by direct mail (paper)]**.

   [!DNL :arrow_upper_right:] Saiba mais na documentação do  [Campaign Classic v7](https://experienceleague.adobe.com/docs/campaign-classic/using/sending-messages/sending-direct-mail/creating-a-direct-mail-delivery.html)

1. Definir o público

   Os perfis de recipients devem conter pelo menos seus nomes e endereços postais.

   Os endereços postais são campos calculados. Um endereço pode conter até seis linhas por padrão: a primeira contém o nome e sobrenome, as próximas linhas contêm o endereço postal (rua, etc), e a última linha contém o CEP e a cidade.

   Um endereço é considerado completo se o nome, campo de CEP e campos do município/cidade não estiverem vazios.

   [!DNL :arrow_upper_right:] Saiba mais na documentação do  [Campaign Classic v7](https://experienceleague.adobe.com/docs/campaign-classic/using/sending-messages/key-steps-when-creating-a-delivery/steps-defining-the-target-population.html)

1. Definir o conteúdo do arquivo

   Use o assistente de extração para definir as informações (colunas) a serem exportadas para o arquivo de saída.

   [!DNL :arrow_upper_right:] Saiba mais na documentação do  [Campaign Classic v7](https://experienceleague.adobe.com/docs/campaign-classic/using/sending-messages/sending-direct-mail/defining-the-direct-mail-content.html)

1. Validar a entrega

   Verifique o resultado da análise e o conteúdo do arquivo de saída.

   [!DNL :arrow_upper_right:] Saiba mais na documentação do  [Campaign Classic v7](https://experienceleague.adobe.com/docs/campaign-classic/using/sending-messages/sending-direct-mail/validating.html)

   No contexto de uma campanha de marketing, na data da extração, o arquivo de extração é criado. Você pode exibir o conteúdo do arquivo extraído, aprová-lo ou alterar o formato e reiniciar a extração, se necessário. Depois que o arquivo for aprovado, você poderá enviar o e-mail de notificação para o roteador.

   [!DNL :arrow_upper_right:] Saiba mais na documentação do  [Campaign Classic v7](https://experienceleague.adobe.com/docs/campaign-classic/using/orchestrating-campaigns/orchestrate-campaigns/marketing-campaign-approval.html#approving-an-extraction-file)

1. Iniciar o delivery

   Depois de validar o arquivo de extração, clique em **Confirm delivery** uma mensagem de confirmação permite iniciar o delivery.

   A confirmação inicia a extração de dados no arquivo especificado.

   No contexto de uma campanha de marketing, quando todas as aprovações tiverem sido concedidas, os arquivos de extração serão criados por meio de um workflow especial, que, em uma configuração padrão, será iniciado automaticamente quando um delivery de correspondência direta estiver com extração pendente.

   [!DNL :arrow_upper_right:] Saiba mais na documentação do  [Campaign Classic v7](https://experienceleague.adobe.com/docs/campaign-classic/using/orchestrating-campaigns/orchestrate-campaigns/marketing-campaign-deliveries.html#starting-an-offline-delivery)