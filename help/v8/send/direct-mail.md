---
title: Enviar malas diretas com o Adobe Campaign
description: Introdução à correspondência direta no Campaign
feature: Direct Mail
role: User
level: Beginner
exl-id: ff2be012-72f3-428d-a973-196fea7ec4ab
source-git-commit: 061197048885a30249bd18af7f8b24cb71def742
workflow-type: tm+mt
source-wordcount: '387'
ht-degree: 43%

---

# Criar entregas de correspondência direta

Os deliveries de correspondência direta permitem gerar um arquivo de extração que contém dados sobre a população do target. Você pode compartilhar esse arquivo com o provedor que fornecerá mensagens para as populações do target.

As etapas para gerar o arquivo são:

1. Criar a entrega

   Crie um delivery de correspondência direta com base no template. É possível duplicar e configurar o **[!UICONTROL Deliver by direct mail (paper)]** modelo incorporado.

   Saiba mais na [documentação do Campaign Classic v7](https://experienceleague.adobe.com/docs/campaign-classic/using/sending-messages/sending-direct-mail/creating-a-direct-mail-delivery.html){target="_blank"}

1. Definir o público-alvo

   Os perfis de destinatários devem conter pelo menos seus nomes e endereços postais.

   Os endereços postais são campos calculados. Um endereço pode conter até seis linhas por padrão: a primeira contém o nome e o sobrenome, as próximas linhas contêm o endereço postal (rua etc.), e a última linha contém o CEP/código postal e a cidade. A definição do campo postalAddress calculado padrão pode ser revisada no esquema nms:recipient.

   Um endereço será considerado completo se o nome, o CEP/código postal e a cidade não estiverem em branco. Quaisquer destinatários com endereços incompletos serão excluídos das entregas de correspondência direta.

   Saiba mais na [documentação do Campaign Classic v7](https://experienceleague.adobe.com/docs/campaign-classic/using/sending-messages/key-steps-when-creating-a-delivery/steps-defining-the-target-population.html){target="_blank"}

1. Definir o conteúdo do arquivo

   Use o assistente de extração para definir as informações (colunas) a serem exportadas para o arquivo de saída.

   Saiba mais na [documentação do Campaign Classic v7](https://experienceleague.adobe.com/docs/campaign-classic/using/sending-messages/sending-direct-mail/defining-the-direct-mail-content.html){target="_blank"}

1. Validar a entrega

   Verifique o resultado da análise e o conteúdo do arquivo de output.

   Saiba mais na [documentação do Campaign Classic v7](https://experienceleague.adobe.com/docs/campaign-classic/using/sending-messages/sending-direct-mail/validating.html){target="_blank"}

   No contexto de uma campanha de marketing, na data de extração, o arquivo de extração é criado. Você pode visualizar o conteúdo do arquivo extraído, aprová-lo ou alterar o formato e reiniciar a extração, se necessário. Depois que o arquivo for aprovado, você poderá enviar o e-mail de notificação para o roteador. Saiba mais [nesta página](https://experienceleague.adobe.com/docs/campaign/automation/campaign-orchestration/marketing-campaign-approval.html?lang=pt-BR)

1. Iniciar a entrega

   Depois de validar o arquivo de extração, clique em **Confirmar delivery** uma mensagem de confirmação permite iniciar o delivery.

   A confirmação inicia a extração de dados no arquivo especificado.

   No contexto de uma campanha de marketing, quando todas as aprovações foram concedidas, os arquivos de extração são criados por um workflow especial que, em uma configuração padrão, começa automaticamente quando um delivery de correspondência direta está com extração pendente. Saiba mais em [nesta seção](https://experienceleague.adobe.com/docs/campaign/automation/campaign-orchestration/marketing-campaign-deliveries.html?lang=pt-BR)
