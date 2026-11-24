---
source-git-commit: ffa29306eb4402ed20c7d04bdbbaffd4dde5bfe4
workflow-type: tm+mt
source-wordcount: '238'
ht-degree: 3%
---
# HttpServletRequest (Classe)

Representa a consulta de um cliente encaminhada a um servlet.

Há apenas uma instância desse endereço acessível por meio de `request`. variável.

## Métodos

| Método | Descrição |
| --- | --- |
| [getHeader](m-httpservletrequest-getheader.md) | Retorna um atributo definido no cabeçalho da consulta. |
| [getParameter](m-httpservletrequest-getparameter.md) | Retorna o valor de um parâmetro de consulta. |
| [getRemoteAddr](m-httpservletrequest-getremoteaddr.md) | Retorna o endereço IP do cliente ou o último proxy que enviou uma solicitação. |
| [getUTF8Parameter](m-httpservletrequest-getutf8parameter.md) | Retorna o valor (codificado em UTF-8) de um parâmetro da consulta. |
| [getBodyAsString](m-httpservletrequest-getbodyasstring.md) | Retorna o corpo da consulta na forma de uma cadeia de caracteres usando a codificação de consulta. |
| [avançar](m-httpservletrequest-forward.md) | Redireciona o query para outra página sem passar pelo cliente. |

## Propriedades

| Propriedade | Descrição |
| --- | --- |
| [parâmetros](p-httpservletrequest-parameters.md) | Retorna os parâmetros de consulta. |
| [cookies](p-httpservletrequest-cookies.md) | Retorna os cookies da query. |
| [requestURI](p-httpservletrequest-requesturi.md) | Retorna o URL da consulta. |
| [queryString](p-httpservletrequest-querystring.md) | Retorna a parte do URL da consulta que corresponde aos parâmetros. |
| [esquema](p-httpservletrequest-scheme.md) | Retorna o nome do protocolo usado (HTTP, HTTPS etc.) para acessar esta página. |
| [serverName](p-httpservletrequest-servername.md) | Retorna o nome do servidor de consulta. |
| [portaServidor](p-httpservletrequest-serverport.md) | Retorna o número da porta usada para contatar o servidor. |
| [URLdoServidor](p-httpservletrequest-serverurl.md) | Retorna o URL para acessar o servidor. |
| [servletPath](p-httpservletrequest-servletpath.md) | Retorna a seção do URL da consulta que corresponde ao servlet. |
| [contextPath](p-httpservletrequest-contextpath.md) | Retorna a seção do URL da consulta que corresponde ao contexto. |
| [pathInfo](p-httpservletrequest-pathinfo.md) | Retorna as informações adicionais do URL da consulta. |
| [método](p-httpservletrequest-method.md) | Retorna uma string de caracteres contendo o método HTTP usado para chamar essa consulta (GET, HEAD, POST etc.). |

## Recursos

**Disponível em:**

* JSSP
* WebApp
