---
title: Introdução aos relatórios de análise do Adobe Campaign
description: Saiba como criar cubos
feature: Reporting
role: Developer
level: Beginner
exl-id: f57f3074-981f-4bcf-9274-7908cd00a4a2
TQID: 'https://experienceleague.adobe.com/rWE0PPnY4uRgpGy9a-cucZFSGnRyaI9IwwjJFmvYY9s'
product_v2:
  - id: dfc56824-e8b9-499e-85d4-21aedb507314
    internal-label: Campaign
  - id: d0e9f0b2-1f2b-4134-9844-49cd4e950f27
    internal-label: Campaign v8
feature_v2:
  - id: c309ee4e-82e4-4f7e-b608-ef345678c34e
    internal-label: Dynamic reporting
subfeature_v2:
  - id: b3a4149f-2b3a-44d1-894e-e3ac4c77fb47
    internal-label: Reporting interface
role_v2:
  - id: ff6a42d2-313e-452e-93a6-792e4fad9ff8
    internal-label: Developer
level_v2:
  - id: e8ccd51f-da0d-4e3b-939b-e30d5ebb1ea5
    internal-label: Beginner
topic_v2:
  - id: aa2f3246-cb95-4b30-8899-fdf7d73550cc
    internal-label: Reporting
source-git-commit: 7fd43a8d3d6afe9f4d3fb000d925cc6185ba9f40
workflow-type: tm+mt
source-wordcount: '529'
ht-degree: 76%
---
# Introdução aos relatórios de análise do Campaign {#gs-cube}

O Adobe Campaign vem com uma ferramenta intuitiva de exploração de dados para criar relatórios dinâmicos.

Use os recursos de análise de marketing para analisar e medir dados, calcular estatísticas, simplificar e otimizar a criação e o cálculo de relatórios. Você pode criar relatórios e populações de públicos-alvo e armazená-los em listas que podem ser usadas no Adobe Campaign para tarefas de direcionamento ou segmentação.

É possível ampliar o recursos de exploração e análise do banco de dados e, ao mesmo tempo, facilitar para os usuários finais a configuração de relatórios e tabelas: basta selecionar um cubo existente (totalmente configurado) ao criar os relatórios ou as tabelas para processar cálculos, medidas e estatísticas.

Os cubos são usados para gerar determinados relatórios internos, incluindo [relatórios do delivery](delivery-reports.md) (rastreamento de delivery, cliques, aberturas, etc.).

Depois que tiverem sido criados e configurados, os cubos serão usados em caixas de consulta de relatório e aplicação web. Eles podem ser utilizados e manipulados dentro de tabelas dinâmicas.

Use o módulo Marketing Analytics do Campaign para:

1. Criar cubos e indicadores

   * agregar e armazenar dados em uma tabela de trabalho para pré-calcular indicadores com base nas necessidades do usuário,
   * reduzir o volume de dados envolvidos nos vários cálculos usados para relatórios e consultas, otimizando significativamente os tempos de cálculo do indicador,
   * simplificar o acesso aos dados e permitir que os usuários manipulem dados (sejam pré-agregados ou não) que dependem de várias dimensões.

   Para obter mais informações, consulte [Criar indicadores](cube-indicators.md).

1. Criar tabelas dinâmicas e explorar dados

   * explorar dados calculados e medidas configuradas,
   * selecionar os dados a serem exibidos, bem como o seu modo de exibição,
   * personalizar as medidas e os indicadores usados,
   * e oferecer ferramentas de análise interativa a usuários sem conhecimento técnico.

   Para saber mais, consulte [Usar cubos para explorar dados](cube-tables.md).

1. Criar uma consulta usando dados calculados e agregados em um cubo.
1. Identificar populações e referenciá-las em listas.

## Terminologia {#terminology}

Os termos específicos do trabalho com cubos estão listados abaixo.

* **Cubo** - Um cubo é uma representação de informações multidimensionais: ele fornece estruturas projetadas para análise interativa de dados aos usuários finais.

* **Tabela/esquema de fatos** - A tabela de fatos (ou esquema de fatos) contém os dados brutos ou primários nos quais as análises serão baseadas. Trata-se principalmente de tabelas de grandes volumes (possivelmente com tabelas vinculadas) com cálculos potencialmente longos. Por exemplo, uma tabela de fatos pode ser: a tabela de broadlog, a tabela de compras, etc.

* **Dimensão** - As dimensões permitem segmentar dados em grupos: uma vez criadas, as dimensões atuam como eixos de análise. Na maioria dos casos, para determinada dimensão, vários níveis serão definidos. Por exemplo, para uma dimensão temporal, os níveis serão meses, dias, horas, minutos e etc. Esse conjunto de níveis representa a hierarquia de dimensão e permite vários níveis de análise de dados.

* **Compartimentalização** - Em alguns campos, é possível definir a compartimentalização para agrupar valores e facilitar a leitura das informações. A compartimentalização é aplicada aos níveis. Recomendamos que você defina a compartimentalização quando houver a possibilidade de muitos valores diferentes.

* **Medida** - As medidas mais comuns são soma, média, máximo, mínimo, desvio padrão etc. As medidas podem ser calculadas: por exemplo, a taxa de aceitação de uma oferta é a razão do número de vezes que foi apresentada em comparação ao número de vezes que foi aceita.
