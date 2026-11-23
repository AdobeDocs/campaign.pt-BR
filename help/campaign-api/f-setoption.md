---
source-git-commit: ffa29306eb4402ed20c7d04bdbbaffd4dde5bfe4
workflow-type: tm+mt
source-wordcount: '116'
ht-degree: 8%
---
# setOption

Altera o valor de uma opção na tabela de opções.

```text
setOption (name, value, description )
```

## Parâmetros

**nome** Nome da opção.

**value** Valor da opção.

**descrição** Valor da descrição (opcional).

## Valor de retorno

Nenhum.

## Observações

Os diferentes tipos de dados são:

* texto,
* inteiro,
* ponto flutuante,
* Data + hora,
* longtext

Observe que longText e o tipo inteiro não podem ser criados a partir da API.

Para esses dois tipos, primeiro é necessário criar a opção no console e depois gerenciar os valores por meio da API setOption.

**Exemplo:**

```javascript
               //create option of type Date+Time'
               var ourDate = getCurrentDate();
               setOption("testOptionDateTime",ourDate,"option of type Date+Time");
                              
               //create option of type Floating point'
               setOption("testOptionFloat",1,"option of type Floating point");
               
               //create option of type Text'
               setOption("testOptionText","I am a text","option of type Text");               
           
```

Se quiser excluir a descrição, será necessário chamar a API com uma descrição vazia (setOption(name,value,&quot;&quot;)).

## Recursos

**Disponível em:**

* Gerenciamento de conteúdo
* Propriedades de entrega
* Regra de tipologia
* JSSP
* Método SOAP
* WebApp
* Fluxo de trabalho
