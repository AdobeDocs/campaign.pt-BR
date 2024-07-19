---
product: campaign
title: Práticas recomendadas de interação com o Adobe Campaign
description: Abordagem de práticas recomendadas para gerenciar o módulo de interação no Adobe Campaign
feature: Interaction, Offers
role: User, Admin
exl-id: 28f3a5bc-67f5-413e-b2ba-35c341f9ec5f
source-git-commit: 1a0b473b005449be7c846225e75a227f6d877c88
workflow-type: tm+mt
source-wordcount: '1166'
ht-degree: 67%

---

# Práticas recomendadas de interação {#interaction-best-practices}

## Recomendações gerais {#general-recommendations}

O gerenciamento de ofertas no Adobe Campaign requer um gerenciamento cuidadoso para operar com eficiência. Para evitar problemas, é necessário encontrar um equilíbrio entre o número de contatos e o número de ofertas e categorias de ofertas.

Esta seção apresenta as práticas recomendadas para gerenciar o módulo **Interação** no Adobe Campaign, incluindo regras de qualificação, filtros predefinidos, atividades de fluxo de trabalho e opções de banco de dados.

* Ao **implementar e configurar interações**, você deve estar ciente das seguintes recomendações:

   * Para o motor em lote (normalmente usado em comunicações de saída como email), a taxa de transferência é a principal preocupação, pois vários contatos podem ser manipulados ao mesmo tempo. O afunilamento típico é o desempenho do banco de dados.
   * A restrição principal do motor unitário (normalmente usado em comunicações de entrada como um banner em um site) é latência, pois alguém espera uma resposta. O afunilamento típico é o desempenho da CPU.
   * O design do catálogo de ofertas tem um enorme impacto no desempenho do Adobe Campaign.
   * Ao trabalhar com muitas ofertas, a prática recomendada é dividi-las em vários catálogos de ofertas.

* Abaixo estão listadas algumas práticas recomendadas para trabalhar com **regras de qualificação**:

   * Simplifique as regras. A complexidade das regras afeta o desempenho enquanto estende a pesquisa. Uma regra complexa é qualquer regra com mais de cinco condições.
   * Para aumentar o desempenho, as regras podem ser divididas em filtros predefinidos distintos que são compartilhados entre várias ofertas.
   * Coloque as regras de categoria de oferta mais restritivas na posição mais alta possível na árvore. Ao fazer isso, eles filtram a maioria dos contatos primeiro, reduzindo o número de target e evitando que sejam processados por regras adicionais.
   * Coloque as regras mais dispendiosas em termos de tempo ou processamento na parte inferior da árvore. Ao fazer isso, essas regras só serão executadas no público-alvo restante.
   * Comece em uma categoria específica para evitar a verificação da árvore inteira.
   * Para economizar tempo de processamento, os agregados pré-calculam em vez de criar regras complexas com junções. Para fazer isso, tente armazenar os dados do cliente em uma tabela de referência que possa ser pesquisada dentro de regras de elegibilidade.
   * Utilize um número mínimo de pesos para limitar o número de queries.
   * É recomendável ter um número limitado de ofertas por espaço de oferta. Isso garante uma recuperação mais rápida de ofertas em qualquer espaço.
   * Use índices, principalmente em colunas de pesquisa usadas com frequência.

* Abaixo estão listadas algumas práticas recomendadas relacionadas à **tabela de propostas**:

   * Use um número mínimo de regras para tornar o processamento mais rápido possível.
   * Limite o número de registros na tabela de apresentação: mantenha os registros necessários para rastrear sua atualização de status e o que é necessário para as regras, e arquive em outro sistema.
   * Realize a manutenção intensiva do banco de dados na tabela de apresentação, como índices de reconstrução ou recriação da tabela.
   * Limite o número de apresentações realizadas por target. Não defina mais do que você realmente vai usar.
   * Evite junções o máximo possível nos critérios da regra.

## Dicas ao gerenciar ofertas {#tips-managing-offers}

Esta seção contém recomendações mais detalhadas sobre como gerenciar ofertas e usar o módulo de interação no Adobe Campaign.

### Vários espaços de oferta em um email {#multiple-offer-spaces}

Ao incluir ofertas em deliveries, elas geralmente são selecionadas em upstream no fluxo de trabalho do Campaign por meio de uma atividade de fluxo de trabalho **Enriquecimento** (ou outra atividade semelhante).

Ao selecionar ofertas em uma atividade de **Enriquecimento**, você pode escolher qual espaço de ofertas usar. No entanto, independentemente do espaço de ofertas selecionado, o menu de personalização da entrega depende do espaço de ofertas configurado na entrega.

No exemplo abaixo, o espaço de ofertas selecionado na entrega é **[!UICONTROL Email (Environment - Recipient)]**:

![](assets/Interaction-best-practices-offer-space-selected.png)

Se o espaço de ofertas selecionado na entrega não tiver uma função de renderização HTML configurada, você não o verá no menu da entrega e ele não estará disponível para seleção. Isso é independente do espaço de ofertas selecionado na atividade **Enrichment**.

No exemplo abaixo, a função de renderização HTML está disponível na lista suspensa porque o espaço de ofertas selecionado na entrega tem uma função de renderização:

![](assets/Interaction-best-practices-HTML-rendering.png)

Essa função insere código como: `<%@ include proposition="targetData.proposition" view="rendering/html" %>`.

Quando você seleciona a proposta, o valor do atributo **[!UICONTROL view]** é o seguinte:
* &quot;rendering/html&quot;: html rendering. Ele usa a função de renderização HTML.
* &quot;offer/view/html&quot;: html content. Ela não usa a função de renderização HTML. Inclui apenas o campo HTML.

Ao incluir vários espaços de ofertas em uma única entrega de email e se alguns deles tiverem funções de renderização e outros não, lembre-se de quais ofertas usam quais espaços e quais espaços de ofertas têm funções de renderização.

Consequentemente, para evitar qualquer problema, recomenda-se que todos os espaços de ofertas tenham uma função de renderização HTML definida, mesmo se ele exigir apenas conteúdo HTML.

### Definir a classificação na tabela de log de propostas {#rank-proposition-log-table}

Os espaços de ofertas têm a capacidade de armazenar dados na tabela de propostas quando as proposições são geradas ou aceitas:

![](assets/Interaction-best-practices-offer-space-storage.png)

No entanto, isso se aplica somente às interações de entrada.

Também é possível armazenar dados adicionais na tabela de proposta ao usar interações de saída e ao usar ofertas de saída sem o módulo de interação.

Qualquer campo da tabela temporária do fluxo de trabalho cujo nome corresponda a um nome de campo na tabela de proposta é copiado para o mesmo campo na tabela de proposta.

Por exemplo, ao selecionar uma oferta manualmente (sem interação) em uma atividade de fluxo de trabalho **Enriquecimento**, os campos padrão são definidos da seguinte maneira:

![](assets/Interaction-best-practices-manual-offer-std-fields.png)

Campos adicionais podem ser adicionados, como um campo `@rank`:

![](assets/Interaction-best-practices-manual-offer-add-fields.png)

Como há um campo na tabela de proposta chamado `@rank`, o valor na tabela temporária do fluxo de trabalho será copiado.

Para obter mais informações sobre como armazenar campos adicionais na tabela de propostas, consulte [esta seção](interaction-send-offers.md#storing-offer-rankings-and-weights).

Para ofertas de saída com interação, isso é útil quando várias ofertas são selecionadas e você deseja gravar em qual ordem elas serão exibidas em um email.

Você também pode armazenar metadados adicionais diretamente na tabela de proposta, como o nível de gastos atual, para manter registros históricos sobre a utilização feita no momento em que as ofertas foram geradas.

Ao usar a interação de saída, o campo `@rank` pode ser adicionado, como no exemplo acima, mas seu valor é automaticamente definido com base na ordem retornada pela interação. Por exemplo, se estiver usando a interação para selecionar três ofertas, o campo `@rank` terá os valores 1, 2 e 3 retornados.

Ao usar a interação e selecionar ofertas manualmente, o usuário pode combinar ambas as abordagens. Por exemplo, o usuário pode definir manualmente o campo `@rank` como 1 para a oferta selecionada manualmente e usar uma expressão como `"1 + @rank"` para as ofertas retornadas pela interação. Supondo que a interação selecione três ofertas, as ofertas retornadas por ambas as abordagens serão classificadas de 1 a 4:

![](assets/Interaction-best-practices-manual-offer-combined.png)

### Estenda o schema nms:offer {#extending-nms-offer-schema}

Ao expandir o esquema nms:offer, siga a estrutura predefinida já configurada:
* Defina qualquer novo campo para armazenamento de conteúdo em `<element name="view">`.
* Cada novo campo precisa ser definido duas vezes. Uma vez como um campo XML regular e outra como um campo XML CDATA com &quot;_jst&quot; anexado ao nome. Por exemplo:

  ```
  <element label="Price" name="price" type="long" xml="true"/>
  <element advanced="true" label="Script price" name="price_jst" type="CDATA" xml="true"/>
  ```

* Todos os campos que contêm URLs a serem rastreados devem ser posicionados em `<element name="trackedUrls">`which is found under`<element name="view" >`.
