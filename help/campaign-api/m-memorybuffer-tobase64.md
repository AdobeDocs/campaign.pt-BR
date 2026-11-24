---
source-git-commit: ffa29306eb4402ed20c7d04bdbbaffd4dde5bfe4
workflow-type: tm+mt
source-wordcount: '85'
ht-degree: 14%
---
# toBase64

Converte o buffer ou parte da cadeia de caracteres codificada na base 64.

```text
toBase64 ( [start ] [, length ])
```

## Parâmetros

**start** Número de bytes a serem ignorados no início do buffer. O primeiro byte corresponde ao valor 0 (valor padrão).

**length** Número de bytes a serem convertidos. Por padrão, todos os bytes restantes são considerados.

## Valor de retorno

O conteúdo do buffer codificado na base 64.

## Recursos

**Método de classe:** [MemoryBuffer](c-memorybuffer.md)

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
