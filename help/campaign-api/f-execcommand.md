---
source-git-commit: ffa29306eb4402ed20c7d04bdbbaffd4dde5bfe4
workflow-type: tm+mt
source-wordcount: '199'
ht-degree: 5%
---
# execCommand

> Aviso: essa função está disponível para um ambiente no local.

Executa um comando e captura o código de erro e a saída padrão.

```text
execCommand (command [, bNoThrow ])
```

## Parâmetros

**comando** O comando a ser executado com seus parâmetros.

**bNoThrow** true para obter a saída e o código de erro mesmo se o comando não retornar zero (false por padrão).

## Valor de retorno

Retorna uma tabela cujo primeiro elemento corresponde ao código de retorno do comando (se o código de retorno for diferente de zero, haverá uma anomalia) e o segundo elemento é uma cadeia de caracteres que contém a saída padrão produzida.

## Observações

Sem a opção bNothrow, uma exceção será gerada se o comando não puder ser executado ou se o comando for executado com um erro. Se bNoThrow for igual a true, uma exceção será gerada somente se o comando não puder ser executado. O operador precisa de direitos &#39;createProcess&#39; para usar esta função, caso contrário, uma exceção será gerada. Dependendo da sua instalação, alguns comandos podem estar na lista de bloqueios. Por exemplo: ln, dd, openssl, curl, wget, python, python3, perl, ruby, sh, bash, dash, zsh, base64, nlserver, node, phantomjs, java, awk, nc, telnet, ssh, scp, ftp.

## Exemplo

```text
var result = execCommand('gpg-exec.sh gpg --no-tty --yes -r CampaignOperations@adobe.com --encrypt "file_to_encrypt"', true);
```

## Recursos

**Disponível em:**

* Gerenciamento de conteúdo
* Propriedades de entrega
* Regra de tipologia
* JSSP
* Método SOAP
* WebApp
* Fluxo de trabalho
