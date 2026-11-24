---
source-git-commit: ffa29306eb4402ed20c7d04bdbbaffd4dde5bfe4
workflow-type: tm+mt
source-wordcount: '117'
ht-degree: 11%
---
# iniciar

Inicia uma consulta no modo assíncrono.

```text
start (context, name, ...)
```

## Parâmetros

**contexto** Qualquer parâmetro de usuário que será encaminhado para a função [complete](p-soapservice-complete.md).

**nome** Nome do método a ser chamado.

**...** Parâmetros de função.

## Valor de retorno

A consulta criada. Este objeto não tem propriedades ou funções. É útil para a função [wait](m-soapservice-wait.md) que permite aguardar até o fim de uma operação.

## Observações

A conexão de serviço deve ser assíncrona. Se a conexão estiver sendo bloqueada, uma exceção será gerada. As consultas não podem ser executadas se outra consulta estiver sendo executada na conexão. Nesse caso, uma exceção é gerada.

## Recursos

**Método de classe:** [SoapService](c-soapservice.md)

**Disponível em:**

* Gerenciamento de conteúdo
* Propriedades de entrega
* Mensagem de entrega
* Regra de tipologia
* Importação
* JSSP
* Método SOAP
* WebApp
* Fluxo de trabalho
