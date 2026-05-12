---
title: Introdução às REST APIs do Campaign
description: Crie integrações e construa seu próprio ecosistema interligando o Campaign a um painel de tecnologias.
audience: developing
content-type: reference
topic-tags: campaign-standard-apis
role: Developer
level: Experienced
exl-id: c6968252-a012-4029-bbb8-66f4f693e99b
TQID: https://experienceleague.adobe.com/RRDY-7SFGUwxHk34LLhRHaFN-0U4A9NQfNvLPXO8GM8
product_v2:
  - id: dfc56824-e8b9-499e-85d4-21aedb507314
feature_v2:
  - id: b12f6872-9271-4369-85e5-86969a0b99a2
  - id: d5ef99fa-df0c-4153-bf94-105ad0724167
subfeature_v2:
  - id: bf97c196-a4d1-4fa3-a151-e68a114c8ac0
role_v2:
  - id: ff6a42d2-313e-452e-93a6-792e4fad9ff8
source-git-commit: 15d7b12d07f84356fac7bee2a54a0057c5d00d41
workflow-type: tm+mt
source-wordcount: 240
ht-degree: 58%

---

# Introdução às REST APIs do Campaign {#get-started-apis}

As APIs REST do Campaign permitem **criar integrações** com o Adobe Campaign e **criar seu próprio ecossistema**, conectando o Adobe Campaign ao painel de tecnologias que você usa.

>[!AVAILABILITY]
>
>* Esse recurso só está disponível sob demanda para todos os [ambientes FDA do Campaign](../../architecture/fda-deployment.md). Ele **não** disponível para [implantações corporativas (FFDA)](../../architecture/enterprise-deployment.md). Para obter acesso, entre em contato com o(a) representante da Adobe.
>
>* Antes de executar chamadas de API, verifique as limitações de escala correspondentes ao seu contrato de licença. Para obter mais informações, consulte a [Descrição do produto Adobe Campaign v8](https://helpx.adobe.com/br/legal/product-descriptions/adobe-campaign-managed-cloud-services.html){target="_blank"}.


Com as APIs REST do Adobe Campaign, você obtém acesso às seguintes funcionalidades:

<table><tr>
 <td valign="top"><a href="retrieving-profiles.md"><img width="60px" alt="condições" src="assets/icon_profile.svg"/></a><p><a href="retrieving-profiles.md">Perfis</a></p></td>
<td valign="top"><a href="creating-a-service.md"><img width="60px" alt="condições" src="assets/icon_services.svg"/></a><p><a href="creating-a-service.md">Serviços e assinaturas</a></p></td>
<td valign="top"><a href="interacting-with-custom-resources.md"><img width="60px" alt="condições" src="assets/icon_customresources.svg"/></a><p><a href="interacting-with-custom-resources.md">Recursos personalizados</a></p></td>
<td valign="top"><a href="controlling-a-workflow.md"><img width="60px" alt="condições" src="assets/icon_workflows.svg"/></a><p><a href="controlling-a-workflow.md">Fluxos de trabalho</a></p></td>
<td valign="top"><a href="managing-transactional-messages.md"><img width="60px" alt="condições" src="assets/icon_transactionalmessage.svg"/></a><p><a href="managing-transactional-messages.md">Mensagens transacionais</a></p></td>
</tr></table>

Para usar as REST APIs do Campaign, você precisa de uma conta do Adobe I/O. Esta é uma primeira etapa obrigatória para avançar e descobrir os recursos da API.
Para obter mais informações, consulte [esta seção](setting-up-api-access.md).

As APIs que fornecemos usam **conceitos padrão** com uma interface REST e cargas JSON.

Todos os pontos de extremidade são descritos extensivamente nesta documentação com as noções gerais que você deve ter para manipular a API, a referência completa da API, exemplos de código e guias de início rápido. Todos os exemplos funcionam com o Postman, mas podem usar seu cliente REST favoritos.

