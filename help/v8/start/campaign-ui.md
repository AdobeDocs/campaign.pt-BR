---
title: Espaço de trabalho do Discover Campaign
description: Saiba como navegar e usar a área de trabalho do Campaign
feature: Overview
role: Data Engineer
level: Beginner
exl-id: a7846b95-7570-4dce-b3f4-d3cc23eefcac
source-git-commit: b54a39ee6d106d68446878815c068571e310aaa3
workflow-type: tm+mt
source-wordcount: '513'
ht-degree: 32%

---

# Interface do usuário do Discover Campaign

## Acessar a interface do usuário do Campaign

O espaço de trabalho do Campaign está disponível por meio do [Console do cliente](../dev/general-architecture.md).

Saiba como instalar e configurar o Console do cliente do Campaign em [esta seção](../start/connect.md).

![](assets/home-page.png)

Você também pode usar um navegador da Web para acessar o Campaign. Nesse contexto, somente um subconjunto de recursos do Campaign está disponível. [Saiba mais](#web-browser)

## Procurar a interface do usuário

Depois de se conectar ao Campaign, você acessa a página inicial. Navegue pelos links para acessar os recursos. O conjunto de recursos disponíveis na interface do usuário depende de suas opções e permissões.

Na seção central da página inicial, use links para acessar os materiais de ajuda do Campaign, a comunidade e o site de suporte.

Use as guias na seção superior para navegar pelos principais recursos do Campaign:

![](assets/overview-home.png)

>[!NOTE]
>
>A lista de recursos principais que você pode acessar depende de suas permissões e da implementação.

Para cada recurso, você pode acessar o conjunto de recursos principais na variável **[!UICONTROL Browsing]** seção. O **[!UICONTROL More]** permite acessar todos os outros componentes.

Por exemplo, ao navegar para a variável **[!UICONTROL Profiles and targets]** , é possível acessar as listas de recipients, os serviços de assinatura, os workflows para construção do target existentes e os atalhos para criar todos esses componentes.

![](assets/overview-list.png)

Ao selecionar um elemento na tela, ele é carregado em uma nova guia, para que você possa navegar facilmente pelo conteúdo.

![](assets/new-tab.png)

## Criar um elemento {#create-an-element}

Use atalhos no **[!UICONTROL Create]** à esquerda da tela para adicionar novos elementos. Também é possível usar a variável **[!UICONTROL Create]** acima da lista para adicionar novos elementos a ela.

Por exemplo, na página de delivery, use o botão **[!UICONTROL Create]** para criar um novo delivery.

![](assets/new-recipient.png)

## Usar um navegador da Web {#web-browser}

Você também pode acessar um subconjunto de recursos do Campaign por meio de um navegador da Web.

A interface de acesso da web é semelhante à interface do console. Em um navegador, você pode usar os mesmos recursos de navegação e exibição do console, mas é possível executar apenas um conjunto reduzido de ações em campanhas. Por exemplo, é possível visualizar e cancelar campanhas, mas não modificar campanhas.

![](../assets/do-not-localize/glass.png) [Saiba mais sobre o acesso à Web do Campaign](../start/connect.md#web-access).

## Acessar o explorador da campanha {#ac-explorer-ui}

Navegue pelo explorador do Campaign para acessar todos os recursos e configurações do Adobe Campaign.

![](assets/explorer.png)

Este espaço de trabalho permite acessar a árvore do Explorer para procurar todos os recursos e opções.

A seção à esquerda mostra a árvore do explorador do Campaign e permite navegar em todos os componentes e configurações da sua instância, com base em suas permissões.

A seção superior mostra a lista de registros na pasta atual. Essas listas são totalmente personalizáveis. [Saiba mais](customize-ui.md)

A seção inferior mostra os detalhes do registro selecionado.


## Idiomas

A interface do usuário do Campaign v8 está disponível nos seguintes idiomas:

* Inglês (Reino Unido)
* Inglês (EUA)
* Francês
* Alemão
* Japonês

O idioma é selecionado durante o processo de instalação.

>[!CAUTION]
>
>O idioma não pode ser alterado após a criação da instância.

O idioma afeta os formatos de data e hora.


As principais diferenças entre inglês americano e inglês do Reino Unido são:

<table> 
 <thead> 
  <tr> 
   <th> Formatos<br /> </th> 
   <th> Inglês (US)<br /> </th> 
   <th> Inglês (EN)<br /> </th> 
  </tr> 
 </thead> 
 <tbody> 
  <tr> 
   <td> Data<br /> </td> 
   <td> A semana começa no domingo<br /> </td> 
   <td> A semana começa na segunda-feira<br /> </td> 
  </tr> 
  <tr> 
   <td> Data abreviada<br /> </td> 
   <td> <p>%2M/%2D/%4Y</p><p><strong>ex: 09/25/2018</strong></p> </td> 
   <td> <p>%2D/%2M/%4Y</p><p><strong>ex: 25/09/2018</strong></p> </td> 
  </tr> 
  <tr> 
   <td> Data abreviada com hora<br /> </td> 
   <td> <p>%2M/%2D/%4Y %I:%2N:%2S %P</p><p><strong>ex: 25/09/2018 22:47:25</strong></p> </td> 
   <td> <p>%2D/%2M/%4Y %2H:%2N:%2S</p><p><strong>ex: 25/09/2018 22:47:25</strong></p> </td> 
  </tr> 
 </tbody> 
</table>
