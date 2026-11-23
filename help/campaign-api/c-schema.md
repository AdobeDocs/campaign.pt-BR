---
source-git-commit: ffa29306eb4402ed20c7d04bdbbaffd4dde5bfe4
workflow-type: tm+mt
source-wordcount: '173'
ht-degree: 8%
---
# Esquema (Classe)

Representa a definição do esquema.

Um esquema é obtido chamando-se o método da variável global `application`. Uma instância desse objeto tem um objeto como um protótipo e, portanto, herda seus métodos.

## Métodos

| Método | Descrição |
| --- | --- |
| [paraDocumento](m-schema-todocument.md) | Converte o esquema em um formulário de documento XML. |

## Propriedades

| Propriedade | Descrição |
| --- | --- |
| [enumerações](p-schema-enumerations.md) | Retorna a tabela que contém a lista de [enumerações](c-enumeration.md) definidas neste esquema. |
| [id](p-schema-id.md) | O identificador do esquema no formato de uma sequência. |
| [isLibrary](p-schema-islibrary.md) | Retorna um booliano que especifica se o esquema é uma biblioteca de componentes. |
| [labelSingular](p-schema-labelsingular.md) | O nome no singular do esquema na forma de uma cadeia de caracteres. |
| [mappingType](p-schema-mappingtype.md) | A natureza do mapeamento de esquema na forma de uma cadeia de caracteres |
| [md5](p-schema-md5.md) | O código MD5 do esquema na forma de uma cadeia de caracteres hexadecimal. |
| [namespace](p-schema-namespace.md) | Namespace do esquema na forma de uma sequência. |
| [raiz](p-schema-root.md) | Elemento principal do esquema ou nulo se não estiver definido. |
| [userDescription](p-schema-userdescription.md) | A descrição do esquema no formato de uma cadeia de caracteres. |

## Recursos

**Disponível em:**

* Gerenciamento de conteúdo
* Propriedades de entrega
* Regra de tipologia
* JSSP
* Método SOAP
* WebApp
* Fluxo de trabalho
