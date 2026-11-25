---
product: campaign
title: Definir o layout de formulários web
description: Definir o layout de formulários web
feature: Web Forms
version: Campaign v8, Campaign Classic v7
exl-id: 23ca17f8-de1a-4f9c-8357-3965dc3329b1
TQID: 'https://experienceleague.adobe.com/-0PZWl-79Q-MXZ-jHjp-VF12IUPeMcq27aGSgWl5Ans'
product_v2:
  - id: dfc56824-e8b9-499e-85d4-21aedb507314
    internal-label: Campaign
  - id: d0e9f0b2-1f2b-4134-9844-49cd4e950f27
    internal-label: Campaign v8
feature_v2:
  - id: a4671286-a59f-47e3-b97b-90627a1977d5
    internal-label: Communication channels
subfeature_v2:
  - id: f391046b-0cf3-4e76-bd3b-97fe06654506
    internal-label: Web Apps
  - id: ed29abcd-b6a8-4d4b-ab8b-b7e746973281
    internal-label: Web Forms
  - id: d7be2b01-dc9c-40f7-aace-a151707504ed
    internal-label: Landing pages
source-git-commit: d3b34546c1b08190772154efe6f818b98cc1094c
workflow-type: tm+mt
source-wordcount: '703'
ht-degree: 71%
---
# Definir o layout de formulários web{#defining-web-forms-layout}



## Criação de containers {#creating-containers}

Os containers permitem combinar os campos de uma página, configurar seu layout e organizar os elementos na página.

Para cada página do formulário, os são criados por meio do botão **[!UICONTROL Containers]** Containers da barra de ferramentas.

![Editor de páginas de formulários web com o botão Contêineres da barra de ferramentas aberto, oferecendo a opção Contêiner padrão](assets/s_ncs_admin_survey_containers_add.png)

Use um container para agrupar elementos da página sem adicionar um rótulo à renderização final. Os elementos são agrupados na subárvore container. Os containers padrão permitem gerenciar o layout.

Por exemplo:

![Propriedades da página com uma árvore de dois contêineres, Informações gerais e Seus contratos, e seus campos de formulário](assets/s_ncs_admin_survey_containers_std_arbo.png)

A posição dos rótulos é aplicada aos elementos posicionados abaixo do container na hierarquia. Ela pode ser sobrecarregada para cada elemento, se necessário. Adicionar ou remover colunas para alterar o layout. Consulte [Posicionamento dos campos na página](#positioning-the-fields-on-the-page).

No exemplo acima, a renderização será a seguinte:

![Página de formulário renderizada com dois contêineres: campos de detalhes pessoais e uma lista de caixas de seleção de contrato, além de um botão Validar](assets/s_ncs_admin_survey_containers_std_ex.png)

## Posicionamento dos campos na página {#positioning-the-fields-on-the-page}

O layout do formulário web é definido pela página em cada container e pode ser sobrecarregado se necessário.

As páginas são divididas em colunas: cada página contém determinado número de colunas. Cada campo da página ocupa **n** células. Os containers também ocupam um certo número de colunas e os campos que eles contêm ocupam um certo número de células.

Por padrão, as páginas são criadas em uma única coluna e cada elemento ocupa uma célula. Isso significa que os campos são exibidos um embaixo do outro e cada um ocupa uma linha inteira, como mostrado abaixo:

![Página de formulário de coluna única renderizada com campos de Sexo, Nome, Nome e Email empilhados em linhas separadas](assets/s_ncs_admin_survey_container_ex.png)

No exemplo a seguir, a configuração padrão foi mantida. A página ocupa uma única coluna que inclui quatro containers.

![Propriedades da página com quatro contêineres e Número de colunas definido como 1 realçado](assets/s_ncs_admin_survey_container_ex0.png)

Cada container ocupa uma coluna e cada elemento ocupa uma célula:

![Propriedades do elemento de informações com Número de células definido como 1 realçado nas Configurações de exibição](assets/s_ncs_admin_survey_container_ex0a.png)

A renderização é a seguinte:

![Renderização de página de coluna única com quatro contêineres, cada um com uma coluna, empilhada verticalmente](assets/s_ncs_admin_survey_container_ex0_rend.png)

Você pode adaptar os parâmetros de exibição para obter a seguinte renderização:

![Renderização da página de duas colunas, onde os contêineres 1 e 3 preenchem a coluna da esquerda e os contêineres 2 e 4, à direita](assets/s_ncs_admin_survey_container_ex1_rend.png)

No exemplo de renderização acima, cada campo de entrada, título e imagem ocupa uma célula nas colunas dos containers.

Você pode modificar a formatação em cada container. No nosso exemplo, você pode distribuir o conteúdo do container 4 em duas colunas e distribuir os elementos.

![Contêiner 4 com duas colunas: título e caixa de combinação ocupam uma célula cada, a caixa de seleção abrange duas células](assets/s_ncs_admin_survey_container_ex2_rend.png)

O título e a lista ocupam uma célula cada (e, portanto, uma linha inteira do container) e a caixa de seleção se estende por duas células. O número de células atribuídas ao campo de entrada é definido na guia **[!UICONTROL General]** ou na guia **[!UICONTROL Advanced]**, de acordo com o tipo de campo:

![Guia Avançado do elemento da caixa de seleção com Número de células definido como 2 em Configurações de exibição](assets/s_ncs_admin_survey_container_ex2.png)

## Definição da posição dos rótulos {#defining-the-position-of-labels}

Você pode definir o alinhamento dos campos e rótulos no formulário.

Por padrão, os parâmetros de exibição para campos e outros conteúdos da página são herdados da configuração geral do formulário, da configuração da página ou da configuração do container primário, se existir.

Os parâmetros de exibição global para todo o formulário são especificados na caixa de propriedades do formulário. A guia **[!UICONTROL Rendering]** permite selecionar a posição dos rótulos.

![Caixa de diálogo Propriedades do formulário Web, guia Renderização, com a lista Posição do rótulo: Herdado, Esquerdo, Direito, Acima, Abaixo, Oculto](assets/s_ncs_admin_survey_label_position.png)

Essa posição pode ser sobrecarregada para cada página, cada container e cada campo, por meio da guia **[!UICONTROL Advanced]**.

Os seguintes alinhamentos são suportados:

* Herdado: o alinhamento é herdado do elemento primário (valor padrão), ou seja, o container primário, se houver, ou a página,
* Esquerda/Direita: o rótulo é posicionado à direita ou à esquerda do campo,
* Acima/Abaixo: o rótulo está posicionado acima ou abaixo do campo,
* Oculto: o rótulo não é exibido.
