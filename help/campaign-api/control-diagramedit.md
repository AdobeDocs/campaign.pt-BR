---
source-git-commit: ffa29306eb4402ed20c7d04bdbbaffd4dde5bfe4
workflow-type: tm+mt
source-wordcount: '88'
ht-degree: 1%
---
# EditarDiagrama

Esse controle é usado para editar diagramas como fluxos de trabalho ou pesquisas.

![Controle de EdiçãoDeDiagrama](assets/diagramedit.d750db7e.png)

## Propriedades

**backColor - cadeia de caracteres** Cor de fundo (btnshadow, branco).

**borda - cadeia de caracteres** Altera o estilo de estrutura de tópicos de controle (sólido, duplo, margem interna, início, nenhum).

**rótulo - cadeia de caracteres** Rótulo associado.

**nolabel - booleano** Exibe o rótulo como uma bolha de ajuda.

**readOnly - booleano** Força o controle a ser somente leitura.

## Observações

A barra de ferramentas pode ser personalizada, cada subelemento desse controle corresponde a botões adicionais na barra de ferramentas.

```xml
<input type="diagramEdit" xpath=".">
  <input type="separator"/>
  <input img="xtk:properties.png" label="Properties" resetForm="true" prebuildSubForm="true">
    <form name="properties" label="Properties">
      <input xpath="/tmp/@test"/>
    </form>
  </input>
  <input type="separator"/>
  <input img="nms:prepare.png" label="Publish" checkModify="true">
    <form name="properties" label="Properties">
      <input xpath="/tmp/@test"/>
    </form>
  </input>
</input>
```

Para obter mais informações sobre os botões na barra de ferramentas, consulte a documentação do controle SubFormButton.
