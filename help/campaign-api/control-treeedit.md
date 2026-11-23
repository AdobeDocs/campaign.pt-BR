---
source-git-commit: ffa29306eb4402ed20c7d04bdbbaffd4dde5bfe4
workflow-type: tm+mt
source-wordcount: '151'
ht-degree: 1%
---
# TreeEdit

Controle para exibir e editar vários valores agrupados em várias categorias.

![Controle de TreeEdit](assets/treeedit.253f1374.png)

## Propriedades

**backColor - cadeia de caracteres** Cor de fundo (btnshadow, branco).

**borda - cadeia de caracteres** Altera o estilo de estrutura de tópicos de controle (sólido, duplo, margem interna, início, nenhum).

**editável - cadeia de caracteres** Autoriza a modificação (verdadeiro por padrão).

**tamanho da fonte - inteiro** Altera o tamanho da fonte.

**rótulo - cadeia de caracteres** Rótulo associado.

**noImage - string** Oculta as imagens dos elementos na lista.

**nolabel - booleano** oculta o rótulo associado.

**readOnly - booleano** Força o controle a ser somente leitura.

## Observações

Propriedades dos subelementos

* visibleIf: uma condição XTK para exibir ou ocultar o elemento.
* label: rótulo do elemento.
* exprLabel: rótulo do elemento no formulário de uma expressão.
* xpath: XPath do elemento.
* img: imagem do elemento.

Propriedades dos subelementos de entrada

* editável: valor editável. O valor padrão é herdado do elemento raiz.

Propriedades dos subelementos do container

* recolhido: true\|false Exibe ou oculta subelementos.

Exemplo:

```xml
<input nolabel="true" type="treeEdit">
  <container label="Text fields">
    <input xpath="@text1"/>
    <input xpath="@text2"/>
    <input xpath="@text3"/>
    <input xpath="@text4"/>
    <input xpath="@text5"/>
  </container>
  <container label="Boolean fields">
    <input xpath="@boolean1"/>
    <input xpath="@boolean2"/>
    <input xpath="@boolean3"/>
  </container>
</input>
    
```
