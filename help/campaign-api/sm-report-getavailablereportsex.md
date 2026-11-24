---
source-git-commit: ffa29306eb4402ed20c7d04bdbbaffd4dde5bfe4
workflow-type: tm+mt
source-wordcount: '79'
ht-degree: 25%
---
# GetAvailableReportsEx

Recupera a lista de relatórios sem seu histórico, levando em conta as condições de classificação de dados e a numeração de páginas

```text
XML reports = GetAvailableReportsEx ( String activeContext, String schema, String selection, XML where, XML orderBy, Number editionMode, Number lineCount, Number startLine, String locationName )
```

## Parâmetros

**ativeContext** Contexto ativo (seleção, global)

**Esquema** envolvido

**seleção** IDs das entidades selecionadas, separadas por &#39;,&#39;

**onde** Filtrando o nó &#39;onde&#39;

**orderBy** Classificando nó &#39;orderBy&#39;

**editionMode** Durante a edição, os relatórios não publicados também ficam visíveis

**lineCount** Número de relatórios a coletar

**startLine** Deslocamento a ser aplicado à numeração de páginas

**locationName**

## Retornar valor(es)

**relatórios** Lista de relatórios qualificados

## Recursos

**Esquema:** [xtk:report](s-xtk-report.md)

**Estático:**

Sim
