---
source-git-commit: ffa29306eb4402ed20c7d04bdbbaffd4dde5bfe4
workflow-type: tm+mt
source-wordcount: '105'
ht-degree: 11%
---
# hmac

Calcula o hash MD5, SHA-1 ou SHA-256 do buffer.

```text
hmac (key [, algo ])
```

## Parâmetros

Chave **key**, na forma de buffer.

**algo** Tipo de hash a ser usado. Os valores possíveis são &quot;MD5&quot;, &quot;SHA1&quot; ou &quot;SHA256. Eles não diferenciam maiúsculas de minúsculas, portanto, os valores podem ser inseridos em minúsculas ou maiúsculas. Por padrão, o valor &quot;SHA1&quot; será selecionado se o parâmetro não for especificado.

## Valor de retorno

O hash MD5, SHA-1 ou SHA-256 (de acordo com o tipo de hash escolhido) do buffer.

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
