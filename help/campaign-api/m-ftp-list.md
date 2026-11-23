---
source-git-commit: ffa29306eb4402ed20c7d04bdbbaffd4dde5bfe4
workflow-type: tm+mt
source-wordcount: '99'
ht-degree: 10%
---
# lista

Retorna a lista de arquivos no servidor em um diretório especificado.

```text
list (URL, pattern [, max ])
```

## Parâmetros

**URL** Endereço do servidor FTP como uma URL.

**pattern** Arquivo e máscara da lista de arquivos a serem recuperados.

**max** Número máximo de arquivos para retornar. Se esse parâmetro estiver ausente, o método retornará a lista completa de arquivos.

## Valor de retorno

Uma tabela que contém os nomes de arquivo correspondentes ao caminho e à máscara especificados.

## Observações

Se o comando FTP falhar e a exceção for gerada. Exemplo:

```javascript
var ftp = new FTP
var files = ftp.list("ftp://ftp.funet.fi/", "pub/standards/RFC/rfc*.txt", 10)
for(var i in files)
  logInfo(files[i])
ftp.dispose()
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
