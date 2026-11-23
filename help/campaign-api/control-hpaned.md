---
source-git-commit: ffa29306eb4402ed20c7d04bdbbaffd4dde5bfe4
workflow-type: tm+mt
source-wordcount: '109'
ht-degree: 1%
---
# HPaned

Organiza vários contêineres verticalmente.

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

Cada subelemento deve ser um container. Cada um de seus subcontêineres pode especificar a porcentagem da altura total que deseja usar graças à propriedade height-percent. Exemplo:

```xml
<container type="hpaned">
  <container label="Group 1" height-percent="25"/>
    <input .../>
  </container>
  <container label="Group 2" height-percent="75"/>
    <input .../>
  </container>
</container>
```
