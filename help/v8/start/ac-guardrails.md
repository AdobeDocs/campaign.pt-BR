---
title: Medidas de proteção do Campaign v8
description: Medidas de proteção do Campaign v8
feature: Overview
role: User
level: Beginner, Intermediate, Experienced
exl-id: 50c254ba-cc33-49b2-b7d5-12aa69883c07
source-git-commit: 58fff46ba12f5c6221bbcd88a40fa0806a6c98b9
workflow-type: ht
source-wordcount: '245'
ht-degree: 100%

---

# Medidas de proteção do produto{#guardrails}

Os direitos, as limitações de produto e as medidas de proteção de desempenho estão listados na [página de descrição do produto Adobe Campaign Managed Cloud Services](https://helpx.adobe.com/br/legal/product-descriptions/adobe-campaign-managed-cloud-services.html){target="_blank"}.

Abaixo você encontrará medidas de proteção e limitações adicionais para uso do [!DNL Adobe Campaign].

As medidas de proteção e limitações identificam recursos, arquiteturas ou processos que não são compatíveis com essa versão do produto ou que não interoperam corretamente com ele. Revise essas limitações cuidadosamente.

* O Adobe Campaign v8 não está disponível para implantações locais/híbridas, apenas as lançadas como um Adobe Managed Cloud Service
* Não há migração automática para o Adobe Campaign v8 disponível para clientes existentes
* No contexto de uma [implantação corporativa (FFDA)](../architecture/enterprise-deployment.md), nenhuma replicação bidirecional de dados é fornecida: a replicação acontece somente a partir do banco de dados local do Campaign para o banco de dados da nuvem
* Os recursos listados [nesta seção](v7-to-v8.md#gs-unavailable-features) não estão disponíveis na build atual do Campaign v8
* Alguns recursos não disponíveis ou removidos ainda estão visíveis na interface do usuário
* No contexto de uma [implantação corporativa (FFDA)](../architecture/enterprise-deployment.md), os mecanismos de assinatura (aceitação) e cancelamento de assinatura (recusa) e o registro em dispositivos móveis são processos assíncronos. As solicitações são processadas a cada hora por meio de um fluxo de trabalho técnico específico. [Saiba mais](../architecture/replication.md#tech-wf)
* As duplicatas precisam ser manipuladas manualmente pelos usuários finais. [Saiba mais](../architecture/keys.md)
* O Adobe Campaign v8 não é compatível com a produtividade estendida em aplicativos da API e da Web; no caso de necessidades específicas, entre em contato com a Adobe para obter orientação
* O módulo de otimização de campanha do Adobe Campaign não considera os deliveries agendados nas regras de tipologia de pressão. Saiba mais [nesta página](https://experienceleague.adobe.com/docs/campaign/automation/campaign-optimization/pressure-rules.html?lang=pt-BR)