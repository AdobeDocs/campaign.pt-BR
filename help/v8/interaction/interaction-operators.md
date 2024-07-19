---
title: Perfis de operadores
description: Criar operadores de Gerenciamento de ofertas
feature: Interaction, Offers
role: User, Admin
level: Beginner
exl-id: 865ddb84-3373-45e0-849d-9d3c92455d22
source-git-commit: 567c2e84433caab708ddb9026dda6f9cb717d032
workflow-type: tm+mt
source-wordcount: '243'
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
