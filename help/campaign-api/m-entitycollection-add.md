---
source-git-commit: ffa29306eb4402ed20c7d04bdbbaffd4dde5bfe4
workflow-type: tm+mt
source-wordcount: '141'
ht-degree: 6%
---
# adicionar

Adiciona uma nova entidade à coleção.

```text
add ( [index ], xml)
```

## Parâmetros

**índice** A entidade será adicionada neste ponto de índice. Se esse argumento não for especificado, a entidade será anexada ao final da lista.

**xml** A entidade a ser inserida no formulário XML.

## Valor de retorno

O elemento criado.

## Observações

O exemplo a seguir mostra duas maneiras diferentes de adicionar um novo elemento a uma coleção. A primeira solução passa a definição completa do elemento para o método add(), enquanto o segundo passa e o elemento empty &lt;attachment/> atribui os atributos da maneira normal.

```javascript
var delivery = NLWS.nmsDelivery.load("12435")

delivery.attachment.add(
  {attachment: {
    compressMode: "print", filterActive: "false", label: "First File", 
    nameScriptActive: "false", type: "normal", upload: "false", 
    name: { $: "file1.txt" }
  }})

var attach = delivery.attachment.add()
attach.label            = "Second File"
attach.name             = "file2.txt"
attach.compressMode     = "print"
attach.type             = "normal"
attach.filterActive     = false
attach.nameScriptActive = false
attach.upload           = false

delivery.save()
```

As duas soluções são equivalentes, mas a segunda permite usar os tipos de JavaScript correspondentes aos tipos de atributo, enquanto a primeira aceita somente strings.

## Recursos

**Método de classe:** [EntityCollection](c-entitycollection.md)

**Disponível em:**

* Gerenciamento de conteúdo
* Propriedades de entrega
* Regra de tipologia
* JSSP
* Método SOAP
* WebApp
* Fluxo de trabalho
