---
source-git-commit: ffa29306eb4402ed20c7d04bdbbaffd4dde5bfe4
workflow-type: tm+mt
source-wordcount: '87'
ht-degree: 2%
---
# LinkListChoice

Escolha de uma ou mais entidades.

## Propriedades

**backColor - cadeia de caracteres** Cor de fundo (btnshadow, branco).

**borda - cadeia de caracteres** Altera o estilo de estrutura de tópicos de controle (sólido, duplo, margem interna, início, nenhum).

**dblClickAction - cadeia de caracteres** Nome do formulário a ser aberto ao clicar duas vezes.

**tamanho da fonte - inteiro** Altera o tamanho da fonte.

**rótulo - cadeia de caracteres** Rótulo associado.

**multiSelection - booleano** Autoriza seleção múltipla

**nolabel - booleano** oculta o rótulo associado.

**readOnly - booleano** Força o controle a ser somente leitura.

**serializar - booleano** Salva a última seleção no arquivo configuration.wu do usuário

**xpath-link - cadeia de caracteres** Link da lista.

## Observações

Exemplos:

```xml
      <input xpath="." type="linkListChoice" xpath-link="operator">
  <input xpath="[/]"  label="Operator or named right "/>
  <input xpath="@type"/>
  <input xpath="comment"/>
  <sysFilter>
    <condition expr="@type <> 1"/>
  </sysFilter>
  <orderBy>
    <node expr="@type"/>
  </orderBy>
</input>
```
