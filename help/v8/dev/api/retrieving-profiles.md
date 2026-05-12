---
title: Recuperação de perfis
description: Saiba como recuperar perfis com APIs
role: Developer
level: Experienced
exl-id: 19679804-f728-49fa-b26e-8f31b67c29bf
TQID: https://experienceleague.adobe.com/pL6dAoJZ-Qb-aP2BWZKTxsYMTpQEM9EZoU3REWE0OoI
product_v2: id: dfc56824-e8b9-499e-85d4-21aedb507314
feature_v2: id: b12f6872-9271-4369-85e5-86969a0b99a2
role_v2: id: ff6a42d2-313e-452e-93a6-792e4fad9ff8
source-git-commit: 15d7b12d07f84356fac7bee2a54a0057c5d00d41
workflow-type: tm+mt
source-wordcount: 234
ht-degree: 4%

---

# Recuperação de perfis com APIs {#retrieving-profiles}

A recuperação de perfis é executada com uma solicitação **GET**.

Você pode refinar sua pesquisa usando filtros, ordenação e paginação. Para obter mais informações, consulte a seção [Operações adicionais](sorting.md).

Além disso, as APIs do Campaign Standard permitem procurar perfis com base em um destes campos: email, nome, sobrenome ou qualquer campo personalizado. Para obter mais informações, consulte [esta seção](#searching-field).

<br/>

***Solicitações de exemplo***

* Exemplo de solicitação do GET para recuperar todos os perfis.

  ```
  -X GET https://mc.adobe.io/<ORGANIZATION>/campaign/profileAndServices/profile \
  -H 'Content-Type: application/json' \
  -H 'Authorization: Bearer <ACCESS_TOKEN>' \
  -H 'Cache-Control: no-cache' \
  -H 'X-Api-Key: <API_KEY>'
  ```

  Resposta à solicitação.

  ```
  {
      "content": [
          {
              "PKey": "<PKEY>",
              "firstName": "John",
              "lastName":"Doe",
              "birthDate": "1980-10-24",
              ...
          },
          ...
  }
  ```

* Exemplo de solicitação do GET para recuperar os primeiros 10 valores de email.

  ```
  -X GET https://mc.adobe.io/<ORGANIZATION>/campaign/profileAndServices/profile/email?_lineCount=10 \
  -H 'Content-Type: application/json' \
  -H 'Authorization: Bearer <ACCESS_TOKEN>' \
  -H 'Cache-Control: no-cache' \
  -H 'X-Api-Key: <API_KEY>'
  ```

  Resposta à solicitação. O nó &quot;next&quot; retorna o URL que dá acesso aos 10 próximos valores de email.

  ```
  {
  "content": [
      "amy.dakota@mail.com",
      "kristen.smith@mail.com",
      "omalley@mail.com",
      "xander.harrys@mail.com",
      "jane.summer@mail.com",
      "gloria.boston@mail.com",
      "edward.snow@mail.com",
      "dorian.simons@mail.com",
      "peter.paolini@mail.com",
      "mingam+test08@adobe.com"
  ],
  "next": {
      "href": "https://mc.adobe.io/<ORGANIZATION>/campaign/profileAndServices/profile/email?_lineCount=10&_
      lineStart=@Qy2MRJCS67PFf8soTf4BzF7BXsq1Gbkp_e5lLj1TbE7HJKqc"
  }
  }
  ```

## Pesquisar perfis com base em um campo {#searching-field}

O parâmetro **[!UICONTROL filterType]** permite recuperar perfis com base em um destes campos: email, nome, sobrenome ou qualquer campo personalizado que tenha sido adicionado à Filtragem avançada ao estender o recurso de perfil.

>[!NOTE]
>
>As pesquisas diferenciam maiúsculas de minúsculas e são executadas somente em prefixos. Por exemplo, você não poderá procurar um perfil usando as últimas letras do nome.

***Solicitações de exemplo***

* Exemplo de solicitação para filtrar perfis com base no nome.

  ```
  -X GET https://mc.adobe.io/<ORGANIZATION>/campaign/profileAndServices/profile/byText?text=John&filterType=firstName \
  -H 'Content-Type: application/json' \
  -H 'Authorization: Bearer <ACCESS_TOKEN>' \
  -H 'Cache-Control: no-cache' \
  -H 'X-Api-Key: <API_KEY>'
  ```

* Exemplo de solicitação para filtrar perfis com base no sobrenome.

  ```
  -X GET https://mc.adobe.io/<ORGANIZATION>/campaign/profileAndServices/profile/byText?text=Miller&filterType=lastName \
  -H 'Content-Type: application/json' \
  -H 'Authorization: Bearer <ACCESS_TOKEN>' \
  -H 'Cache-Control: no-cache' \
  -H 'X-Api-Key: <API_KEY>'
  ```

* Exemplo de solicitação para filtrar perfis com base em email.

  ```
  -X GET https://mc.adobe.io/<ORGANIZATION>/campaign/profileAndServices/profile/byText?text=John%40gmail.com&filterType=email \
  -H 'Content-Type: application/json' \
  -H 'Authorization: Bearer <ACCESS_TOKEN>' \
  -H 'Cache-Control: no-cache' \
  -H 'X-Api-Key: <API_KEY>'
  ```

* Exemplo de solicitação para filtrar perfis com base no campo personalizado &quot;Hobby&quot;.

  ```
  -X GET https://mc.adobe.io/<ORGANIZATION>/campaign/profileAndServicesExt/profile/byText?cusHobby=Dancing&filterType=Hobby \
  -H 'Content-Type: application/json' \
  -H 'Authorization: Bearer <ACCESS_TOKEN>' \
  -H 'Cache-Control: no-cache' \
  -H 'X-Api-Key: <API_KEY>'
  ```
