---
source-git-commit: ffa29306eb4402ed20c7d04bdbbaffd4dde5bfe4
workflow-type: tm+mt
source-wordcount: '45'
ht-degree: 20%
---
# upload

Baixe um arquivo de um arquivo local para um servidor FTP.

```text
upload (URL)
```

## Parâmetros

URL do Servidor **URL**.

## Valor de retorno

Nenhum.

## Observações

O URL deve começar com &#39;ftp:&#39; Exemplo:

```javascript
var ftp = new FTP
ftp.setFile("c:/rfc.txt")
ftp.upload("ftp://ftp.funet.fi/pub/standards/RFC")
```

## Recursos

**Método da classe:** [FTP](c-ftp.md)

**Disponível em:**

* Gerenciamento de conteúdo
* Propriedades de entrega
* Regra de tipologia
* JSSP
* Método SOAP
* WebApp
* Fluxo de trabalho
