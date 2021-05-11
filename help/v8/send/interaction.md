---
solution: Campaign
product: Adobe Campaign
title: Interação de campanha - Gerenciamento de ofertas
description: Introdução ao Gerenciamento de ofertas
feature: Visão geral
role: Data Engineer
level: Beginner
translation-type: tm+mt
source-git-commit: 6f84e739f25caf5dbd2ef964e38a6264e4b4342b
workflow-type: tm+mt
source-wordcount: '1214'
ht-degree: 37%

---

# Interação e gestão de ofertas{#interaction-and-offer-management}

O Campaign vem com um módulo **Interaction** que permite responder em tempo real durante uma interação com um determinado contato (um cliente ou target), tornando-os uma única ou várias ofertas adaptadas. Por exemplo, essas podem ser mensagens de comunicação simples, ofertas especiais de um ou vários produtos ou um serviço.

Você pode criar um catálogo de ofertas com seus canais de saída (email, correspondência direta, SMS) para selecionar a melhor oferta para enviar a um contato em um determinado contexto. A seleção de melhor oferta para um recipient é baseada em **regras de elegibilidade**. A seleção de uma oferta de um conjunto de ofertas relevantes é determinada usando regras de prioridade. As regras de apresentação de ofertas levam em consideração o histórico do contato e ajudam a evitar que elas recebam a mesma oferta várias vezes.

A interação permite criar e gerenciar um catálogo de ofertas e configurar as regras de elegibilidade e os temas de aplicações vinculados a elas. Dependendo do canal escolhido, o conteúdo da oferta pode ser personalizado graças a várias funções de renderização. Por fim, você pode usar o módulo de simulação para calcular o impacto de uma apresentação de ofertas.

## Conceitos e terminologia

Descubra termos específicos da oferta e orientações relacionadas antes de começar.

* **** Os ambientes incluem um catálogo de ofertas e espaços de ofertas (ganchos). Você precisa criar um ambiente por targeting dimension.
Há dois tipos de ambientes:

   * **Ambiente** de design: as ofertas são criadas no ambiente de design, bem como nas regras de tipologia e . As regras de tipologia determinam as ofertas para apresentar (ou não) a uma pessoa alvo. A tabela de indivíduos que serão alvos das ofertas e a tabela para armazenar todas as propostas de oferta também são definidas neste ambiente. O nó **[!UICONTROL Design environment]** contém subpastas de espaço de ofertas, filtros predefinidos e categorias de ofertas. Para cada **[!UICONTROL Design environment]** existe um **[!UICONTROL Live environment]** somente leitura correspondente, gerado a partir desse mesmo **[!UICONTROL Design environment]**.
   * **Ambiente** dinâmico: ambiente vinculado a um  **[!UICONTROL Design environment]** que contém ofertas somente leitura cujo conteúdo e elegibilidade foram aprovados por meio do  **[!UICONTROL Design environment]**. Eles devem ser selecionados para serem apresentados inseridos em uma mensagem.

* O **Espaço de ofertas** é um local (pasta) que define o local onde a oferta é exposta. Ao criar um espaço de oferta, você pode especificar o canal, criar o conteúdo da oferta usando funções de renderização, especificar a ordem das ofertas e seu modo: modo unitário e/ou modo de lote (padrão). O espaço de oferta é a interface entre o canal e o mecanismo de oferta.
* O **Offer catalog** é um conjunto de ofertas definido no Adobe Campaign que pode ser selecionado durante uma interação. O catálogo é organizado hierarquicamente com cada nó correspondente a uma categoria.
* Uma **Category** é uma pasta vinculada ao catálogo de ofertas em um ambiente, que organiza ofertas com base na natureza, na data de elegibilidade e no tema da aplicação. Uma categoria pode conter subcategorias, que herdam todas as características da categoria principal. As regras de elegibilidade podem ser definidas para uma categoria como compartilhada para várias ofertas.
* **Os** temas da aplicação são palavras-chave definidas na categoria, que permitem filtrar ofertas quando são apresentadas, restringindo a seleção de ofertas a uma ou duas categorias.
* **As** regras de elegibilidade são restrições aplicadas a um ambiente, categoria ou oferta, relacionadas ao período de validade, target e peso. Eles permitem garantir que uma oferta esteja alinhada com o contato alvo.

   Nos ambientes, as regras de elegibilidade incluem regras de apresentação aplicadas às ofertas e às pessoas a serem alvos.

   Nas categorias, as regras de elegibilidade permitem limitar a validade da categoria no tempo, definir temas de aplicação e determinar as pessoas a serem alvos. Eles também podem receber um peso multiplicador por determinado período. Isso permite compartilhar as regras para ofertas em outras categorias e simplifica sua administração.

   Nas ofertas, as regras de elegibilidade permitem limitar a validade de ofertas no tempo e determinar as pessoas a serem alvos.

* A **Arbitragem** é a ação de selecionar ofertas que serão exibidas em um ambiente (ofertas elegíveis). A arbitragem classifica as ofertas por prioridade de acordo com os critérios definidos nas categorias, ofertas e ofertas de contexto.
* Uma **interação de saída** chama o mecanismo de interação de uma lista de contatos (usado para delivery de emails, mala direta etc.). As mesmas regras e processos são aplicados a cada contato. Esse tipo de interação geralmente é processado em modo de lote.
* O **Batch mode** permite selecionar a melhor oferta para um conjunto de contatos. As regras de elegibilidade/priorização são aplicadas a todos os contatos do conjunto. Esse modo geralmente é usado para interações de saída.
* O **Modo Unitário** permite processar um único contato de cada vez. Esse modo geralmente é usado para mensagens transacionais.
* **As** ofertas elegíveis atendem às restrições definidas upstream que podem ser oferecidas de forma consistente a um target.
* **As** regras de apresentação são regras de tipologia mencionadas no ambiente de oferta, que permitem excluir algumas ofertas levando em conta o histórico de apresentações.
* **** Fórmulas de ponderação que permitem calcular precisamente a relevância de uma oferta para selecionar a mais relevante. Os pesos são definidos nas ofertas. Ofertas elegíveis são consideradas em ordem decrescente de peso.
* **A** função de renderização é definida no espaço de oferta para construir sua representação de oferta com base nos atributos definidos na oferta. Há três modos diferentes de função de renderização: HTML, XML e texto.
* **A** apresentação de oferta é o resultado da ação que consiste em apresentar uma ou várias ofertas a um contato em um determinado espaço (banner em um site, email ou SMS, por exemplo). Esse resultado é armazenado na tabela de apresentações de oferta. No entanto, não é obrigatório salvar as apresentações.
* **** Simulação é um módulo que permite testar a apresentação de ofertas nos recipients alvos antes de realmente enviar as ofertas.
* O **Preview** da oferta mostra a oferta como ela é exibida em sua pasta. É acessível a partir da janela de configurações de oferta ou do perfil de contato.
* **Os** filtros predefinidos são regras de filtragem que podem considerar os parâmetros de oferta (por exemplo, um código de oferta). Eles podem ser reutilizados após a criação de ofertas.
* Uma **Representação da oferta** é uma informação usada pelo canal para exibir a oferta. A representação da oferta pode ser construída a partir da função de renderização do espaço em que a oferta é representada ou inserida diretamente na interface (por exemplo, no bloco HTML). Uma oferta pode ser representada por espaço.

## Introdução a ofertas

As principais etapas para iniciar estão listadas abaixo.

### Configurar sua plataforma

Antes de começar, como um **Administrador** do Campaign, certifique-se de executar as seguintes tarefas em ambientes de design:

1. Crie perfis de usuário. [Saiba mais](interaction-operators.md).
1. (opcional) Crie um ambiente de oferta para cada targeting dimension. [Saiba mais](interaction-env.md)
1. Crie regras de tipologia para cada ambiente. [Saiba mais](interaction-offer.md#offer-presentation).
1. Crie espaços de ofertas para cada ambiente e configure as funções de renderização. [Saiba mais](interaction-offer-spaces.md).
Se o espaço for definido por um canal unitário no modo identificado, você deverá especificar os parâmetros avançados para esse espaço.

### Criar e publicar o catálogo de ofertas {#managing-the-offer-catalog-}

Como um **Offer manager**, você precisa executar as seguintes tarefas:

1. Crie categorias de ofertas em ambientes de design. [Saiba mais](interaction-offer-catalog.md#creating-offer-categories).
1. Crie ofertas em ambientes de design. [Saiba mais](interaction-offer.md).
1. Aprove e publique ofertas em um ou vários espaços para torná-las disponíveis em ambientes dinâmicos para o gerenciador de delivery. [Saiba mais](interaction-offer.md#approve-offers).

### Aproveite o catálogo de ofertas {#using-the-offer-catalog-}

Como **Delivery manager**, você precisa executar as seguintes tarefas:

1. Crie uma campanha.
1. Faça referência a uma oferta na campanha ou no delivery. [Saiba mais](interaction-send-offers.md).

