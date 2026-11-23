---
source-git-commit: ffa29306eb4402ed20c7d04bdbbaffd4dde5bfe4
workflow-type: tm+mt
source-wordcount: '106'
ht-degree: 9%
---
# baixar

Faz o download de um arquivo do servidor para um arquivo local ou para a memória.

```text
download (URL [, append ])
```

## Parâmetros

URL **URL** do arquivo a ser baixado.

**anexar** Por padrão, se o arquivo baixado já existir no disco local, ele será substituído pelo novo arquivo recebido. Se o booleano estiver ativado, o Adobe Campaign gravará o conteúdo baixado no arquivo com o mesmo nome, juntamente com o conteúdo existente.

## Valor de retorno

Nenhum.

## Observações

Para recuperar o arquivo em um arquivo local, comece usando o método setFile. Exemplo:

```javascript
var ftp = new FTP
ftp.setFile("c:/rfc.txt")
ftp.download("ftp://ftp.funet.fi/pub/standards/RFC/rfc2068.txt")
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
