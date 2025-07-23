---
title: Introdução às REST APIs do Campaign
description: Crie integrações e construa seu próprio ecosistema interligando o Campaign a um painel de tecnologias.
audience: developing
content-type: reference
topic-tags: campaign-standard-apis
role: Data Engineer
level: Experienced
exl-id: c6968252-a012-4029-bbb8-66f4f693e99b
source-git-commit: c74669a0ccdabe735eb905b7e8c1634140a7ea0b
workflow-type: tm+mt
source-wordcount: '239'
ht-degree: 47%

---

# Introdução às REST APIs do Campaign {#get-started-apis}

>[!AVAILABILITY]
>
>Esse recurso só está disponível sob demanda para todos os ambientes FDA do Campaign. **não** disponível para implantações do FFDA do Campaign. Para obter acesso, entre em contato com o representante da Adobe.

>[!CAUTION]
>
>Antes de executar chamadas de API, verifique as limitações de escala correspondentes ao seu contrato de licença. Para obter mais informações, consulte [esta página](https://helpx.adobe.com/br/legal/product-descriptions/campaign-standard.html#ITInfrastructureResourcesbyActiveProfilesTiers).

As APIs REST do Campaign permitem **criar integrações** com o Adobe Campaign e **criar seu próprio ecossistema**, conectando o Adobe Campaign ao painel de tecnologias que você usa.

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

Todos os endpoints são descritos extensivamente nesta documentação com as noções gerais que você deve ter para manipular a API, a referência completa da API, exemplos de código e guias de início rápido. Todos os exemplos funcionam com o Postman, mas podem usar seu cliente REST favoritos.

Se algo estiver incorreto ou ausente, pergunte à [comunidade](https://experienceleaguecommunities.adobe.com/t5/adobe-campaign-standard/ct-p/adobe-campaign-standard-community?profile.language=pt).
