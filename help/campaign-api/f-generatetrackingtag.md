---
source-git-commit: ffa29306eb4402ed20c7d04bdbbaffd4dde5bfe4
workflow-type: tm+mt
source-wordcount: '145'
ht-degree: 3%
---
# generateTrackingTag

Gera automaticamente uma tag do JavaScript para rastreamento web.

```text
generateTrackingTag (request [, tagid ] [, folder ])
```

## Parâmetros

**solicitar** o objeto HttpServletRequest

**tagid** Uma cadeia de caracteres que representa o nome da tagid personalizada. Se estiver vazio, a função gerará a tag com base no nome do caminho.

**pasta** Uma cadeia de caracteres que representa o nome interno de uma pasta. Se estiver vazia, a tag é criada no diretório padrão, ou seja, &quot;Tags de rastreamento web&quot;.

## Valor de retorno

Uma string de caracteres que contém o código JavaScript a ser incluído.

## Observações

A tag gerada é baseada no nome do aplicativo da Web, página html, controlador ou, de uma forma mais geral, no nome do caminho, se a tagid não for inserida. O último parâmetro especifica a pasta de destino da tag. Para chamar a função, passe o objeto de solicitação como um argumento. Observe o uso de &lt;%== já que a função gera código html. Exemplo:

```xml
              <%== generateTrackingTag(request, request.getParameter('art'), request.getParameter('cat')) %>
```

## Recursos

**Disponível em:**

* JSSP
* WebApp
