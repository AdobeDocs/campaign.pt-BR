---
source-git-commit: ffa29306eb4402ed20c7d04bdbbaffd4dde5bfe4
workflow-type: tm+mt
source-wordcount: '63'
ht-degree: 39%
---
# DeclareTableSpaces

Declara as opções, necessárias para usar tablespaces específicos no banco de dados remoto acessível por meio da conta externa, no banco de dados do Adobe Campaign.

```text
DeclareTableSpaces ( String extAccountId, String tableSpace, String tableSpaceIndex )
```

## Parâmetros

**extAccountId** Nome interno ou chave primária da conta externa

**tableSpace** Nome do tablespace a ser usado para tabelas de trabalho remoto

**tableSpaceIndex** Nome do tablespace a ser usado para índices

## Retornar valor(es)

Nenhum.

## Recursos

**Esquema:** [nms:extAccount](s-nms-extaccount.md)

**Estático:**

Sim
