---
title: Perfis de operadores
description: Criar operadores de Gerenciamento de ofertas
feature: Overview
role: Data Engineer
level: Beginner
exl-id: 865ddb84-3373-45e0-849d-9d3c92455d22
source-git-commit: d2f4e54b0c37cc019061dd3a7b7048cd80876ac0
workflow-type: tm+mt
source-wordcount: '357'
ht-degree: 33%

---

# Perfis de operadores {#operator-profiles}

Dois tipos de operadores podem usar a Interação de campanha: **Gerentes de oferta** e **Gerentes de delivery**. Cada um deles tem permissões e restrições específicas. Saiba mais sobre operadores e permissões do Campaign em [esta página](../start/permissions.md).

* O **[!UICONTROL Offer manager]** cria e mantém ofertas.
* O **[!UICONTROL Delivery manager]** aprova e usa ofertas

## Criar um operador do Offer manager{#offer-manager}

1. Criar um operador.

   ![](../assets/do-not-localize/book.png) As etapas para criar um operador no Campaign são detalhadas em [Documentação do Campaign Classic v7](https://experienceleague.adobe.com/docs/campaign-classic/using/getting-started/permissions/access-management-operators.html)

1. Vá para a janela **[!UICONTROL Groups and named rights]**, clique em **[!UICONTROL Add]** e selecione o grupo **[!UICONTROL Offer manager]**.

Os direitos atribuídos ao Gerente de ofertas permitem que eles executem as seguintes tarefas:

* Modificar ambientes **[!UICONTROL Design]**.
* Visualizar ambientes **[!UICONTROL Live]**.
* Configurar funções de administração (espaços e filtros predefinidos).
* Criar e alterar categorias.
* Criar ofertas.
* Configurar a qualificação para a oferta.
* Aprovar ofertas.

Se as ofertas forem usadas em um workflow, o operador deverá ser adicionado ao **[!UICONTROL Administrator]** ou **[!UICONTROL Offer managers]** grupo de operadores para executar o workflow.

>[!NOTE]
>
>**Gerentes de oferta** só pode aprovar uma oferta se nenhum revisor for especificado, ou se eles tiverem sido declarados como revisores no template de oferta.

## Criar um operador Delivery manager {#delivery-manager}

1. Criar um operador.

   ![](../assets/do-not-localize/book.png) As etapas para criar um operador no Campaign são detalhadas em [Documentação do Campaign Classic v7](https://experienceleague.adobe.com/docs/campaign-classic/using/getting-started/permissions/access-management-operators.html)

1. Vá para a janela **[!UICONTROL Groups and named rights]**, clique em **[!UICONTROL Add]** e selecione o grupo **[!UICONTROL Delivery manager]**.

Os direitos atribuídos aos Gerentes de delivery permitem que eles executem as seguintes tarefas:

* Exibir ambientes **[!UICONTROL Live]**.
* Exibir e modificar categorias de ofertas.
* Aprovar ofertas se elas forem revisores.

   >[!NOTE]
   >
   >**Gerentes de delivery** só poderá aprovar uma oferta se ela tiver sido declarada como revisores na configuração de oferta.

## Matriz de permissões por operador de interação {#recap-of-rights-according-to-operator}

<table> 
 <tbody> 
  <tr> 
   <td> </td> 
   <td> <strong>Gerente de ofertas (ambiente Design)</strong><br /> </td> 
   <td> <strong>Gerente de ofertas (Ambiente dinâmico)</strong><br /> </td> 
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
   <td> Recipiente - Ambiente<br /> </td> 
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
   <td> <strong>Gerente de delivery (Design env.)</strong><br /> </td> 
   <td> <strong>Gerente de delivery (Live env.)</strong><br /> </td> 
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
   <td> Recipiente - Ambiente<br /> </td> 
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
