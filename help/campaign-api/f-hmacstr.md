---
source-git-commit: ffa29306eb4402ed20c7d04bdbbaffd4dde5bfe4
workflow-type: tm+mt
source-wordcount: '200'
ht-degree: 6%
---
# hmacStr

Calcula o hash MD5, SHA-1 ou SHA-256 de uma cadeia de caracteres. A cadeia de caracteres é codificada automaticamente em UTF-8 antes do cálculo.

```text
hmacStr (string [, key ] [, algo ])
```

## Parâmetros

**cadeia** A cadeia de caracteres na qual o hash deve ser calculado.

Chave **key**, na forma de uma cadeia de caracteres. Ele é convertido automaticamente em UTF-8. Se a chave estiver ausente, o servidor usará uma chave que depende da instância e que é válida somente nessa instância.

**algo** Tipo de hash a ser usado. Os valores possíveis são &quot;MD5&quot;, &quot;SHA1&quot; ou &quot;SHA256&quot;. A capitalização é ignorada, portanto, os valores podem ser inseridos em minúsculas ou maiúsculas. O valor &quot;SHA1&quot; é selecionado por padrão, se nenhum parâmetro for especificado.

## Valor de retorno

O hash MD5, SHA-1 ou SHA-256 (dependendo do tipo de hash selecionado) da string transmitida como um parâmetro.

## Observações

Para os tipos MD5 e SHA-1, a chave pode ter até 64 caracteres (512 bits) após a conversão em UTF-8. Para o tipo SHA-256, a chave pode ter até 32 caracteres (256 bits) após a conversão em UTF-8.

## Recursos

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
