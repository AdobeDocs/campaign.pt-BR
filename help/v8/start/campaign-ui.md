---
title: Conheça o espaço de trabalho do Campaign
description: Saiba como navegar e usar o espaço de trabalho do Campaign
feature: Overview
role: Admin, Developer, User
level: Beginner
exl-id: a7846b95-7570-4dce-b3f4-d3cc23eefcac
source-git-commit: 3c7455f348468a8f00fb853a3269a1d63b81e7b8
workflow-type: tm+mt
source-wordcount: '524'
ht-degree: 32%

---

# Conheça a interface do usuário do Campaign

## Acessar a interface do Campaign{#ui-access}

O espaço de trabalho do Campaign está disponível por meio do [Console do cliente](../architecture/general-architecture.md).

Saiba como instalar e configurar o Console do cliente do Campaign no [nesta seção](../start/connect.md).

![](assets/home-page.png)

Você também pode usar um navegador da Web para acessar o Campaign. Nesse contexto, somente um subconjunto de recursos do Campaign está disponível. [Saiba mais](#web-browser)

## Navegar na interface{#ui-browse}

Depois de se conectar ao Campaign, você acessa a home page. Navegue pelos links para acessar recursos do. O conjunto de recursos disponíveis na interface do usuário depende de suas opções e permissões.

Na seção central da página inicial, use links para acessar os materiais de ajuda do Campaign, a comunidade e o site de suporte.

Use as guias na seção superior para procurar recursos principais do Campaign:

![](assets/overview-home.png)

>[!NOTE]
>
>A lista de recursos principais que você pode acessar depende das suas permissões e da sua implementação.

Para cada recurso, você pode acessar o conjunto de recursos principais na **[!UICONTROL Browsing]** seção. A variável **[!UICONTROL More]** link permite acessar todos os outros componentes.

Por exemplo, ao navegar até o **[!UICONTROL Profiles and targets]** , você poderá acessar listas de recipients, serviços de assinatura, workflows para construção do target existentes e atalhos para criar todos esses componentes.

![](assets/overview-list.png)

Quando você seleciona um elemento na tela, ele é carregado em uma nova guia para que você possa navegar facilmente pelo conteúdo.

![](assets/new-tab.png)

## Criar um elemento {#create-an-element}

Use atalhos na **[!UICONTROL Create]** à esquerda da tela para adicionar novos elementos. Você também pode usar a variável **[!UICONTROL Create]** acima da lista para adicionar novos elementos a ela.

Por exemplo, na página de delivery, use o botão **[!UICONTROL Create]** para criar um novo delivery.

![](assets/new-recipient.png)

## Usar um navegador da Web {#web-browser}

Também é possível acessar um subconjunto de recursos do Campaign por meio de um navegador da Web.

A interface de acesso da web é semelhante à interface do console. Em um navegador, você pode usar os mesmos recursos de navegação e exibição do console, mas é possível executar apenas um conjunto reduzido de ações em campanhas. Por exemplo, é possível visualizar e cancelar campanhas, mas não modificar campanhas.

![](../assets/do-not-localize/glass.png) [Saiba mais sobre o Campaign Web Access](../start/connect.md#web-access).

## Acessar o explorador do Campaign {#ac-explorer-ui}

Navegue pelo Campaign Explorer para acessar todos os recursos e configurações do Adobe Campaign.

![](assets/explorer.png)

Esse espaço de trabalho permite que você acesse a árvore do Explorer para procurar todos os recursos e opções.

* A seção à esquerda mostra a árvore do explorador do Campaign e permite navegar por todos os componentes e configurações da sua instância com base em suas permissões. Você pode adicionar e personalizar pastas conforme explicado em [esta página](../audiences/folders-and-views.md).

* A seção superior mostra a lista de registros na pasta atual. Essas listas são totalmente personalizáveis. [Saiba mais](../config/ui-settings.md)

* A seção inferior mostra os detalhes do registro selecionado.

## Idiomas{#languages}

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

O idioma afeta datas e formatos de hora.

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
