---
source-git-commit: ffa29306eb4402ed20c7d04bdbbaffd4dde5bfe4
workflow-type: tm+mt
source-wordcount: '213'
ht-degree: 6%
---
# formatDate

Formata uma data como uma sequência de caracteres.

```text
formatDate (date, format [, timeZone ])
```

## Parâmetros

**data** A data a ser convertida.

**format** A cadeia de caracteres que descreve o formato a ser usado. Os caracteres usados para formatar as diferentes partes da data são os seguintes:

* Y - Ano
* M - Mês do ano (1-12)
* B - Nome do mês
* D - Dia do mês (1-31)
* A - Nome do dia
* J - Dia do ano (1-366)
* W - Semana do ano
* H - Hora (0-23)
* I - Hora (1-12)
* N - Minutos (0-59)
* S - Segundos (0-59)
* P - AM/PM

Você pode especificar um número na frente de alguns desses caracteres. Os caracteres A e B podem ser seguidos por um l para usar o nome completo em vez da versão reduzida ou um i para usar o nome em inglês. Exemplos:

* &quot;%4Y/%2M/%2D&quot; => 01/2000/24.
* &quot;%A %D %B %4Y&quot; => mês 24 de janeiro de 2000.
* &quot;%Al %D %Bl %4Y&quot; => Segunda-Feira, 24 De janeiro De 2000.
* &quot;%02H:%02N:%02S&quot; exibe a hora, os minutos e os segundos em dois números.

**timeZone** Cadeia de caracteres correspondente ao fuso horário. Os valores possíveis estão especificados no esquema de enumeração xtk:common:timezone.

## Valor de retorno

Uma cadeia de caracteres que representa a data no formato solicitado.

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
