---
source-git-commit: ffa29306eb4402ed20c7d04bdbbaffd4dde5bfe4
workflow-type: tm+mt
source-wordcount: '58'
ht-degree: 22%
---
# getImageUrl

Habilita a geração do URL de acesso do recurso público

```text
getImageUrl (ID|internal name)
```

## Parâmetros

**ID\|nome interno** ID do recurso público ou nome interno do recurso.

## Valor de retorno

Retorna o URL de acesso do recurso público.

## Observações

Os recursos devem ser publicados em servidores frontais. Exemplo:

```xml
              <%= getImageUrl(content.@["banner-id"]) %>Code HTML généré :http://media.adobe.com/res/img/18cd386d9e8b7f35f3477ac6a9efd762.jpg
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
