---
source-git-commit: ffa29306eb4402ed20c7d04bdbbaffd4dde5bfe4
workflow-type: tm+mt
source-wordcount: '119'
ht-degree: 3%
---
# CodeEdit

Controle para editar o código-fonte.

![Controle CodeEdit](assets/codeedit.8a744c8b.png)

## Propriedades

**backColor - cadeia de caracteres** Cor de fundo (btnshadow, branco).

**borda - cadeia de caracteres** Altera o estilo de estrutura de tópicos de controle (sólido, duplo, margem interna, início, nenhum).

**contentType - cadeia de caracteres** Idioma do código-fonte, usado para cor sintaxe e outras opções vinculadas ao idioma. Os seguintes idiomas são suportados:

* padrão
* xml
* dtd
* xsl
* html
* txt
* JavaScript
* sq

Outros idiomas também podem ser adicionados editando o arquivo editor.cfg localizado no mesmo diretório que nlclient.exe.

**tamanho da fonte - inteiro** Altera o tamanho da fonte.

**rótulo - cadeia de caracteres** Rótulo associado.

**nolabel - booleano** oculta o rótulo associado.

**readOnly - booleano** Força o controle a ser somente leitura.

**barra de ferramentas - booleano** Exibe ou oculta a barra de ferramentas.

**toolbarAlign - string** Posição da barra de ferramentas: horizontal ou vertical.

## Observações

Exemplo:

```xml
<input xpath="code" nolabel="true" type="CodeEdit"
       contentType="JavaScript" toolbar="true" toolbarAlign="horizontal"/>
```
