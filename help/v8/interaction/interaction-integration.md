---
product: campaign
title: Adicionar uma oferta em uma página da Web
description: Saiba como adicionar uma oferta em uma página da Web
feature: Interaction, Offers
role: User, Admin
exl-id: 1eb0775a-5da9-4a27-aa7b-339372748f9c
source-git-commit: 1a0b473b005449be7c846225e75a227f6d877c88
workflow-type: tm+mt
source-wordcount: '1458'
ht-degree: 68%

---

# Adicionar uma oferta em uma página da Web{#add-an-offer-in-web}

Para chamar o Mecanismo de oferta em uma página da Web, insira uma chamada para um código JavaScript diretamente na página. Essa chamada retorna o conteúdo da oferta em um elemento direcionado.

O URL de chamada de script tem essa aparência:

```
<script id="interactionProposalScript" src="https://<SERVER_URL>/nl/interactionProposal.js?env=" type="text/javascript"></script>
```

O parâmetro &quot;**env**&quot; recebe o nome interno do ambiente ativo dedicado às interações anônimas.

Para apresentar uma oferta, precisamos criar um ambiente e um espaço de oferta no Adobe Campaign e, em seguida, configurar a página HTML.

Os seguintes casos de uso detalham as possíveis opções para integrar ofertas via JavaScript.

## Opção 1: modo HTML {#html-mode}

### Apresentar uma oferta anônima {#presenting-an-anonymous-offer}

**Etapa 1: Preparar o mecanismo de oferta**

1. Abra a interface do Adobe Campaign e prepare um ambiente anônimo.
1. Crie um espaço de oferta vinculado ao ambiente anônimo.
1. Crie uma oferta e sua representação vinculada ao espaço de oferta.

**Etapa 2: atualizar o conteúdo da página de HTML**

A página HTML deve incluir um elemento com um atributo @id com o valor do nome interno do espaço de oferta criado (&quot;i_internal name space&quot;). A oferta será inserida neste elemento pelo Interaction.

No nosso exemplo, o atributo @id recebe o valor &quot;i_SPC12&quot;, onde &quot;SPC12&quot; é o nome interno do espaço de oferta criado anteriormente:

```
<div id="i_SPC12"></div>
```

No nosso exemplo, a URL para chamar o script é a seguinte (&quot;OE3&quot; é o nome interno do ambiente ativo):

```
<script id="interactionProposalScript" src="https://instance.adobe.org:8080/nl/interactionProposal.js?env=OE3" type="text/javascript"></script>
```

>[!CAUTION]
>
>A tag `<script>` não deve fechar automaticamente.

Essa chamada estática gerará automaticamente uma chamada dinâmica contendo todos os parâmetros necessários do mecanismo de oferta.

Esse comportamento permite usar vários espaços de ofertas na mesma página, gerenciados por uma única chamada do mecanismo de oferta.

**Etapa 3: exibir os resultados na página HTML**

O conteúdo da representação da oferta é retornado para a página HTML pelo Mecanismo de oferta:

```
<div id="banner_header">
 <div id="i_SPC12">
   <table>
    <tbody>
        <tr>
            <td><h3>Fly to Japan!</h3></td>
        </tr>
        <tr>
            <td><img width="150px" src="https://instance.adobe.org/res/Track/874fdaf72ddc256b2d8260bb8ec3a104.jpg"></td>
            <td>
            <p>Discover Japan for 2 weeks at an unbelievable price!!</p>
            <p><b>2345 Dollars - All inclusive</b></p>
        </td>
        </tr>
    </tbody>
    </table>
 </div>
<script src="https://instance.adobe.org:8080/nl/interactionProposal.js?env=OE3" id="interactionProposalScript" type="text/javascript"></script>
</div>
```

### Apresentar uma oferta identificada {#presenting-an-identified-offer}

Para apresentar uma oferta a um contato identificado, o processo é semelhante ao processo detalhado [nesta seção](#presenting-an-anonymous-offer).

No conteúdo da página da Web, é necessário adicionar o script a seguir para identificar o contato durante a chamada para o mecanismo de oferta:

```
<script type="text/javascript">
  interactionTarget = <contact_identifier>;
</script>
```

1. Vá para o espaço de oferta que será chamado pela página da Web, clique em **[!UICONTROL Advanced parameters]** e adicione uma ou mais chaves de identificação.

   ![](assets/interaction_htmlmode_001.png)

   Neste exemplo, a chave de identificação é composta por ser baseada no e-mail e no nome do destinatário.

1. Durante a exibição da página da Web, a avaliação do script permite passar a ID do recipient para o mecanismo de oferta. Se a ID for composta, as chaves serão exibidas na mesma sequência usada nas configurações avançadas e separadas por um |.

   No exemplo a seguir, o contato fez logon no site e foi reconhecido durante a chamada para o mecanismo de oferta graças ao email e ao nome.

   ```
   <script type="text/javascript">
     interactionTarget = myEmail|myName;
   </script>
   ```

### Usar uma função de renderização de HTML {#using-an-html-rendering-function}

Para gerar a representação de oferta HTML automaticamente, é possível usar uma função de renderização.

1. Vá para o espaço da oferta e clique no link **[!UICONTROL Edit functions]**.
1. Selecione **[!UICONTROL Overload the HTML rendering function]**.
1. Vá para a guia **[!UICONTROL HTML rendering]** e insira as variáveis que correspondem aos campos definidos para o conteúdo da oferta no espaço de oferta.

   ![](assets/interaction_htmlmode_002.png)

   Neste exemplo, a oferta é exibida no formato de um banner na página da Web e é composta de uma imagem clicável e um título que corresponde aos campos definidos no conteúdo da oferta.

## Opção 2: modo XML {#xml-mode}

### Apresentar uma oferta {#presenting-an-offer}

O módulo Campaign **Interaction** permite retornar um nó XML para a página HTML que chama o mecanismo de oferta. Este nó XML pode ser processado por funções a serem desenvolvidas no lado do cliente.

A chamada para o mecanismo de oferta tem esta aparência:

```
<script type="text/javascript" id="interactionProposalScript" src="https://<SERVER_URL>/nl/interactionProposal.js?env=&cb="></script>
```

* O parâmetro &quot;**env**&quot; recebe o nome interno do ambiente ativo.

* O parâmetro &quot;**cb**&quot; recebe o nome da função que lê o nó XML retornado pelo mecanismo que contém a(s) proposta(s) (de retorno de chamada). Este parâmetro é opcional.

* O parâmetro &quot;**t**&quot; recebe o valor do target, somente para uma interação identificada. Esse parâmetro também pode ser passado com a variável **interactionTarget.** Este parâmetro é opcional.

* O parâmetro &quot;**c**&quot; recebe a lista de nomes internos das categorias. Este parâmetro é opcional.

* O parâmetro &quot;**th**&quot; recebe a lista de temas. Este parâmetro é opcional.

* O parâmetro &quot;**gctx**&quot; recebe a chamada dos dados globais (contexto) para a página inteira. Este parâmetro é opcional.

O nó XML retornado tem esta aparência:

```
<propositions>
 <proposition id="" offer-id="" weight="" rank="" space="" div=""> //proposition identifiers
   ...XML content defined in Adobe Campaign...
 </proposition>
 ...
</propositions>
```

O caso de uso abaixo detalha as configurações a serem executadas no Adobe Campaign para habilitar o modo XML e, em seguida, mostrar o resultado da chamada para o mecanismo na página de HTML.

1. **Criar um ambiente e um espaço de ofertas**

   Para obter mais informações sobre como criar um ambiente, consulte [esta página](interaction-env.md).

   Para obter mais informações sobre como criar um espaço de ofertas, consulte [esta página](interaction-offer-spaces.md).

1. **Estender o esquema de oferta para adicionar novos campos**

   Esse esquema definirá os seguintes campos: Title number 2 e price.

   O nome do schema no exemplo é **cus:offer**.

   ```
   <srcSchema _cs="Marketing offers (cus)" created="2013-01-18 17:14:20.762Z" createdBy-id="0"
              desc="" entitySchema="xtk:srcSchema" extendedSchema="nms:offer" img="nms:offer.png"
              label="Marketing offers" labelSingular="Marketing offers" lastModified="2013-01-18 15:20:18.373Z"
              mappingType="sql" md5="F14A7AA009AE1FCE31B0611E72866AC3" modifiedBy-id="0"
              name="offer" namespace="cus" xtkschema="xtk:srcSchema">
     <createdBy _cs="Administrator (admin)"/>
     <modifiedBy _cs="Administrator (admin)"/>
     <element img="nms:offer.png" label="Marketing offers" labelSingular="Marketing offer"
              name="offer">
       <element label="Content" name="view">
         <element label="Price" name="price" type="long" xml="true"/>
         <element label="Title 2" name="title2" type="string" xml="true"/>
   
         <element advanced="true" desc="Price calculation script." label="Script price"
                  name="price_jst" type="CDATA" xml="true"/>
         <element advanced="true" desc="Title calculation script." label="Script title"
                  name="title2_jst" type="CDATA" xml="true"/>
       </element>
     </element>
   </srcSchema>
   ```

   >[!CAUTION]
   >
   >Cada elemento precisa ser definido duas vezes. Os elementos do tipo CDATA (&quot;_jst&quot;) podem conter campos de personalização.
   >
   >Não esqueça de atualizar a estrutura do banco de dados.

   Você pode estender o schema de ofertas para adicionar novos campos em modo de lote e unitário e em qualquer formato (texto, HTML e XML).

1. **Estender a fórmula de oferta para editar novos campos e modificar um campo existente**

   Edite o formulário de entrada **Offer (nsm)**.

   Na seção &quot;Views&quot;, insira os dois novos campos com o seguinte conteúdo:

   ```
   <input label="Title 2" margin-right="5" prebuildSubForm="false" type="subFormLink" xpath="title2_jst">
        <form label="Edit title 2" name="editForm" nothingToSave="true">
            <input nolabel="true" toolbarAlign="horizontal" type="jstEdit" xpath="." xpathInsert="/ignored/customizeTitle2">
            <container>
                <input menuId="viewMenuBuilder" options="inbound" type="customizeBtn" xpath="/ignored/customizeTitle2"/>
            </container>
            </input>
        </form>
    </input>
    <input nolabel="true" type="edit" xpath="title2_jst"/>
    <input label="Price" margin-right="5" prebuildSubForm="false" type="subFormLink" xpath="price_jst">
        <form label="Edit price" name="editForm" nothingToSave="true">
        <input nolabel="true" toolbarAlign="horizontal" type="jstEdit" xpath="." xpathInsert="/ignored/customizePrice">
            <container>
                <input menuId="viewMenuBuilder" options="inbound" type="customizeBtn" xpath="/ignored/customizePrice"/>
            </container>
        </input>
        </form>
    </input>
    <input colspan="2" label="Prix" nolabel="true" type="number" xpath="price_jst"/>
   ```

   Comente o campo URL de destino:

   ![](assets/interaction_xmlmode_form_001.png)

   >[!CAUTION]
   >
   >Os campos do formulário (`<input>`) devem apontar para os elementos do tipo CDATA definidos no esquema criado.

   A renderização nas representações de oferta é semelhante a esta:

   ![](assets/interaction_xmlmode_form.png)

   Os campos **[!UICONTROL Title 2]** e **[!UICONTROL Price]** foram adicionados e o campo **[!UICONTROL Destination URL]** não é mais exibido.

1. **Criar uma oferta**

   Para obter mais informações sobre criação de ofertas, consulte [esta página](interaction-offer.md).

   No caso de uso a seguir, a oferta é inserida da seguinte maneira:

   ![](assets/interaction_xmlmode_offer.png)

1. **Aprovar a oferta**

   Aprove uma oferta ou solicite a outra pessoa a aprovar, então ative-a no espaço de oferta criado na última etapa para que ela fique disponível no ambiente ativo vinculado.

1. **O mecanismo chama e mostra o resultado na página HTML.**

   A chamada para o mecanismo de oferta na página de HTML tem esta aparência:

   ```
   <script id="interactionProposalScript" src="https://<SERVER_URL>/nl/interactionProposal.js?env=OE7&cb=alert" type="text/javascript">
   ```

   O valor do parâmetro &quot;**env**&quot; é o nome interno do ambiente ativo.

   O valor do parâmetro &quot;**cb**&quot; é o nome da função que precisa interpretar o nó XML retornado pelo mecanismo. No nosso exemplo, a função chamada abre uma janela modal (alert() função).

   O nó XML retornado pelo mecanismo de oferta tem esta aparência:

   ```
   <propositions>
    <proposition id="a28002" offer-id="10322005" weight="1" rank="1" space="SPC14" div="i_SPC14">
     <xmlOfferView>
      <title>Travel to Russia</title>
      <price>3456</price>
      <description>Discover this vacation package!INCLUDES 10 nights. FEATURES buffet breakfast daily. BONUS 5th night free.</description>
      <image>
       <path>https://myinstance.com/res/Track/ae1d2113ed732d58a3beb441084e5960.jpg</path>
       <alt>Travel to Russia</alt>
      </image>
     </xmlOfferView>
    </proposition>
   </propositions>
   ```

### Usar uma função de renderização {#using-a-rendering-function-}

É possível usar uma função de renderização XML para criar uma apresentação de ofertas. Essa função modificará o nó XML retornado à página de HTML durante a chamada para o mecanismo de oferta.

1. Vá para o espaço da oferta e clique no link **[!UICONTROL Edit functions]**.
1. Selecione **[!UICONTROL Overload the XML rendering function]**.
1. Vá para a guia **[!UICONTROL XML rendering]** e insira a função desejada.

   A função pode ter esta aparência:

   ```
   function (proposition) {
     delete proposition.@id;
     proposition.@newAttribute = "newValue";
   } 
   ```

![](assets/interaction_xmlmode_001.png)

## Configurar uma integração com o SOAP

Os serviços da Web SOAP fornecidos para o gerenciamento de ofertas são diferentes daqueles normalmente usados no Adobe Campaign. Eles podem ser acessados por meio da URL de interação descrita na seção anterior e permitem apresentar ou atualizar ofertas para um determinado contato.

### Apresentação da oferta {#offer-proposition}

Para uma apresentação de oferta via SOAP, adicione o comando **nms:proposta#Propose** seguido pelos seguintes parâmetros:

* **targetId**: chave primária do destinatário (pode ser uma chave composta).
* **maxCount**: especifica o número de apresentações de oferta para o contato.
* **contexto**: permite adicionar informações de contexto no schema de espaço. Se o schema usado for **nms:interaction**, **`<empty>`** deverá ser adicionado.
* **categories**: especifica a(s) categoria(s) que as ofertas devem pertencer.
* **themes**: especifica o(s) tema(s) aos quais a(s) oferta(s) deve pertencer.
* **uuid**: valor do cookie permanente do Adobe Campaign (&quot;uuid230&quot;).
* **nli**: valor do cookie da sessão do Adobe Campaign (&quot;nlid&quot;).
* **noProp**: use o valor &quot;true&quot; para desativar a inserção de proposta.

>[!NOTE]
>
>As configurações **targetId** e **maxCount** são obrigatórias. As outras são opcionais.

Em resposta à query, o serviço SOAP retorna os seguintes parâmetros:

* **interactionId**: ID da interação.
* **propositions**: o elemento XML contém a lista de propostas, cada uma com sua própria identificação e representação HTML.

### Atualização da oferta {#offer-update}

Adicione o comando **nms:interação#UpdateStatus** à URL, seguido desses parâmetros:

* **proposition**: string de caracteres, contém o ID de proposta fornecida como uma saída durante uma apresentação de oferta. Consulte [Apresentação da oferta](#offer-proposition).
* **status**: tipo string, ele especifica o novo status da oferta. Os valores possíveis são listados na enumeração **propositionStatus** , no schema **nms:common.** Por exemplo, inicialmente, o número 3 corresponde ao status **Accepted**.
* **context**: o elemento XML permite adicionar informações de contexto no schema de espaço. Se o schema usado for **nms:interaction**, **`<empty>`** deverá ser adicionado.

### Exemplo usando uma chamada SOAP {#example-using-a-soap-call}

Veja um exemplo de código para uma chamada SOAP:

```
<%
  var space = request.parameters.sp
  var cnx = new HttpSoapConnection(
    "https://" + request.serverName + ":" + request.serverPort + "/interaction/" + env + "/" + space,
    "utf-8",
    HttpSoapConnection.SOAP_12)
  var session = new SoapService(cnx, "nms:interaction")
  var action = request.parameters.a
  if( action == undefined )
    action = 'propose'

  try
  {
    switch( action )
    {
    case "update":
      var proposition = request.parameters.p
      var status      = request.parameters.st
      session.addMethod("UpdateStatus", "nms:interaction#UpdateStatus",
       ["proposition", "string",
        "status",      "string",
        "context",     "NLElement"],
       [])
      session.UpdateStatus(proposition, status, <undef/>)
      var redirect = request.parameters.r
      if( redirect != undefined )
        response.sendRedirect(redirect)
      break;

    case "propose":
      var count = request.parameters.n
      var target = request.parameters.t
      var categorie = request.parameters.c
      var theme = request.parameters.th
      var layout = request.parameters.l
      if( count == undefined )
        count = 1
      session.addMethod("Propose", "nms:proposition#Propose",
       ["targetId",      "string",
        "maxCount",      "string",
         "categories",    "string",
         "themes",        "string",
        "context",       "NLElement"],
       ["interactionId", "string",
        "propositions",  "NLElement"])
      response.setContentType("text/html")
      var result = session.Propose(target, count, category, theme, <empty/>)
      var props = result[1]
  %><table><tr><%
      for each( var propHtml in props.proposition.*.mdSource )
      {
        %><td><%=propHtml%></td><%
      }
  %></tr></table><%
      break;
    }
  }
  catch( e )
  {
  }
  %>
```
