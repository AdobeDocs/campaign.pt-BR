---
source-git-commit: ffa29306eb4402ed20c7d04bdbbaffd4dde5bfe4
workflow-type: tm+mt
source-wordcount: '64'
ht-degree: 20%
---
# generateImgTag

Permite a geração de uma tag HTML &lt;img> com base em um recurso público.

```text
generateImgTag (ID)
```

## Parâmetros

**ID** ID do recurso público

## Valor de retorno

Retorna a tag HTML &lt;img> com as propriedades da imagem contidas na definição de recurso público.

## Observações

Os recursos devem ser publicados em servidores frontais. Exemplo:

```xml
              <%= generateImgTag(content.@["banner-id"]) %>Code HTML généré :<img src="http://media.adobe.com/res/img/18cd386d9e8b7f35f3477ac6a9efd762.jpg" width="800" height="200" alt="My image"/>
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
