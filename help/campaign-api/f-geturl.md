---
source-git-commit: ffa29306eb4402ed20c7d04bdbbaffd4dde5bfe4
workflow-type: tm+mt
source-wordcount: '109'
ht-degree: 11%
---
# getUrl

Recupera um conteúdo de texto de um URL.

```text
getUrl (url [, timeout ])
```

## Parâmetros

**url** O endereço da página a ser recuperada.

**tempo limite** Tempo limite da conexão. Se a conexão não puder ser estabelecida dentro do atraso determinado, um erro será gerado e o script será interrompido.

## Valor de retorno

Uma cadeia de caracteres que contém a página de texto.

## Observações

A codificação da string retornada é a codificação especificada pela resposta (Content-Type). Se ocorrer um erro durante o download ou se o código de retorno for diferente de 200 (OK), um erro será gerado e o script que está sendo executado será interrompido. Exemplo:

```javascript
      var content = getUrl("http://www.google.com/index.html")
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
