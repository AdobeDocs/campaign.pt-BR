---
source-git-commit: ffa29306eb4402ed20c7d04bdbbaffd4dde5bfe4
workflow-type: tm+mt
source-wordcount: '219'
ht-degree: 0%
---
# LinkEdit

Controle para editar links.

![Controle LinkEdit](assets/linkedit.7cb7bf14.png)

## Propriedades

**backColor - cadeia de caracteres** Cor de fundo (btnshadow, branco).

**borda - cadeia de caracteres** Altera o estilo de estrutura de tópicos de controle (sólido, duplo, margem interna, início, nenhum).

**choiceButton - booleano** Oculta ou mostra o botão de opção (oculto por padrão).

**computeStringExpr - string** Expressão de campo calculado.

**computestringKey - string** Atualiza a cadeia de caracteres calculada em vez da chave externa.

**computeStringAlias - cadeia de caracteres** Alias de cadeia de caracteres calculada.

**createMode - cadeia de caracteres** Cria o link se ele não existir (nenhum, incorporado), com o modo de edição padrão.

**externalKey - booleano** usa a chave externa.

**tamanho da fonte - inteiro** Altera o tamanho da fonte.

**formulário - cadeia de caracteres** Força o formulário de edição de link.

**rótulo - cadeia de caracteres** Rótulo associado.

**loadEntityOnChange - booleano** Recarrega a entidade quando o link muda.

**obrigatório - booleano** Nega valores vazios.

**noAutoComplete - booleano** Desabilita o modo de preenchimento automático.

**noEdition - booleano** O link não pode ser modificado.

**nolabel - booleano** oculta o rótulo associado.

**notifyPathList - cadeia de caracteres** Lista de XPaths separados dos elementos vinculados por vírgulas, para carregar no contexto.

**noTransaction - booleano** Desabilita o modo transacional.

**noZoom - booleano** Sem formulário de edição de link.

**orderBy - elemento** Agendamento de opções.

**readOnly - booleano** Força o controle a ser somente leitura.

**obrigatório - booleano** O campo é obrigatório.

**esquema - cadeia de caracteres** Esquema do link.

**serializar - booleano** Salva a última seleção na configuração do usuário.

**sysFilter - element** Limitação de opções.

**xpathMandatory - cadeia de caracteres** Caminho para uma propriedade booleana que indica se o link pode ou não estar vazio.

## Observações

Exemplos:

```xml
<input xpath="operator">
  <sysFilter>
    <condition expr="@type= 1/>
  </sysFilter>
  <orderBy>
    <node expr="@name"/>
  </orderBy>
</input>

<input xpath="/tmp/recipient" type="linkEdit" label="Recipient"
       schema="nms:recipient">
```
