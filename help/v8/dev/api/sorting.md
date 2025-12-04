---
title: Operações adicionais
description: Saiba como executar operações adicionais
audience: developing
content-type: reference
topic-tags: campaign-standard-apis
role: Developer
level: Experienced
exl-id: 7db25b8d-a6f1-4151-bf37-c47e9991ae48
source-git-commit: 00d9c3229b7bbabfec3b1750ae84978545fdc218
workflow-type: tm+mt
source-wordcount: '739'
ht-degree: 1%

---

# Operações adicionais {#additional-operations}

## Classificação {#sorting}

A classificação está disponível por padrão em ordem crescente. Para classificar em ordem decrescente, anexe **%20desc** ao valor do parâmetro **_order**.

Para saber se um campo pode ser classificado, verifique o parâmetro &quot;classitable&quot; nos metadados do recurso. Para obter mais informações, consulte [esta seção](metadata-mechanism.md).

<br/>

***Solicitações de exemplo***

* Exemplo de solicitação do GET para recuperar emails no banco de dados em ordem alfabética.

  ```
  -X GET https://mc.adobe.io/<ORGANIZATION>/campaign/profileAndServices/profile/email?_order=email \
  -H 'Content-Type: application/json' \
  -H 'Authorization: Bearer <ACCESS_TOKEN>' \
  -H 'Cache-Control: no-cache' \
  -H 'X-Api-Key: <API_KEY>'
  ```

  Resposta à solicitação.

  ```
  {
  "content": [
      "adam@email.com",
      "allison.durance@example.com",
      "amy.dakota@mail.com",
      "andrea.johnson@mail.com",
      ...
  ]
  ...
  }
  ```

* Exemplo de solicitação do GET para recuperar o email no banco de dados em ordem alfabética decrescente.

  ```
  -X GET https://mc.adobe.io/<ORGANIZATION>/campaign/profileAndServices/profile/email?_order=email%20desc \
  -H 'Content-Type: application/json' \
  -H 'Authorization: Bearer <ACCESS_TOKEN>' \
  -H 'Cache-Control: no-cache' \
  -H 'X-Api-Key: <API_KEY>'
  ```

  Resposta à solicitação.

  ```
  {
  "content": [
      "tombinder@example.com",
      "tombinder@example.com",
      "timross@example.com",
      "john.smith@example.com",
      ...
  ]
  }
  ```

## Filtragem {#filtering}

### Recuperando metadados de filtros

Os filtros estão disponíveis para cada recurso. Para identificar os filtros associados a um recurso, é necessário executar uma solicitação GET nos metadados do recurso. Essa solicitação retorna o URL em que todos os filtros são definidos para um determinado recurso. Para obter mais informações sobre metadados, consulte [esta seção](metadata-mechanism.md).

Para identificar os metadados de um filtro e determinar como usá-lo, é necessário executar uma solicitação GET no URL retornado anteriormente.

<br/>

***Solicitação de exemplo***

As cargas de amostra abaixo mostram como recuperar os metadados do filtro &quot;byText&quot; para o recurso &quot;perfil&quot;. Primeiro, execute uma solicitação de GET na metada de recurso &quot;perfil&quot;.

```
-X GET https://mc.adobe.io/<ORGANIZATION>/campaign/profileAndServices/resourceType/profile \
-H 'Content-Type: application/json' \
-H 'Authorization: Bearer <ACCESS_TOKEN>' \
-H 'Cache-Control: no-cache' \
-H 'X-Api-Key: <API_KEY>'
```

Ele retorna o URL no qual os filtros são descritos.

```
{
"filters": {
        "href": "https://mc.adobe.io/<ORGANIZATION>/campaign/profileAndServices/resourceType/<PKEY>/filters/"
    }
  }
```

Execute uma solicitação GET no URL. Ele retorna a lista de filtros para o recurso de perfil, com os metadados associados a cada filtro.

```
{
"birthday": {
        "PKey": "@FL-CbDFXbnHbXcVpeCGWL46VXJLn1LqxLMPagt2vz8sCxQ52lvB15KiUaxXkxJYQw-tZXYrgUWG6K8QcB4gxVY9RKoba5bRFY3294YFshDmorRr8",
        "category": "0150_profile",
        "condition": ...,
        "data": "https://mc.adobe.io/<ORGANIZATION>/campaign/profileAndServices/profile/birthday?type=$value&precision=$value&operator=$value&day=$value&month=$value&includeStart=$value&endDay=$value&endMonth=$value&includeEnd=$value&relativeValue=$value&nextUnitsValue=$value&previousUnitsValue=$value",
        "formType": "webPage",
        "fragmentName": "",
        "label": "Birthday",
}
```

### Estrutura de metadados de filtros

A mesma estrutura de metadados está disponível para cada filtro:

* Os campos **@formType** e **@webPage** são campos técnicos.
* O campo **dados** fornece uma amostra sobre como usar o filtro.
* O nó **metadata** descreve os parâmetros de filtro.
* O nó **condition** descreve o que o filtro deve fazer. Os parâmetros de filtro descritos no nó de metadados são usados para criar condições de filtro. Para cada condição de filtro, se **enabledIf** for true, a **expr** será aplicada.

<br/>

Exemplo de estrutura de metadados de filtro:

```
"byText": {
        "PKey": "...",
        "category": "99_none",
        "condition": ...,
        "data": "/profileAndServices/profile/byText?text=$value",
        "formType": "none",
        "fragmentName": "",
        "label": "By name or email",
    }
```

### Utilização de filtros

A filtragem é executada com a seguinte solicitação:

`GET https://mc.adobe.io/<ORGANIZATION>/campaign/profileAndServices/<resourceName>/by<filterName>?<filterParam>=<filterValue>`

É possível combinar vários filtros em uma única solicitação:

`GET https://mc.adobe.io/<ORGANIZATION>/campaign/profileAndServices/<resourceName>/<filter1name>/<filter2name>?<filter1param>=<filter1value>&<filter2param>=<filter2value>`

<br/>

***Solicitações de exemplo***

* Exemplo de solicitação do GET para recuperar os recursos de &quot;serviço&quot; com o tipo &quot;email&quot;.

  ```
  -X GET https://mc.adobe.io/<ORGANIZATION>/campaign/profileAndServices/service/byChannel?channel=email \
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
              "created": "2019-09-25 23:20:35.000Z",
              "href": "https://mc.adobe.io/<ORGANIZATION>/campaign/profileAndServices/service/@I_FIiDush4OQPc0mbOVR9USoh36Tt5CsD35lATvQjdWlXrYc0lFkvle2XIwZUbD8GqTVvSp8AfWFUvjkGMe1fPe5nok",
              "label": "Marketing Newsletter",
              "lastModified": "2019-09-25 23:20:35.000Z",
              "limitedDuration": false,
              "messageType": "email",
              "mode": "newsletter",
              ...
          },
          ...
      ],
      ...
  }
  ```

* Exemplo de solicitação do GET para recuperar os recursos de &quot;perfil&quot; que contêm &quot;Concluído&quot; em
os campos email ou sobrenome (o filtro byText pesquisa nos campos email e sobrenome).

  ```
  -X GET https://mc.adobe.io/<ORGANIZATION>/campaign/profileAndServices/profile/byText?text=Doe \
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
          }
          ...
      ],
      ...
  }
  ```

* Exemplo de solicitação do GET para recuperar os recursos de serviços com o tipo &quot;email&quot; e o rótulo &quot;sport&quot;.

  ```
  -X GET https://mc.adobe.io/<ORGANIZATION>/campaign/profileAndServices/service/byChannel/byText?channel=email&text=sport \
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
              "created": "2019-09-26 09:36:01.014Z",
              "href": "https://mc.adobe.io/<ORGANIZATION>/campaign/profileAndServices/service/<PKEY>",
              "label": "sport",
              "lastModified": "2019-09-26 09:36:01.014Z",
              "limitedDuration": false,
              "messageType": "email",
              "mode": "newsletter",
              "name": "SVC13",
              ...
          }
      ],
      ...
  }
  ```

### Filtros personalizados

Se quiser usar um filtro personalizado, será necessário criá-lo e personalizá-lo na interface do Adobe Campaign Standard. O filtro personalizado terá o mesmo comportamento que os filtros prontos para uso:

`GET https://mc.adobe.io/<ORGANIZATION>/campaign/profileAndServicesExt/<resourceName>/by<customFilterName>?<customFilterparam>=<customFilterValue>`

Para obter mais informações, consulte a documentação do Campaign Standard:

* [Configurando definição de filtro](https://helpx.adobe.com/br/campaign/standard/developing/using/configuring-filter-definition.html).
* [Caso de uso: chamada de um recurso usando uma chave de identificação composta](https://experienceleague.adobe.com/docs/campaign-standard/using/developing/adding-or-extending-a-resource/uc-calling-resource-id-key.html?lang=pt-BR).

<br/>

***Solicitação de exemplo***

Exemplo de solicitação do GET para recuperar os recursos de &quot;perfil&quot; com valores de transação de US$ 100 ou mais. Observe que o filtro &quot;byAmount&quot; foi definido primeiro na interface do Adobe Campaign Standard e vinculado à tabela personalizada &quot;Transaction&quot;.

```
-X GET https://mc.adobe.io/<ORGANIZATION>/campaign/profileAndServicesExt/profile/byAmount?amount_parameter=100 \
-H 'Content-Type: application/json' \
-H 'Authorization: Bearer <ACCESS_TOKEN>' \
-H 'Cache-Control: no-cache' \
-H 'X-Api-Key: <API_KEY>'
```

<!--
Response to the request.

```

{
    "content": [
        {
            "PKey": "<PKEY>",
            "builtIn": false,
            "created": "2019-09-26 09:36:01.014Z",
            "desc": "",
            "end": "",
            "href": "https://mc.adobe.io/<ORGANIZATION>/campaign/profileAndServices/profile/<PKEY>",
            ...
        }
    ],
}

```

-->

<!-- exemple à vérifier de bout en bout-->

<!--+category = query editor
privacy ?
displayFOrmat ?
pour faire un POST sur une enum, il faut lui passer le @name décrit dans le noeud values, chaque @name a une correspondance en format = au format définit par le resType
-->





<!--
 if link ou collection.* resName +
* resTarget tout ca, ca va ensemble : le système de lien, resTarget va donner la ressource targetée par le lien. type
resType = type technique (long..) resType = link alors unbound='false' ou 'true'
If type = enumeration alors champ "values" rajouté et les valeurs sont dans values
pour faire un POST sur une enum, il faut lui passer le @name décrit dans le noeud values, chaque @name a une correspondance en format = au format définit par le resType
ail faut que la valeur poster soit conforme ,elle doit valider la dataPolicy . La dataPolicy peut soit controler la valeur (email invalide), soit transformé (cas du smartCase par exemple)
type dans les metadata = type de haut-niveau (nombre, text)
-->

## Contagem {#counting}

A API REST do Adobe Campaign pode contar o número de registros em uma solicitação. Para fazer isso, use a URL retornada no nó **count**.

<br/>

***Solicitação de exemplo***

Para contar todos os serviços que têm um valor **messageType** igual a &quot;sms&quot;, execute uma solicitação GET com o filtro **byChannel**.

```
-X GET https://mc.adobe.io/<ORGANIZATION>/campaign/profileAndServices/service/byChannel?channel=sms \
-H 'Content-Type: application/json' \
-H 'Authorization: Bearer <ACCESS_TOKEN>' \
-H 'Cache-Control: no-cache' \
-H 'X-Api-Key: <API_KEY>'
```

Retorna os serviços correspondentes ao filtro.

```
{
    "content": [
        {
            ...
            "messageType": "sms",
            "mode": "newsletter",
            "name": "SVC6",
            ...
        },
        ...
    ],
    "count": {
        "href": "https://mc.adobe.io/<ORGANIZATION>/campaign/profileAndServices/service/byChannel/_count?channel=sms&_lineStart=@iKTZ2q3IiSEDqZ5Nw1vdoGnQCqF-8DAUJRaVwR9obqqTxhMy"
    },
    "serverSidePagination": true
}
```

Execute uma solicitação GET na URL do nó **count** para recuperar o número de resultados.

```
-X GET https://mc.adobe.io/<ORGANIZATION>/campaign/profileAndServices/service/byChannel/_count?channel=sms&_lineStart=@iKTZ2q3IiSEDqZ5Nw1vdoGnQCqF-8DAUJRaVwR9obqqTxhMy \
-H 'Content-Type: application/json' \
-H 'Authorization: Bearer <ACCESS_TOKEN>' \
-H 'Cache-Control: no-cache' \
-H 'X-Api-Key: <API_KEY>'
```

Retorna o número de registros.

```
{
    "count": 26
}
```

## Paginação {#pagination}

Por padrão, 25 recursos são carregados em uma lista.

O parâmetro **_lineCount** permite limitar o número de recursos listados na resposta.  Você pode usar o nó **próximo** para exibir os próximos resultados.

>[!NOTE]
>
>Sempre use o valor da URL retornado no nó **next** para executar uma solicitação de paginação.
>
>A solicitação **_lineStart** é calculada e deve sempre ser usada dentro da URL retornada no nó **next**.

<br/>

***Solicitação de exemplo***

Exemplo de solicitação do GET para exibir 1 registro do recurso de perfil.

```
-X GET https://mc.adobe.io/<ORGANIZATION>/campaign/profileAndServices/profile?_lineCount=1 \
-H 'Content-Type: application/json' \
-H 'Authorization: Bearer <ACCESS_TOKEN>' \
-H 'Cache-Control: no-cache' \
-H 'X-Api-Key: <API_KEY>'
```

Resposta à solicitação, com o nó **next** para executar a paginação.

```
{
    "content": [
        {
            "PKey": "<PKEY>",
            "firstName": "John",
            "lastName":"Doe",
            "birthDate": "1980-10-24",
            ...
        }
    ],
    "next": {
        "href": "https://mc.adobe.io/<ORGANIZATION>/campaign/profileAndServices/profile/email?_lineCount=10&_
        lineStart=@Qy2MRJCS67PFf8soTf4BzF7BXsq1Gbkp_e5lLj1TbE7HJKqc"
    }
    ...
}
```

Por padrão, o nó **próximo** não está disponível ao interagir com tabelas com uma grande quantidade de dados. Para executar a paginação, você deve adicionar o parâmetro **_forcePagination=true** à URL da chamada.

```
-X GET https://mc.adobe.io/<ORGANIZATION>/campaign/profileAndServices/profile?_forcePagination=true \
-H 'Content-Type: application/json' \
-H 'Authorization: Bearer <ACCESS_TOKEN>' \
-H 'Cache-Control: no-cache' \
-H 'X-Api-Key: <API_KEY>'
```

>[!NOTE]
>
>O número de registros acima do qual uma tabela é considerada grande é definido na opção **XtkBigTableThreshold** da Campaign Standard. O valor padrão é 100.000 registros.
