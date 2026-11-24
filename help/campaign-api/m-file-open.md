---
source-git-commit: ffa29306eb4402ed20c7d04bdbbaffd4dde5bfe4
workflow-type: tm+mt
source-wordcount: '151'
ht-degree: 5%
---
# open

Abre o arquivo no modo de leitura ou gravação.

```text
open ( [mode ] [, codepage ])
```

## Parâmetros

**modo** Modo de abertura de arquivo. O modo pode ser um de vários valores:

* &quot;r&quot; - Abre o arquivo no modo somente leitura. Esse é o modo padrão.
* &quot;w&quot; - Abre o arquivo no modo de gravação.
* &quot;a&quot; - Abre o arquivo no modo &#39;append&#39;; os dados gravados no arquivo são anexados ao final.

**página de código** A codificação do arquivo. A codificação pode ser um dos seguintes valores:

* File.CODEPAGE\_CURRENT - Essa é a página de código padrão.
* Arquivo.CODEPAGE\_OEM
* Arquivo.CODEPAGE\_MAC
* Arquivo.CODEPAGE\_THREAD
* Arquivo.PÁGINA.CÓDIGO\_LATINO1
* Arquivo.PÁGINA.CÓDIGO\_LATINO2
* Arquivo.PÁGINA.CÓDIGO\_ISOLAMENTO1
* Arquivo.PÁGINA.CÓDIGO\_ISOLAMENTO2
* Arquivo.PÁGINA.CÓDIGO\_OEMLATIN1
* Arquivo.PÁGINA.CÓDIGO\_OEMLATIN2
* Arquivo.CODEPAGE\_UTF7
* Arquivo.CODEPAGE\_UTF8
* Arquivo.PÁGINA.CÓDIGO\_ISOLAMENTO9
* Arquivo.CODEPAGE\_OEMUS
* File.CODEPAGE\_SHIFTJIS
* Arquivo.CODEPAGE\_BIG5
* Arquivo.CODEPAGE\_CHINÊS
* File.CODEPAGE\_EUCKOREAN
* Arquivo.CODEPAGE\_UTF16LE
* Arquivo.CODEPAGE\_UTF16BE

## Valor de retorno

Nenhum.

## Observações

Se o arquivo não puder ser aberto, uma exceção será gerada.

## Recursos

**Método da classe:** [Arquivo](c-file.md)

**Disponível em:**

* Gerenciamento de conteúdo
* Propriedades de entrega
* Regra de tipologia
* JSSP
* Método SOAP
* WebApp
* Fluxo de trabalho
