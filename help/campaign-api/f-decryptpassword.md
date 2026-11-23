---
source-git-commit: ffa29306eb4402ed20c7d04bdbbaffd4dde5bfe4
workflow-type: tm+mt
source-wordcount: '80'
ht-degree: 5%
---
# decryptPassword

> Aviso:
>
> Esta documentação foi atualizada. Para obter mais detalhes, consulte esta [página](https://experienceleague.adobe.com/en/docs/campaign-classic/using/technotes/gcm-functions#decryptpassword-headding-anchor-decryptpassword-javascript).

Descriptografa uma senha armazenada em uma conta externa.

```text
decryptPassword (str)
```

## Parâmetros

**str** A cadeia de caracteres criptografada.

## Valor de retorno

Retorna a senha de texto simples.

## Observações

Esta função não pode ser chamada em workflows, aplicativos web, relatórios ou deliveries. Ele pode ser chamado em implementações de chamada JSSP ou SOAP. Exemplo:

```javascript
          function nms_extAccount_LogonToRemoteInstance(remoteInstanceUrl, login, encryptedPassword) {
          var cnx = null, sessionService = null;
          try
              {
                  var cnx = new HttpSoapConnection(remoteInstanceUrl + '/nl/jsp/soaprouter.jsp', 'utf-8', 0);
                  sessionService = new SoapService(cnx, 'xtk:session');
                  sessionService.addMethod("Logon", "xtk:session#Logon",
                      ["token", "string", "login", "string", "password", "string", "parameters", "NLElement"],
                      ["sessionToken", "string", "sessionInfo", "NLElement", "securityToken", "string"]);
                  return sessionService.Logon("", login, decryptPassword(encryptedPassword), <parameters/>);
              }
          catch( e ) {
          logError(e);
          }
          finally {
          if( sessionService ) sessionService.dispose();
          if( cnx ) cnx.dispose();
          }
          })
      
```

## Recursos

**Disponível em:**

* Método SOAP
