---
source-git-commit: ffa29306eb4402ed20c7d04bdbbaffd4dde5bfe4
workflow-type: tm+mt
source-wordcount: '119'
ht-degree: 9%
---
# HttpClientResponse (Classe)

Um objeto que representa a resposta a uma consulta HTTP.

Só pode ser obtido após a execução de uma consulta HTTP pela propriedade `response`.

## Propriedades

| Propriedade | Descrição |
| --- | --- |
| [corpo](p-httpclientresponse-body.md) | O corpo da resposta HTTP na forma de um objeto MemoryBuffer. |
| [código](p-httpclientresponse-code.md) | O código de retorno da resposta HTTP na forma de um inteiro JavaScript. |
| [codePage](p-httpclientresponse-codepage.md) | O valor de codePage da resposta. Usado para decodificar o corpo da resposta HTTP. |
| [cabeçalho](p-httpclientresponse-header.md) | Um objeto que contém todos os cabeçalhos HTTP. |
| [cabeçalhos](p-httpclientresponse-headers.md) | A lista de cabeçalhos da resposta HTTP agrupados por nome. |
| [mensagem](p-httpclientresponse-message.md) | A mensagem transportada pela resposta HTTP. |

## Recursos

**Disponível em:**

* Gerenciamento de conteúdo
* Propriedades de entrega
* Regra de tipologia
* JSSP
* Método SOAP
* WebApp
* Fluxo de trabalho
