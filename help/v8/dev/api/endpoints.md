---
title: Pontos de acesso
description: Saiba mais sobre os endpoints das APIs.
audience: developing
content-type: reference
topic-tags: campaign-standard-apis
role: Developer
level: Experienced
exl-id: 9f6d3da6-374d-47f5-bc8f-b31b19cbb5ca
TQID: https://experienceleague.adobe.com/1ajh28ZpUsuyTh-qHnto3GsH4J25WSsyK7TqTjlhHfg
product_v2:
  - id: dfc56824-e8b9-499e-85d4-21aedb507314
feature_v2:
  - id: b12f6872-9271-4369-85e5-86969a0b99a2
subfeature_v2:
  - id: bf97c196-a4d1-4fa3-a151-e68a114c8ac0
role_v2:
  - id: ff6a42d2-313e-452e-93a6-792e4fad9ff8
topic_v2:
  - id: a004cc84-67b9-4a33-a3a7-8ec7273ef4dc
source-git-commit: 15d7b12d07f84356fac7bee2a54a0057c5d00d41
workflow-type: tm+mt
source-wordcount: 197
ht-degree: 9%

---

# Pontos de acesso {#endpoints}

Os endpoints disponíveis para a API REST do Adobe Campaign:

* **/profileAndServices**: interage com campos prontos para uso. Os campos estendidos não podem ser acessados com este endpoint.
* **/profileAndServicesExt**: interage com campos personalizados adicionados durante a extensão de recurso personalizado Perfil ou Serviços. Para obter mais informações sobre recursos personalizados, consulte [esta seção](custom-resources.md).
* **/&lt;transactionalAPI>**: interagir com a API de mensagens transacionais (o nome do ponto de extremidade da API de mensagens transacionais depende da configuração da instância). Para obter mais informações, consulte [esta seção](managing-transactional-messages.md).
* **/workflow/execution**: interagir com fluxos de trabalho. Para obter mais informações, consulte [esta seção](controlling-a-workflow.md).

Por padrão, os principais recursos disponíveis para as APIs **profileAndServices** e **profileAndServicesExt** são:

* **/profile**: interagir com perfis do banco de dados do Campaign. Para adicionar perfis a um serviço, use o ponto de extremidade **/serviço**. Para obter mais informações sobre perfis no Campaign, consulte a [documentação do Campaign](https://helpx.adobe.com/campaign/standard/audiences/using/about-profiles.html).
* **/serviço**: gerenciar serviços de assinatura. Para obter mais informações sobre os serviços no Campaign, consulte a [documentação do Campaign](https://helpx.adobe.com/campaign/standard/audiences/using/creating-a-service.html).

>[!NOTE]
>
>Todos os outros recursos estendidos ou criados estão disponíveis somente por meio da API **ProfileAndServicesExt**. Eles devem estar vinculados ao recurso **Perfil** para serem acessíveis.
