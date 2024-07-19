---
title: Introdução aos relatórios de análise do Adobe Campaign
description: Saiba como criar cubos
feature: Reporting
role: Data Engineer
level: Beginner
exl-id: f57f3074-981f-4bcf-9274-7908cd00a4a2
source-git-commit: 77ec01aaba1e50676bed57f503a9e4e8bb1fe54c
workflow-type: tm+mt
source-wordcount: '525'
ht-degree: 76%

---

# Introdução aos relatórios de análise do Campaign {#gs-cube}

O Adobe Campaign vem com uma ferramenta intuitiva de exploração de dados para criar relatórios dinâmicos.

Use os recursos de análise de marketing para analisar e medir dados, calcular estatísticas, simplificar e otimizar a criação e o cálculo de relatórios. Você pode criar relatórios e populações de públicos-alvo e armazená-los em listas que podem ser usadas no Adobe Campaign para tarefas de direcionamento ou segmentação.

É possível ampliar o recursos de exploração e análise do banco de dados e, ao mesmo tempo, facilitar para os usuários finais a configuração de relatórios e tabelas: basta selecionar um cubo existente (totalmente configurado) ao criar os relatórios ou as tabelas para processar cálculos, medidas e estatísticas.

Os cubos são usados para gerar determinados relatórios internos, incluindo [relatórios do delivery](delivery-reports.md) (rastreamento de delivery, cliques, aberturas, etc.).

Depois que tiverem sido criados e configurados, os cubos serão usados em caixas de query de relatório e aplicação web. Eles podem ser utilizados e manipulados dentro de tabelas dinâmicas.

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

1. Criar um query usando dados calculados e agregados em um cubo.
1. Identificar populações e referenciá-las em listas.

## Terminologia {#terminology}

Os termos específicos do trabalho com cubos estão listados abaixo.

* **Cubo** - Um cubo é uma representação de informações multidimensionais: ele fornece estruturas projetadas para análise interativa de dados aos usuários finais.

* **Tabela/esquema de fatos** - A tabela de fatos (ou esquema de fatos) contém os dados brutos ou primários nos quais as análises serão baseadas. Trata-se principalmente de tabelas de grandes volumes (possivelmente com tabelas vinculadas) com cálculos potencialmente longos. Por exemplo, uma tabela de fatos pode ser: a tabela de broadlog, a tabela de compras, etc.

* **Dimensão** - As dimensões permitem segmentar dados em grupos: uma vez criadas, as dimensões atuam como eixos de análise. Na maioria dos casos, para determinada dimensão, vários níveis serão definidos. Por exemplo, para uma dimensão temporal, os níveis serão meses, dias, horas, minutos e etc. Esse conjunto de níveis representa a hierarquia de dimensão e permite vários níveis de análise de dados.

* **Compartimentalização** - Em alguns campos, é possível definir a compartimentalização para agrupar valores e facilitar a leitura das informações. A compartimentalização é aplicada aos níveis. Recomendamos que você defina a compartimentalização quando houver a possibilidade de muitos valores diferentes.

* **Medida** - As medidas mais frequentes são: soma, média, máximo, mínimo, desvio padrão, etc. As medidas podem ser calculadas: por exemplo, a taxa de aceitação de uma oferta é a razão do número de vezes que foi apresentada em comparação ao número de vezes que foi aceita.
