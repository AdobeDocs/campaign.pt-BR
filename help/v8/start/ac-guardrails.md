---
title: Medidas de proteção do Campaign v8
description: Medidas de proteção do Campaign v8
feature: Overview
role: Data Engineer
level: Beginner
exl-id: 50c254ba-cc33-49b2-b7d5-12aa69883c07
source-git-commit: cda523168525c24ec1c976850bc336f273276ac9
workflow-type: tm+mt
source-wordcount: '257'
ht-degree: 42%

---

# Medidas de proteção do produto{#guardrails}

Os direitos, as limitações de produtos e as medidas de proteção do desempenho estão listados em [Página de descrição do produto Adobe Campaign Managed Cloud Services](https://helpx.adobe.com/br/legal/product-descriptions/adobe-campaign-managed-cloud-services.html){target=&quot;_blank&quot;}.

Você encontrará abaixo medidas de proteção e limitações adicionais ao usar [!DNL Adobe Campaign].

As garantias e limitações identificam recursos, arquitetura ou processos que não são compatíveis com essa versão do produto ou que não interoperam corretamente com ele. Revise essas limitações cuidadosamente.

* O Adobe Campaign v8 não está disponível para implantações locais/híbridas, apenas as lançadas como um serviço na nuvem gerenciado pela Adobe
* Os clientes existentes não podem migrar de um ambiente do Adobe Campaign existente para o Adobe Campaign v8
* No contexto de um [Implantação empresarial (FDA)](../architecture/enterprise-deployment.md), nenhuma replicação bidirecional de dados é fornecida: a replicação acontece somente a partir do banco de dados local do Campaign para o banco de dados do Cloud
* Os recursos listados [nesta seção](v7-to-v8.md#gs-unavailable-features) não estão disponíveis na build atual do Campaign v8
* Alguns recursos não disponíveis ou removidos ainda estão visíveis na interface do usuário
* No contexto de um [Implantação empresarial (FDA)](../architecture/enterprise-deployment.md), os mecanismos de assinatura (aceitação) e cancelamento de assinatura (recusa) e o registro em dispositivos móveis são processos assíncronos . As solicitações são processadas a cada hora por meio de um fluxo de trabalho técnico específico. [Saiba mais](../architecture/replication.md#tech-wf)
* As duplicatas precisam ser manipuladas manualmente pelos usuários finais. [Saiba mais](../architecture/keys.md)
* O Adobe Campaign v8 não suporta throughput estendida em aplicativos da API e da Web - no caso de necessidades específicas, entre em contato com o Adobe para obter orientação
* O módulo de Otimização de Campanha do Adobe Campaign não considera os deliveries agendados nas regras de tipologia de pressão. Saiba mais na [documentação do Campaign Classic v7](https://experienceleague.adobe.com/docs/campaign-classic/using/orchestrating-campaigns/campaign-optimization/pressure-rules.html?lang=pt-BR#setting-the-period){target=&quot;_blank&quot;}