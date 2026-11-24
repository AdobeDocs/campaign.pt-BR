---
source-git-commit: ffa29306eb4402ed20c7d04bdbbaffd4dde5bfe4
workflow-type: tm+mt
source-wordcount: '199'
ht-degree: 1%
---
# LinkList

Controle para editar coleções.

![Controle de LinkList](assets/linklist.8b71bb0e.png)

## Propriedades

**addButton - booleano** Exibe o botão adicionar. Essa opção só terá efeito se a opção hideEditButtons estiver habilitada.

**backColor - cadeia de caracteres** Cor de fundo (btnshadow, branco).

**borda - cadeia de caracteres** Altera o estilo de estrutura de tópicos de controle (sólido, duplo, margem interna, início, nenhum).

**dblClickAction - cadeia de caracteres** Nome do formulário a ser aberto ao clicar duas vezes.

**delButton - booleano** Exibe o botão Excluir. Essa opção só terá efeito se o botão hideEditButtons estiver habilitado.

**enumImage - cadeia de caracteres** Nome da enumeração do sistema usada para exibir a imagem de cada linha.

**tamanho da fonte - inteiro** Altera o tamanho da fonte.

Formulário **formulário - sequência de caracteres** Formulário para edição de link.

**hideEditButtons - booleano** Oculta os botões adicionar, excluir e editar.

**img - Imagem da cadeia de caracteres**.

**rótulo - cadeia de caracteres** Rótulo associado.

**nolabel - booleano** Nenhum rótulo na frente do controle.

**noToolbar - booleano** Oculta a barra de ferramentas.

**orderBy - elemento** - Agendamento de lista.

**readOnly - booleano** Força o controle a ser somente leitura.

**sysFilter - elemento** Filtragem de lista.

**barra de ferramentasAlinhar - cadeia de caracteres** horizontal \| vertical.

**toolbarCaption - string** Rótulo exibido na barra de ferramentas.

**xpath-link - cadeia de caracteres** Link da lista (consulte o exemplo em grupos).

**xpathIndex - cadeia de caracteres** O índice de seleção será armazenado no local especificado por esse caminho.

**xpathLinkEdit - string** Link para edição (consulte o exemplo em grupos).

**zoom - booleano** Autoriza a edição de links.

## Observações

Exemplos:

```xml
      <input type="linkList" xpath="operator" enumImage="@type" nolabel="true">
  <input xpath="@name" label="Name" colSize="30"/>
  <input xpath="@login"/>
  <sysFilter>
    <condition expr="@type=1"/>
  </sysFilter>
</input>

<input type="linkList" xpath="operator" enumImage="@type" nolabel="true">
  <input xpath="@name" label="Name" colSize="30"/>
  <input xpath="@login"/>
  <form label="Add operators">
  <input xpath="." type="linkListChoice" xpath-link="recipient" img="nms:group.bmp">
  <input xpath="@lastName"/>
  <input xpath="@firstName"/>
  </input>
  </form>
</input>

<input type="linklist" xpath="rcpGrpRel" zoom="true" label="Recipients" form="nms:recipient"
       xpath-link="rcpGroup"
       xpathLinkEdit="recipient">
  <input xpath="recipient/@lastName"/>
  <input xpath="recipient/@firstName"/>
  <input xpath="recipient/@email"/>
  <input xpath="recipient/@phone"/>
</input>
```
