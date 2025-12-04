---
title: Rastrear links personalizados
description: Saiba como rastrear links personalizados em emails
feature: Personalization
role: User
level: Beginner
exl-id: d0e00b40-e7dd-4484-b37c-fd3f3ac70fda
source-git-commit: 6e465ec24f72d0b30c4fc287da5d4c4bcaeda05b
workflow-type: tm+mt
source-wordcount: '637'
ht-degree: 50%

---

# Rastrear links personalizados {#tracking-personalized-links}

Os links no conteúdo de email que contêm personalização precisam de sintaxe específica para serem rastreados.

A utilização do JavaScript no conteúdo de email (HTML ou Texto) permite gerar e enviar conteúdo dinâmico para os destinatários, com duas limitações:

* O script não pode acessar o banco de dados diretamente (as funções SQL e API não estão disponíveis),
* O Adobe Campaign deve ser capaz de detectar URLs para que os links possam ser rastreados.

## Instruções de pré-processamento {#pre-processing-instructions}

Você pode adicionar instruções específicas de pré-processamento para fazer o script do URL e rastreá-lo. Essas instruções devem ser escritas no JavaScript e começar com `<%@`.

Por exemplo:

```
<%@ value object="myObject" xpath="@myField" %>
```

Esta instrução recupera o valor do campo `myField` do objeto `myObject`.

## Detecção de URL {#url-detection}

Para detecção de rastreamento, o Adobe Campaign incorpora o [Tidy](https://www.html-tidy.org/) para analisar a origem HTML e detectar o padrão. Ele lista todos os URLs do conteúdo para que possam ser rastreados individualmente. O Adobe Campaign usa o Tidy novamente para substituir o URL (`http://myurl.com`) por um URL que aponte para o servidor de redirecionamento do Adobe Campaign.

Por exemplo, no conteúdo inicial: `http://myurl.com/a.php?name=<%=escapeUrl(recipient.lastName)%>` é substituído para um determinado destinatário por: `http://emailing.customer.com/r/?id=h617791,71ffa3,71ffa8&p1=CustomerName`

Em que:

* &quot;h&quot; significa conteúdo HTML (ou &quot;t&quot; para conteúdo de texto).
* 617791 é a ID da mensagem/broadLog ID (hexadecimal).
* 71ffa3 é a NmsDelivery ID (hexadecimal).
* 71ffa8 é a NmsTrackingUrl ID (hexadecimal).
* p1, p2 e assim por diante são todos os parâmetros que serão substituídos no URL.

### Exemplo de não detecção {#non-detection-example}

`<%= getURL("http://mynewsletter.com") %>` funciona e envia o conteúdo real da página da Web por email para os destinatários. Mas nenhum dos links é rastreado. O motivo para isso é que o MTA executa `"<%=getURL(..."` para cada email antes do envio. Pode ser diferente para cada destinatário. Portanto, o Adobe Campaign não pode saber os URLs para rastreamento e atribuir uma ID de tag a eles.

Quando a página para download é a mesma para todos os recipients, a prática recomendada é usar:

```
<%@ include url="http://mynewsletter.com" %>
```

Nesse caso, a página é baixada durante a análise, antes da detecção do rastreamento. Ela permite que o Adobe Campaign descubra os links, atribua uma ID de tag e rastreie-os.

### Padrão recomendado {#recommended-pattern}

Após o processamento de instruções `<%@`, a URL a ser rastreada deve ter a seguinte sintaxe:

```
<a href="http://myurl.com/a.php?param1=aaa&param2=<%=escapeUrl(recipient.xxx)%>&param3=<%=escapeUrl(recipient.xxx)%>">
```

>[!IMPORTANT]
>
>Todos os outros padrões não são suportados pelo Adobe e devem ser evitados para impedir possíveis falhas de segurança.

## Parâmetros de URL {#url-parameters}

Para garantir que URLs personalizadas sejam rastreadas corretamente, você deve usar a função `escapeUrl()` ou o método de codificação apropriado para os parâmetros em suas URLs.

**Exemplo:**

```
<a href="http://myurl.com/a.php?name=<%=escapeUrl(recipient.lastName)%>">Click here</a>
```

Isso garantirá que o parâmetro personalizado seja codificado e rastreado corretamente pelo Adobe Campaign.

## Looping com `<%@ foreach %>` {#foreach}

A instrução `<%@ foreach %>` permite iterar sobre matrizes de objetos carregadas na entrega para rastrear links individuais relacionados aos objetos.

### Sintaxe

```
<%@ foreach object="myObject" xpath="myLink" index="3" item="myItem" %>
  <!-- Content to repeat -->
<%@ end %>
```

**Parâmetros:**

* **`object`**: Nome do objeto do qual iniciar (normalmente um objeto de script extra, mas pode ser uma entrega)
* **`xpath`** (opcional): XPath da coleção na qual executar um loop. O padrão é &quot;.&quot;, o que significa que o objeto é a matriz na qual executar um loop
* **`index`** (opcional): se xpath não for &quot;.&quot; e o objeto é uma matriz em si, índice de item do objeto (começa em 0)
* **`item`** (opcional): nome de um novo objeto acessível com `<%@ value %>` dentro do loop foreach. O padrão é o nome do link no esquema

### Exemplo

Nas propriedades/personalização da entrega, carregue uma matriz de artigos e uma tabela de relação entre o destinatário e os artigos.

Você pode exibir links para esses artigos com rastreamento individual:

```
<%@ foreach object="articleList" item="article" %>
  <a href="http://example.com/article.jsp?id=<%@ value object="article" xpath="@id" %>">
    <%@ value object="article" xpath="@title" %>
  </a>
<%@ end %>
```

Isso permite que o Adobe Campaign rastreie em qual artigo específico cada recipient clicou, em vez de apenas rastrear se um link de artigo foi clicado.

## Práticas recomendadas {#best-practices}

* Sempre usar a função `escapeUrl()` para parâmetros de URL dinâmicos
* Use `<%@ foreach %>` quando precisar rastrear itens individuais em coleções
* Teste o rastreamento antes de enviar o delivery para garantir que todos os links funcionem corretamente
* Verificar se os links personalizados estão formatados corretamente no conteúdo do delivery
* Verifique os logs de rastreamento para confirmar se os parâmetros personalizados estão sendo capturados corretamente

## Tópicos relacionados {#related-topics}

* [Saiba como configurar links rastreados](tracked-links.md)
* [Saiba como configurar opções de rastreamento de URL](url-tracking.md)
* [Saiba como adicionar campos de personalização](personalization-fields.md)

