---
source-git-commit: ffa29306eb4402ed20c7d04bdbbaffd4dde5bfe4
workflow-type: tm+mt
source-wordcount: '137'
ht-degree: 13%
---
# parseTimeStamp

Converte uma cadeia de caracteres contendo uma data formulada com base em uma versão simplificada do padrão ISO 8601 em um objeto de tipo Date.

```text
parseTimeStamp (aString)
```

## Parâmetros

**aString** A data como uma cadeia de caracteres no formato ISO 8601.

## Valor de retorno

Um objeto de tipo Date que corresponde à data definida como um parâmetro.

## Observações

A sintaxe é a seguinte:

```javascript
              date
              time[time-zone]
            
```

ou

```javascript
              dateTtime[time-zone]
            
```

A data deve ter o seguinte formato:

```javascript
YYYY-MM-DD
```

Por motivos de compatibilidade, o seguinte formato também é aceito:

```javascript
YYYY/MM/DD
```

A hora deve ter o seguinte formato:

```javascript
hh:mm:ss
hh:mm:ss.nnn
```

O fuso horário, se especificado, deve ter o seguinte formato:

```javascript
Z
+hh:mm
-hh:mm
+hh
-hh
```

Se o fuso horário não for especificado, a data será convertida no fuso horário atual (dependendo do contexto). Exemplos:

```javascript
2005-03-02 00:00:00
2005-03-02
2005-03-02T14:32:26
2005-03-02T14:32:26.0000
2005-03-02T14:32:26.0000000+01:00
2005-03-02T14:32:26+01:00
2005-03-02T14:32:26Z
2005-03-02T14:32:26.0005Z
2005/03/02 14:32:25
```

Se o formato de data não for válido, uma exceção será gerada.

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
