---
solution: Campaign v8
product: Adobe Campaign
title: Limitações conhecidas do Campaign v8
description: Limitações conhecidas
feature: Visão geral
role: Data Engineer
level: Beginner
hidefromtoc: true
source-git-commit: 15cd7228a4920702cae182c68e7a329345946e31
workflow-type: tm+mt
source-wordcount: '158'
ht-degree: 1%

---

# Limitações conhecidas

Limitações conhecidas identificam recursos, arquitetura ou processos que não são compatíveis com essa versão do produto ou que não interoperam corretamente com ele. Revise essas limitações cuidadosamente.

Para o Adobe Campaign v8, existem as seguintes limitações:

* O Adobe Campaign v8 não está disponível para implantações locais/híbridas, apenas lançadas como um Cloud Service Adobe Managed.
* Os clientes existentes não podem migrar de um ambiente Adobe Campaign existente para o Adobe Campaign v8
* Nenhuma replicação de dados bidirecional: a replicação acontece somente a partir do banco de dados local do Campaign para o banco de dados do Cloud
* Os recursos listados [nesta seção](capability-matrix.md#gs-unavailable-features) não estão disponíveis na build atual do Campaign v8
* Alguns recursos não disponíveis ou removidos ainda estão visíveis na interface do usuário
* Os mecanismos de assinatura (aceitação) e cancelamento de subscrição (recusa) e registro móvel são processos assíncronos. As solicitações são processadas a cada hora por meio de um workflow técnico específico. [Saiba mais](../config/replication.md#tech-wf)
* Gerenciamento de ID - duplicatas - para confirmar + detalhes
* LINE - para confirmar + detalhes
* Latência - para confirmar + detalhes
