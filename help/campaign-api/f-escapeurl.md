---
source-git-commit: ffa29306eb4402ed20c7d04bdbbaffd4dde5bfe4
workflow-type: tm+mt
source-wordcount: '82'
ht-degree: 15%
---
# escapeUrl

Converte uma cadeia de caracteres para inseri-la em um URL.

```text
escapeUrl (value)
```

## Parâmetros

Cadeia de caracteres **value** a ser convertida.

## Valor de retorno

A sequência de caracteres após a conversão.

## Observações

A função transforma caracteres não alfanuméricos diferentes de $-\_.\!\*&#39;(),?/:@&amp;= no valor hexadecimal correspondente. A função está em conformidade com a especificação RFC1738 e permite apenas codificar caracteres ISO-latinos. Para codificar caracteres UTF-8, use a função de JavaScript encodeURIComponent(). Exemplo:

```javascript
escapeUrl("a#value!")               // "a%23value!"
escapeUrl("Système d'exploitation") // "Syst%E8me%20d'exploitation"
```

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
