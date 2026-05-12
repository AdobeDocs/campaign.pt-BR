---
title: Medidas de proteção do Campaign v8
description: Medidas de proteção do Campaign v8
feature: Configuration
role: User
level: Beginner
exl-id: 50c254ba-cc33-49b2-b7d5-12aa69883c07
TQID: https://experienceleague.adobe.com/4FF81xd4CiMT3fusDRU32n0-ap16O1RVUEhGIbz33Os
product_v2: id: dfc56824-e8b9-499e-85d4-21aedb507314
role_v2: id: b69b2659-1057-424e-8fc5-ed9e016dc554
level_v2: id: e8ccd51f-da0d-4e3b-939b-e30d5ebb1ea5
topic_v2: id: cdd65e7e-8839-44a2-bc21-0e03623b5dd1
source-git-commit: 15d7b12d07f84356fac7bee2a54a0057c5d00d41
workflow-type: tm+mt
source-wordcount: 265
ht-degree: 78%

---

# Medidas de proteção do produto{#guardrails}

Os direitos, as limitações de produto e as medidas de proteção de desempenho estão listados na [página de descrição do produto Adobe Campaign Managed Cloud Services](https://helpx.adobe.com/br/legal/product-descriptions/adobe-campaign-managed-cloud-services.html){target="_blank"}.

Abaixo você encontrará medidas de proteção e limitações adicionais para uso do [!DNL Adobe Campaign].

As medidas de proteção e limitações identificam recursos, arquiteturas ou processos que não são compatíveis com essa versão do produto ou que não interoperam corretamente com ele. Revise essas limitações cuidadosamente.

* O Adobe Campaign v8 não está disponível para implantações locais/híbridas, apenas as lançadas como um Adobe Managed Cloud Service
* Não há migração automática para o Adobe Campaign v8 disponível para clientes existentes
* No contexto de uma [implantação corporativa (FFDA)](../../v8/architecture/enterprise-deployment.md), nenhuma replicação bidirecional de dados é fornecida: a replicação acontece somente a partir do banco de dados local do Campaign para o banco de dados da nuvem
* Os recursos listados [nesta seção](v7-to-v8.md#gs-unavailable-features) não estão disponíveis na build atual do Campaign v8
* Alguns recursos não disponíveis ou removidos ainda estão visíveis na interface do usuário
* No contexto de uma [implantação corporativa (FFDA)](../architecture/enterprise-deployment.md), os mecanismos de assinatura (aceitação) e cancelamento de assinatura (recusa) e o registro em dispositivos móveis são processos assíncronos. As solicitações são processadas a cada hora por meio de um fluxo de trabalho técnico específico. [Saiba mais](../architecture/replication.md#tech-wf)
* No contexto de uma [implantação corporativa (FFDA)](../architecture/enterprise-deployment.md), os duplicados precisam ser manipulados manualmente pelos usuários finais. [Saiba mais](../architecture/keys.md)
* O Adobe Campaign v8 não é compatível com a produtividade estendida em aplicativos da API e da Web; no caso de necessidades específicas, entre em contato com a Adobe para obter orientação
* No contexto de uma [implantação corporativa (FFDA)](../architecture/enterprise-deployment.md), o módulo de Otimização de Campanha da Adobe Campaign não considera as entregas agendadas nas regras de tipologia de pressão. Saiba mais [nesta página](../../automation/campaign-opt/pressure-rules.md)