---
source-git-commit: ffa29306eb4402ed20c7d04bdbbaffd4dde5bfe4
workflow-type: tm+mt
source-wordcount: '96'
ht-degree: 3%
---
# Bloco de notas

Lista de guias para exibir várias páginas.

![Controle de bloco de anotações](assets/notebook.3b531a46.png)

## Propriedades

**backColor - cadeia de caracteres** Cor de fundo (btnshadow, branco).

**nome - cadeia de caracteres** ID do Contêiner.

**preenchimento-esquerda - inteiro** Espaço em pixel à esquerda do contêiner.

**preenchimento à direita - inteiro** Espaço em pixel à direita do contêiner.

**padding-top - inteiro** Espaço em pixel acima do contêiner.

**margin-bottom - inteiro** Espaço em pixels abaixo do contêiner.

**preenchimento - inteiro** Espaço em pixel ao redor do contêiner.

**readOnly - booleano** Força o controle e todos os seus descendentes a somente leitura.

**style - string** flat \| down \| up (padrão).

## Observações

Cada subelemento representa uma página. Exemplos:

```xml
      <container colspan="2" style="down" type="notebook">
   <container label="Products">
     ...
   </container>

   <container colcount="3" xpath="link">
     ...
   </container>

   <container xpath="linkCollection">
     ...
   </container>
 </container>
```
