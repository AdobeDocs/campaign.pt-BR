---
source-git-commit: ffa29306eb4402ed20c7d04bdbbaffd4dde5bfe4
workflow-type: tm+mt
source-wordcount: '60'
ht-degree: 15%
---
# fileGetTempName

Gera um nome de arquivo temporário.

```text
fileGetTempName ( [directory ] [, prefix ] [, extension ])
```

## Parâmetros

**diretório** Diretório do arquivo temporário. Se estiver vazio, use o diretório temporário definido pelo sistema.

**Prefixo** Prefixo com no máximo 4 caracteres. Se estiver vazio, o prefixo tmp será usado.

Extensão de arquivo **extension**.

## Valor de retorno

Nome completo do arquivo.

## Recursos

**Disponível em:**

* Gerenciamento de conteúdo
* Propriedades de entrega
* Regra de tipologia
* JSSP
* Método SOAP
* WebApp
* Fluxo de trabalho
