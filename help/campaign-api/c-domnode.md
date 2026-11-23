---
source-git-commit: ffa29306eb4402ed20c7d04bdbbaffd4dde5bfe4
workflow-type: tm+mt
source-wordcount: '296'
ht-degree: 5%
---
# DOMNode (Classe)

DOMNode é a classe principal de diferentes componentes que compõem um documento.

## Métodos

| Método | Descrição |
| --- | --- |
| [inserirAntes](m-domnode-insertbefore.md) | Inserir um nó antes de uma posição específica. |
| [replaceChild](m-domnode-replacechild.md) | Substituir um nó. |
| [removeChild](m-domnode-removechild.md) | Excluir um nó. |
| [appendChild](m-domnode-appendchild.md) | Insira um nó no final da lista de subpastas. |
| [hasChildNodes](m-domnode-haschildnodes.md) | Testa se o nó tem pelo menos uma subpasta. |
| [normalizar](m-domnode-normalize.md) | Normaliza o nó: os nós de texto adjacentes são mesclados e os nós de texto vazios são excluídos. |
| [hasAttributes](m-domnode-hasattributes.md) | Testa se o nó tem pelo menos um atributo. |
| [isSameNode](m-domnode-issamenode.md) | Testa se a referência fornecida representa o mesmo nó. |
| [isDefaultNamespace](m-domnode-isdefaultnamespace.md) | Testa se o namespace fornecido é o padrão. |
| [lookupNamespaceURI](m-domnode-lookupnamespaceuri.md) | Pesquisado o URI do namespace vinculado ao prefixo fornecido. |
| [isEqualNode](m-domnode-isequalnode.md) | Compara dois nós. |

## Propriedades

| Propriedade | Descrição |
| --- | --- |
| [nodeName](p-domnode-nodename.md) | Nome do nó qualificado. O nome depende do tipo de nó. |
| [nodeValue](p-domnode-nodevalue.md) | Valor do nó. O valor depende do tipo de nó. |
| [nodeType](p-domnode-nodetype.md) | Tipo de nó. |
| [parentNode](p-domnode-parentnode.md) | Nó principal ou nulo. |
| [nósFilhos](p-domnode-childnodes.md) | Retorna a lista de nós filhos na forma de uma tabela. |
| [firstChild](p-domnode-firstchild.md) | Primeiro nó filho deste nó ou nulo se não tiver filhos. |
| [lastChild](p-domnode-lastchild.md) | Último nó filho deste nó ou nulo se ele não tiver filhos. |
| [próximoIrmão](p-domnode-nextsibling.md) | Nó após este nó ou nulo. |
| [irmão](p-domnode-previoussibling.md) | O nó que precifica imediatamente esse nó ou nulo. |
| [atributos](p-domnode-attributes.md) | Retorna uma tabela contendo a lista de atributos se o nó for um elemento, caso contrário, será nulo. |
| [URIdoNamespace](p-domnode-namespaceuri.md) | URI do namespace do nó. |
| [prefixo](p-domnode-prefix.md) | O prefixo do namespace deste nó ou vazio, se não especificado. |
| [localName](p-domnode-localname.md) | Parte local do nome qualificado do nó. |
| [baseURI](p-domnode-baseuri.md) | URI base deste nó. |
| [textContent](p-domnode-textcontent.md) | Conteúdo de texto do nó. O valor depende do tipo de nó. |
| [ownerDocument](p-domnode-ownerdocument.md) | O documento ao qual este nó pertence. |

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
