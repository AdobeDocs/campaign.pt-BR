---
product: campaign
title: Nota técnica - Criptografia e descriptografia assimétrica no Adobe Campaign
description: Nota técnica - Criptografia e descriptografia assimétrica no Adobe Campaign
hide: true
exl-id: 6ee8b05b-2a46-4adf-a036-82fdd4809d0d
source-git-commit: 6728fc8db6a6f8e401b782d6a17f4fa04876daa9
workflow-type: tm+mt
source-wordcount: '142'
ht-degree: 2%

---

# Nota técnica: Criptografia assimétrica e descriptografia no Adobe Campaign {#asymetric-encryption}

Criptografia de chave pública, ou criptografia assimétrica, é o campo dos sistemas criptográficos que usam pares de chaves relacionadas. Cada par de chaves consiste em uma **chave pública** e uma **chave privada** correspondente.

* A **chave pública** é compartilhada abertamente e usada para criptografar dados.

* A **chave privada** é mantida em segredo e usada para descriptografar dados.

Essa abordagem garante que, mesmo que alguém tenha a chave pública, não poderá descriptografar a mensagem sem a chave privada. Ele fornece recursos de segurança importantes, como confidencialidade, autenticação e integridade.

A partir do Adobe Campaign v8.8.3, duas novas funções JavaScript serão adicionadas para criptografia e descriptografia:

* Criptografia usando chave pública: `rsaPublicEncrypt(data, base64EncodedPublicKey, useOAEPpadding)`

* Descriptografia usando chave privada: `rsaPrivateDecrypt(encryptedData, base64EncodedPrivateKey, useOAEPpadding)`


Exemplo:

```Java
// Encryption with PKCS#1 v1.5 padding (default)
var encrypted = rsaPublicEncrypt(
    "Secret message",
    "LS0tLS1CRUdJTiBQVUJMSUMgS0VZLS0t..." // Base64 encoded public key
);
 
// Encryption with OAEP padding
var encryptedOAEP = rsaPublicEncrypt(
    "Secret message",
    "LS0tLS1CRUdJTiBQVUJMSUMgS0VZLS0t...", // Base64 encoded public key
    true
);
 
// Decryption
var decrypted = rsaPrivateDecrypt(
    encrypted,
    "LS0tLS1CRUdJTiBSU0EgUFJJVkFURSBLRVkt..." // Base64 encoded private key
);
```

**Recursos adicionais**

* [Introdução às [!DNL Campaign] APIs](https://experienceleague.adobe.com/pt-br/docs/campaign/campaign-v8/developer/api){target="_blank"}
* [Documentação JSAPI do Campaign](https://experienceleague.adobe.com/developer/campaign-api/api/p-1.html?lang=pt-BR){target="_blank"}
