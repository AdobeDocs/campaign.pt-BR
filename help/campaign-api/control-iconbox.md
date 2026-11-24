---
source-git-commit: ffa29306eb4402ed20c7d04bdbbaffd4dde5bfe4
workflow-type: tm+mt
source-wordcount: '92'
ht-degree: 3%
---
# Caixa de ícones

Lista de ícones que permitem a seleção de várias páginas.

![Controle de Iconbox](assets/iconbox.05daa4bf.png)

## Propriedades

**backColor - cadeia de caracteres** Cor de fundo (btnshadow, branco).

**nome - cadeia de caracteres** ID do Contêiner.

**preenchimento-esquerda - inteiro** Espaço em pixel à esquerda do contêiner.

**preenchimento à direita - inteiro** Espaço em pixel à direita do contêiner.

**padding-top - inteiro** Espaço em pixel acima do contêiner.

**margin-bottom - inteiro** Espaço em pixels abaixo do contêiner.

**preenchimento - inteiro** Espaço em pixel ao redor do contêiner.

**readOnly - booleano** Força o controle e todos os seus descendentes a somente leitura.

## Observações

Cada subelemento container representa uma página. Exemplo:

```xml
<container name="iconbox" type="iconbox">
   <container colcount="3" label="Header">
     ...
   </container>
   <container img="ncm:ctprop.bmp" label="Intro">
     ...
   </container>
   <container img="ncm:subsection.bmp" label="Event">
     ...
   </container>
   <container img="ncm:book.bmp" label="Selection">
     ...
   </container>
   <container img="nms:contacts.bmp" label="Services">
     ...
   </container>
   <container img="nms:contacts.bmp" label="Mail footer ">
     ...
   </container>
 </container>
```
