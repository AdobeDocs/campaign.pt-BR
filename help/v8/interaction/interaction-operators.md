---
title: Perfis de operadores
description: Criar operadores de Gerenciamento de ofertas
feature: Interaction, Offers
role: User, Admin
level: Beginner
exl-id: 865ddb84-3373-45e0-849d-9d3c92455d22
TQID: https://experienceleague.adobe.com/0Nx5tAtCSIZ3Ctm8MHRU7Aa2-8CyX6IbDgj9RF5KlSI
product_v2:
  - id: dfc56824-e8b9-499e-85d4-21aedb507314
role_v2:
  - id: b69b2659-1057-424e-8fc5-ed9e016dc554
  - id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
level_v2:
  - id: e8ccd51f-da0d-4e3b-939b-e30d5ebb1ea5
topic_v2:
  - id: eddd9b14-83bd-4ff4-9072-54a4a484abb7
source-git-commit: 15d7b12d07f84356fac7bee2a54a0057c5d00d41
workflow-type: tm+mt
source-wordcount: 245
ht-degree: 35%

---

# Perfis de operadores {#operator-profiles}

Dois tipos de operadores podem usar a Interação de campanha: **Gerentes de oferta** e **Gerentes de entrega**. Cada um deles tem permissões e restrições específicas. Saiba mais sobre operadores e permissões do Campaign em [esta página](../start/gs-permissions.md).

* O **[!UICONTROL Offer manager]** cria e mantém ofertas.
* O **[!UICONTROL Delivery manager]** aprova e usa ofertas

## Criar um operador do Offer manager{#offer-manager}

1. Crie um operador. [Saiba mais](../start/manage-permissions.md#add-users)
1. Navegue até a janela **[!UICONTROL Groups and named rights]**, clique em **[!UICONTROL Add]** e selecione o grupo **[!UICONTROL Offer manager]**.

As permissões associadas aos gerentes de oferta estão descritas [aqui](../start/manage-permissions.md#ootb-productprofiles)

## Criar um operador de Gerente de delivery {#delivery-manager}

1. Crie um operador. [Saiba mais](../start/manage-permissions.md#add-users)
1. Navegue até a guia **[!UICONTROL Groups and named rights]**, clique em **[!UICONTROL Add]** e selecione o grupo **[!UICONTROL Delivery manager]**.

Os direitos atribuídos aos Gerentes de delivery os habilitam a realizar as seguintes tarefas:

* Exibir ambientes **[!UICONTROL Live]**.
* Exibir e modificar categorias de ofertas.
* Aprove ofertas se elas forem revisores.

  >[!NOTE]
  >
  >**Os gerentes de delivery** só podem aprovar uma oferta se tiverem sido declarados como revisores na configuração da oferta.

## Matriz de permissões por operador de interação {#recap-of-rights-according-to-operator}

<table> 
 <tbody> 
  <tr> 
   <td> </td> 
   <td> <strong>Gerente de ofertas (Ambiente de design)</strong><br /> </td> 
   <td> <strong>Gerente de ofertas (ambiente Live)</strong><br /> </td> 
  </tr> 
  <tr> 
   <td> <strong>Nível de estrutura de árvore</strong><br /> </td> 
   <td> </td> 
   <td> </td> 
  </tr> 
  <tr> 
   <td> Ofertas que estão sendo editadas / Ofertas ativas<br /> </td> 
   <td> Ler / Gravar<br /> </td> 
   <td> Ler<br /> </td> 
  </tr> 
  <tr> 
   <td> Destinatário - Ambiente<br /> </td> 
   <td> Ler / Gravar<br /> </td> 
   <td> Ler<br /> </td> 
  </tr> 
  <tr> 
   <td> Administração<br /> </td> 
   <td> Ler / Gravar<br /> </td> 
   <td> Ler<br /> </td> 
  </tr> 
  <tr> 
   <td> Espaços<br /> </td> 
   <td> Ler / Gravar<br /> </td> 
   <td> Ler<br /> </td> 
  </tr> 
  <tr> 
   <td> filtros de oferta predefinidos<br /> </td> 
   <td> Ler / Gravar<br /> </td> 
   <td> Ler<br /> </td> 
  </tr> 
  <tr> 
   <td> Tipologia<br /> </td> 
   <td> Ler / Gravar<br /> </td> 
   <td> Ler<br /> </td> 
  </tr> 
  <tr> 
   <td> Regras de tipologia<br /> </td> 
   <td> Ler / Gravar<br /> </td> 
   <td> Ler<br /> </td> 
  </tr> 
  <tr> 
   <td> Catálogo de ofertas<br /> </td> 
   <td> Ler / Gravar<br /> </td> 
   <td> Ler<br /> </td> 
  </tr> 
  <tr> 
   <td> Categoria de oferta<br /> </td> 
   <td> Ler / Gravar<br /> </td> 
   <td> Ler<br /> </td> 
  </tr> 
 </tbody> 
</table>

<table> 
 <tbody> 
  <tr> 
   <td> </td> 
   <td> <strong>Gerente de entrega (Ambiente de design)</strong><br /> </td> 
   <td> <strong>Gerente de entrega (Ambiente dinâmico)</strong><br /> </td> 
  </tr> 
  <tr> 
   <td> <strong>Nível de estrutura de árvore</strong><br /> </td> 
   <td> </td> 
   <td> </td> 
  </tr> 
  <tr> 
   <td> Ofertas que estão sendo editadas / Ofertas ativas<br /> </td> 
   <td> </td> 
   <td> Ler<br /> </td> 
  </tr> 
  <tr> 
   <td> Destinatário - Ambiente<br /> </td> 
   <td> </td> 
   <td> Ler<br /> </td> 
  </tr> 
  <tr> 
   <td> Administração<br /> </td> 
   <td> </td> 
   <td> </td> 
  </tr> 
  <tr> 
   <td> Espaços<br /> </td> 
   <td> </td> 
   <td> </td> 
  </tr> 
  <tr> 
   <td> filtros de oferta predefinidos<br /> </td> 
   <td> Ler<br /> </td> 
   <td> Ler<br /> </td> 
  </tr> 
  <tr> 
   <td> Tipologia<br /> </td> 
   <td> Ler<br /> </td> 
   <td> Ler<br /> </td> 
  </tr> 
  <tr> 
   <td> Regras de tipologia<br /> </td> 
   <td> </td> 
   <td> Ler<br /> </td> 
  </tr> 
  <tr> 
   <td> Catálogo de ofertas<br /> </td> 
   <td> Ler<br /> </td> 
   <td> Ler<br /> </td> 
  </tr> 
  <tr> 
   <td> Categoria de oferta<br /> </td> 
   <td> </td> 
   <td> Ler<br /> </td> 
  </tr> 
 </tbody> 
</table>
