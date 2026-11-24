---
source-git-commit: ffa29306eb4402ed20c7d04bdbbaffd4dde5bfe4
workflow-type: tm+mt
source-wordcount: '76'
ht-degree: 2%
---
# RadioButton

Um botão de opção permite escolher entre várias opções. As tags &lt;input> são usadas para enumerar possíveis opções.

![Controle de RadioButton](assets/radio.11bc90a8.png)

## Propriedades

**backColor - cadeia de caracteres** Cor de fundo (btnshadow, branco).

**borda - cadeia de caracteres** Altera o estilo de borda do controle (sólido, duplo, margem interna, início, nenhum).

**checkedValue - cadeia de caracteres** Valor vinculado à escolha.

**tamanho da fonte - inteiro** Altera o tamanho da fonte.

**rótulo - cadeia de caracteres** Rótulo associado.

**nolabel - booleano** oculta o rótulo associado.

**readOnly - booleano** Força o controle a ser somente leitura.

## Observações

Exemplo:

```xml
      <input type="RadioButton" xpath="@gender" checkedValue="0" label="Choice 1"/>
<input type="RadioButton" xpath="@gender" checkedValue="1" label="Choice 2"/>
<input type="RadioButton" xpath="@gender" checkedValue="2" label="Choice 3"/>
```
