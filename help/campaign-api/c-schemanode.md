---
source-git-commit: ffa29306eb4402ed20c7d04bdbbaffd4dde5bfe4
workflow-type: tm+mt
source-wordcount: '944'
ht-degree: 1%
---
# SchemaNode (Classe)

Representa o elemento de um esquema

## Métodos

| Método | Descrição |
| --- | --- |
| [findNode](m-schemanode-findnode.md) | Retorna uma instância de [SchemaNode](c-schemanode.md) ou nulo se o nó não existir e o parâmetro mustExist estiver definido como falso. |

## Propriedades

| Propriedade | Descrição |
| --- | --- |
| [filhos](p-schemanode-children.md) | Retorna um objeto para o qual cada propriedade é um nó filho indexado por seu nome. |
| [computeString](p-schemanode-computestring.md) | Retorna a cadeia de caracteres calculada pelo nó atual. |
| [políticaDeDados](p-schemanode-datapolicy.md) | Retorna uma cadeia de caracteres que fornece a política de dados do nó atual. |
| [descrição](p-schemanode-description.md) | Retorna uma cadeia de caracteres que descreve o nó atual. |
| [valorPadrão](p-schemanode-defaultvalue.md) | Retorna uma cadeia de caracteres que fornece o valor padrão do nó atual. |
| [editType](p-schemanode-edittype.md) | Retorna uma cadeia de caracteres que especifica o tipo de edição do nó atual. |
| [enumeração](p-schemanode-enumeration.md) | Retorna um objeto [Enumeration](c-enumeration.md) que é a enumeração vinculada ao nó atual ou nulo se não houver enumeração. |
| [enumerationImage](p-schemanode-enumerationimage.md) | Retorna o nome da imagem do nó atual na forma de uma cadeia de caracteres. |
| [folderModel](p-schemanode-foldermodel.md) | Somente no nó raiz, retorna uma string que contém os modelos de pasta. Nos outros nós, retorna indefinido. |
| [imagem](p-schemanode-image.md) | Retorna o nome da imagem na forma de uma cadeia de caracteres. |
| [integridade](p-schemanode-integrity.md) | Retorna o tipo de integridade do link. |
| [chaves](p-schemanode-keys.md) | Retorna uma tabela com definições das chaves [SchemaKey](c-schemakey.md) do nó atual. |
| [hasEnumeration](p-schemanode-hasenumeration.md) | Retorna um booliano que indica se o valor do nó atual está vinculado a uma enumeração. |
| [childCount](p-schemanode-childrencount.md) | Retorna um número que especifica o número de nós filhos. |
| [hasSQLTable](p-schemanode-hassqltable.md) | Retorna um booleano que indica se o nó atual está vinculado a uma tabela SQL. |
| [hasUserEnumeration](p-schemanode-hasuserenumeration.md) | Retorna um booliano que indica se o valor do nó atual está vinculado a uma enumeração de usuário. |
| [ajuda](p-schemanode-help.md) | Retorna a cadeia de caracteres de ajuda. |
| [esquema](p-schemanode-schema.md) | Retorna a instância do objeto pai [Esquema](c-schema.md) deste nó. |
| [isAdvanced](p-schemanode-isadvanced.md) | Retorna um booleano que indica se o nó atual está avançado ou não. |
| [isAnyType](p-schemanode-isanytype.md) | Retorna um booleano que indica se o nó atual é ordinário. |
| [isAttribute](p-schemanode-isattribute.md) | Retorna um booleano que indica se o nó atual é um atributo. |
| [isAutoIncrement](p-schemanode-isautoincrement.md) | Retorna um booleano que indica se o valor do nó atual é incrementado automaticamente. |
| [isAutoPK](p-schemanode-isautopk.md) | Retorna um booleano que indica se o nó atual é uma chave primária. |
| [isBlob](p-schemanode-isblob.md) | Retorna um booleano que indica se o nó atual é um BLOB. |
| [isCalculated](p-schemanode-iscalculated.md) | Retorna um booleano que indica se o valor do nó atual é o resultado de um cálculo. |
| [isCDATA](p-schemanode-iscdata.md) | Retorna um booliano que indica se o nó atual é mapeado a partir do XML do tipo CDATA. |
| [isCollection](p-schemanode-iscollection.md) | Retorna um booleano que indica se o nó atual é uma coleção de subelementos e/ou atributos. |
| [isDefaultOnDuplicate](p-schemanode-isdefaultonduplicate.md) | Retorna um valor booleano. Se o valor adicionado for vrai, durante a desduplicação do registro, o valor padrão (definido em defaultValue) será reaplicado automaticamente durante a gravação. |
| [isElementOnly](p-schemanode-iselementonly.md) | Retorna um booleano que indica se o nó atual é uma subdivisão lógica do esquema. |
| [isExternalJoin](p-schemanode-isexternaljoin.md) | True se o nó for um link e se a associação for externa. |
| [isFeature](p-schemanode-isfeature.md) | Retorna um booleano que indica se o nó é um recurso. |
| [isLink](p-schemanode-islink.md) | Retorna um booleano que indica se o nó é um link. |
| [isMappedAsXML](p-schemanode-ismappedasxml.md) | Retorna um booleano que indica se o nó é um mapeamento XML. |
| [isMemo](p-schemanode-ismemo.md) | Retorna um booleano que indica se o nó atual está mapeado por um Memorando. |
| [isMemoData](p-schemanode-ismemodata.md) | Retorna um booleano que indica se o nó atual está mapeado por um MemoData. |
| [isNotNull](p-schemanode-isnotnull.md) | Retorna um booleano que indica se o nó atual pode ou não considerar o valor nulo. |
| [isRequired](p-schemanode-isrequired.md) | Retorna um booleano que indica se o valor do nó atual é obrigatório ou não. |
| [isRoot](p-schemanode-isroot.md) | Retorna um booleano que indica se o nó é a raiz do esquema. |
| [isSQL](p-schemanode-issql.md) | Retorna um booleano que indica se o nó atual está mapeado em SQL. |
| [isTemporaryTable](p-schemanode-istemporarytable.md) | Retorna um booleano indicando se a tabela é temporária. A tabela não será criada durante a criação do banco de dados. |
| [isUnbound](p-schemanode-isunbound.md) | Retorna um booleano que indica se o nó atual tem um número ilimitado de filhos do mesmo tipo. |
| [isUser](p-schemanode-isuser.md) | Retorna um booleano que indica se o nó é ou não do tipo usuário. |
| [joinParts](p-schemanode-joinparts.md) | Retorna uma tabela de instâncias de SchemaNode para as quais cada elemento representa uma condição da junção. |
| [rótulo](p-schemanode-label.md) | Retorna uma cadeia de caracteres que é a descrição do nó atual. |
| [nome](p-schemanode-name.md) | Retorna uma cadeia de caracteres que é o nome do nó atual. |
| [nodePath](p-schemanode-nodepath.md) | Retorna uma cadeia de caracteres que é o caminho absoluto do nó atual. |
| [pai](p-schemanode-parent.md) | Retorna um objeto [SchemaNode](c-schemanode.md) que é o objeto pai ou nulo, se não houver um. |
| [PKSequence](p-schemanode-pksequence.md) | Retorna uma cadeia de caracteres que fornece o nome da sequência a ser usada para a chave primária. |
| [statusDoPacote](p-schemanode-packagestatus.md) | Retorna um número que fornece o status do pacote. |
| [reverseLink](p-schemanode-reverselink.md) | Se o elemento for um link, retornará um objeto [SchemaNode](c-schemanode.md) que representa um link reverso (por meio do esquema de destino). Caso contrário, a propriedade não será definida. |
| [SQLName](p-schemanode-sqlname.md) | O nome SQL do campo. A propriedade é uma cadeia de caracteres vazia se o objeto não for um campo de tipo SQL. |
| [SQLTable](p-schemanode-sqltable.md) | O nome SQL da tabela. A propriedade é uma cadeia de caracteres vazia se o objeto não for o elemento principal ou se o mapeamento de esquema não for do tipo SQL. |
| [tamanho](p-schemanode-size.md) | O tamanho do tipo de cadeia de caracteres. |
| [tableDefinition](p-schemanode-tabledefinition.md) | Uma instância de um [SchemaNode](c-schemanode.md) que é a descrição da tabela que contém o nó atual, nula se não houver nenhum. |
| [destino](p-schemanode-target.md) | O elemento principal do schema do target do link. Se o objeto não for um link, a propriedade não será definida. |
| [tipo](p-schemanode-type.md) | Retorna uma cadeia de caracteres que fornece o tipo de valor do nó atual. |
| [userEnumeration](p-schemanode-userenumeration.md) | Retorna uma cadeia de caracteres que é o nome da enumeração de usuários usada pelo nó atual. |

## Recursos

**Disponível em:**

* Gerenciamento de conteúdo
* Propriedades de entrega
* Regra de tipologia
* JSSP
* Método SOAP
* WebApp
* Fluxo de trabalho
