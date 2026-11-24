---
source-git-commit: ffa29306eb4402ed20c7d04bdbbaffd4dde5bfe4
workflow-type: tm+mt
source-wordcount: '51'
ht-degree: 25%
---
# sha1

Calcula a assinatura SHA-1 do conteúdo do MemoryBuffer.

```text
sha1 ()
```

## Parâmetros

Nenhum.

## Valor de retorno

Uma string de caracteres que é a representação hexadecimal da assinatura SHA-1.

## Observações

Exemplo:

```javascript
var memBuf = new MemoryBuffer();
memBuf.fromString("Hello world", "utf-8");
logInfo(memBuf.sha1()); // Writes down  => 7b502c3a1f48c8609ae212cdfb639dee39673f5e
```

## Recursos

**Método de classe:** [MemoryBuffer](c-memorybuffer.md)

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
