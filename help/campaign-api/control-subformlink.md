---
source-git-commit: ffa29306eb4402ed20c7d04bdbbaffd4dde5bfe4
workflow-type: tm+mt
source-wordcount: '96'
ht-degree: 2%
---
# SubFormLink

Link que abre um subformulário.

![Controle de SubFormLink](assets/urlbutton.d1cf6f42.png)

## Propriedades

**backColor - cadeia de caracteres** Cor de fundo (btnshadow, branco).

**borda - cadeia de caracteres** Altera o estilo de estrutura de tópicos de controle (sólido, duplo, margem interna, início, nenhum).

**discardReadOnly - string** Impede a propagação da propriedade &quot;somente leitura&quot; para o subformulário.

**tamanho da fonte - inteiro** Altera o tamanho da fonte.

**img - cadeia de caracteres** Imagem associada.

**rótulo - cadeia de caracteres** Rótulo do botão.

**nolabel - string** Permite alinhar o controle com a coluna de rótulo.

**prebuildSubForm - string** Inicializa o subformulário ao criar o controle. Essa opção é ativada por padrão, mas pode ser desativada para acelerar a exibição inicial.

## Observações

Exemplo:

```xml
      <input type="subformlink" label="Advanced parameters...">
  <form label=" Advanced parameters">
    <input xpath="@stopIfTooManyRejects"/>
    <input xpath="@traceMode"/>
  </form>
</input>
```
