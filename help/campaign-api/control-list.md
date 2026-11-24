---
source-git-commit: ffa29306eb4402ed20c7d04bdbbaffd4dde5bfe4
workflow-type: tm+mt
source-wordcount: '143'
ht-degree: 1%
---
# Lista

Lista de memória.

## Propriedades

**backColor - cadeia de caracteres** Cor de fundo (btnshadow, branco).

**borda - cadeia de caracteres** Altera o estilo de estrutura de tópicos de controle (sólido, duplo, margem interna, início, nenhum).

**editável - booleano** Autoriza a edição da lista.

**tamanho da fonte - inteiro** Altera o tamanho da fonte.

**formulário - cadeia de caracteres** O formulário de edição.

**img - cadeia de caracteres** Imagem para cada linha.

**rótulo - cadeia de caracteres** Rótulo associado.

**nolabel - booleano** Sem rótulo.

**notitle - booleano** Não exibe títulos de coluna.

**noToolbar - booleano** Oculta a barra de ferramentas.

**ordenado - booleano** Autoriza o agendamento da lista.

**readOnly - booleano** Força o controle a ser somente leitura.

**barra de ferramentasAlinhar - cadeia de caracteres** horizontal \| vertical.

**toolbarCaption - string** Rótulo exibido na barra de ferramentas.

**zoom - booleano** Exibe o formulário de edição.

**zoomOnAdd - booleano** Abre um formulário quando uma linha é adicionada.

**xpathIndex - xpath** O índice da seleção será armazenado no local especificado por esse caminho.

**xpathSelection - xpath** O nó onde o caminho XPATH será armazenado para atingir o elemento selecionado.

## Observações

Exemplo 1:

```xml
      <input type="list" xpath="dataTransferStep" nolabel="true" editable="false"
       zoom="true" form="xtk:exportSource" zoomOnAdd="true" img="xtk:script.bmp">
  <input xpath="@name" colSize="15"/>
  <input xpath="@active" editable="true" colSize="15"/>
</input>
```

Exemplo 2:

```xml
<input type="list" xpath="operator" zoom="true">
  <input xpath="@name" colSize="15"/>
  <form>
    <input xpath="@name"/>
  </form>
</input>
```
