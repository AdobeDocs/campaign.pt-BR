---
product: campaign
title: Apresentar ofertas a perfis anônimos (interação de entrada)
description: Saiba como apresentar ofertas a perfis anônimos
exl-id: b7a04360-f8c6-4c69-9594-2b44d3f819b7
source-git-commit: 00a88cf9217faf32070a3cd34a2c1ae5243d9a6e
workflow-type: tm+mt
source-wordcount: '397'
ht-degree: 75%

---

# Interações anônimas{#anonymous-interactions}

## Ambiente para interações anônimas {#environment-for-anonymous-interactions}

Por padrão, Campaign **Interação** vem com um ambiente pré-configurado para direcionar a tabela de recipients integrada (ofertas identificadas). Se precisar direcionar outra tabela, uma tabela de visitante para ofertas anônimas ou uma tabela de recipients personalizada, por exemplo, é necessário usar o assistente de target mapping para criar o ambiente. [Saiba mais sobre ambientes](interaction-env.md).

Ao criar um ambiente anônimo através do assistente de criação de mapeamento, a caixa **[!UICONTROL Environment dedicated to incoming anonymous interactions]** é automaticamente marcada na guia **[!UICONTROL General]** do ambiente.

O **[!UICONTROL Targeting dimension]** é automaticamente concluído. Por padrão, ele vincula à tabela do visitante.

O campo **[!UICONTROL Visitor folder]** é exibido. Ele é automaticamente preenchido para vincular à pasta **[!UICONTROL Visitors]**. Este campo permite escolher onde armazenar os perfis de visitantes.

![](assets/anonymous_environment_option.png)

>[!NOTE]
>
>Para filtrar vários tipos de visitantes, por exemplo, no caso de ofertas anônimas apresentadas para uma ou mais marcas, é necessário criar um ambiente para cada marca e uma pasta do tipo **[!UICONTROL Visitors]** para cada ambiente.

## Catálogo de ofertas para interações anônimas {#offer-catalog-for-anonymous-interactions}

Assim como as interações de saída, as interações de entrada são organizadas em um catálogo de ofertas que é composto por categorias e ofertas.

Para criar categorias e espaços, aplique o mesmo processo dos visitantes identificados. Consulte [Criar uma categoria de oferta](interaction-offer-catalog.md#creating-offer-categories) e [Criar um ambiente de oferta](interaction-env.md#creating-an-offer-environment)).

## Visitantes anônimos {#anonymous-visitors}

Os visitantes anônimos podem ser submetidos a um processo de identificação por cookies quando se conectam. Esse reconhecimento implícito baseia-se no histórico do navegador do visitante.

Durante essa etapa, uma comparação é feita entre os dados recuperados pelos cookies e aqueles no banco de dados. Em alguns casos, os visitantes são reconhecidos (são então identificados implicitamente), em outros casos, eles não são reconhecidos (e, portanto, permanecem anônimos).

Para executar essa análise, para o espaço de ofertas, marque a opção **[!UICONTROL Implicitly identify the individual based on their browser history]**.

![](assets/identification_anonymous_visitors.png)

## Processamento de visitantes anônimos não identificados {#processing-unidentified-anonymous-visitors}

Após a análise, se um visitante anônimo não for identificado, é possível armazenar seus dados em um determinado espaço. Isso permitirá sugerir ofertas especificamente destinadas a este tipo de visitante, correspondendo às regras específicas da tipologia.

Se não houver elemento que permitam identificar um contato ou se não quiser sugerir uma oferta identificada para um contato que possa ser identificado implicitamente, é possível optar por realizar um fallback em um ambiente anônimo.

Para fazer isso, marque a opção **[!UICONTROL Fall back on an anonymous environment if no individuals were identified]** e, em seguida, especifique o ambiente dedicado para esses visitantes não identificados em **[!UICONTROL Linked anonymous space]** quando especificar um espaço de oferta.

![](assets/anonymous_to_anonymous_environment.png)
