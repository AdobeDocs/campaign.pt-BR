---
source-git-commit: 3319b56a62aa8a8364c7f2f85bc81708a66a5978
workflow-type: tm+mt
source-wordcount: '77'
ht-degree: 15%
---
# ofuscar

Ofusca um inteiro em uma sequência de caracteres. O valor original pode ser recuperado chamando [unobfuscate](f-unobfuscate.md).

```text
obfuscate (value [, size ] [, version ])
```

## Parâmetros

**value** O inteiro a ser ofuscado.

**size** O tamanho da cadeia de caracteres resultante da ofuscação. Um número inteiro entre 6 e 10. 6 por padrão.

**versão** A versão de ofuscação a ser aplicada. 0 por padrão.

## Valor de retorno

Uma sequência de caracteres que representa o inteiro ofuscado.

## Recursos

**Disponível em:**

* Gerenciamento de conteúdo
* Propriedades de entrega
* Mensagem de entrega
* Regra de tipologia
* Importação
* JSSP
* Método SOAP
* WebApp
* Fluxo de trabalho
