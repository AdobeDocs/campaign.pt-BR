---
product: Adobe Campaign
title: Limitações conhecidas do Campaign v8
description: Limitações conhecidas
feature: Visão geral
role: Data Engineer
level: Beginner
hidefromtoc: true
source-git-commit: cf00895f988514fc029d0060d7404bdef0c8b30e
workflow-type: tm+mt
source-wordcount: '177'
ht-degree: 87%

---

# Limitações conhecidas

Limitações conhecidas identificam recursos, arquitetura ou processos que não são compatíveis com essa versão do produto ou que não interoperam corretamente com ele. Revise essas limitações cuidadosamente.

Para o Adobe Campaign v8, existem as seguintes limitações:

* O Adobe Campaign v8 não está disponível para implantações locais/híbridas, apenas as lançadas como um serviço na nuvem gerenciado pela Adobe.
* Os clientes existentes não podem migrar de um ambiente do Adobe Campaign existente para o Adobe Campaign v8
* Nenhuma replicação de dados bidirecional: a replicação acontece somente a partir do banco de dados local do Campaign para o banco de dados na nuvem.
* Os recursos listados [nesta seção](capability-matrix.md#gs-unavailable-features) não estão disponíveis na build atual do Campaign v8
* Alguns recursos não disponíveis ou removidos ainda estão visíveis na interface do usuário
* Os mecanismos de subscrição (aceitação) e cancelamento de subscrição (recusa) e registro móvel são processos assíncronos. As solicitações são processadas a cada hora por meio de um fluxo de trabalho técnico específico. [Saiba mais](../config/replication.md#tech-wf)
* As duplicatas precisam ser manipuladas manualmente pelos usuários finais. [Saiba mais](../dev/keys.md)
* O Adobe Campaign v8 não suporta throughput estendida em aplicativos da API e da Web. Em caso de necessidades específicas, entre em contato com o Adobe para obter orientação.


