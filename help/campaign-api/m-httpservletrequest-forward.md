---
source-git-commit: ffa29306eb4402ed20c7d04bdbbaffd4dde5bfe4
workflow-type: tm+mt
source-wordcount: '75'
ht-degree: 5%
---
# avançar

Redireciona o query para outra página sem passar pelo cliente.

```text
forward (location)
```

## Parâmetros

**local** A URL de redirecionamento.

## Valor de retorno

Nenhum.

## Observações

forward permite realizar um processo preliminar antes de transferir o query para outro recurso que produzirá o conteúdo da resposta. Nenhum dado deve ter sido retornado ao cliente como uma resposta antes de uma chamada de encaminhamento, caso contrário, um erro será gerado.

## Recursos

**Método de classe:** [HttpServletRequest](c-httpservletrequest.md)

**Disponível em:**

* JSSP
* WebApp
