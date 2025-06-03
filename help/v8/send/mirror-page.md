---
title: Adicionar um link para a mirror page
description: Saiba como adicionar e gerenciar o link para a mirror page
feature: Email
role: User
level: Beginner
version: Campaign v8, Campaign Classic v7
exl-id: 7bf3937c-484d-4404-8a9b-de7a10f5455a
source-git-commit: a2efad26232cd380eea850a589b22b23928253e8
workflow-type: tm+mt
source-wordcount: '434'
ht-degree: 56%

---

# Link para a mirror page {#mirror-page}

## Sobre a mirror page {#about-mirror-page}

A mirror page é uma versão online do seu email.

Embora a maioria dos clientes de email renderize imagens sem problemas, algumas predefinições podem evitar a exibição de imagens por motivos de segurança. Os usuários podem navegar até a mirror page de um email. Por exemplo, se estiverem enfrentando problemas de renderização ou imagens quebradas ao tentar exibi-la em sua caixa de entrada. Também é recomendável fornecer uma versão online por motivos de acessibilidade ou incentivar o compartilhamento em redes sociais.

A mirror page gerada pelo Adobe Campaign contém todos os dados de personalização.

![amostra de mirror link](assets/mirror-page-link.png){width="600" align="left"}

## Adicionar um link para a mirror page {#link-to-mirror-page}

Inserir um link para a mirror page é uma boa prática. Esse link pode ser, por exemplo, &quot;Exibir este email em seu navegador&quot; ou &quot;Leia online&quot;. Geralmente, ele está localizado no cabeçalho ou no rodapé do email.

No Adobe Campaign, você pode inserir um link para a mirror page no conteúdo do email usando o **bloco de personalização** dedicado. O bloco de personalização do **Link integrado para a mirror page** insere o seguinte código no conteúdo do email: `<%@ include view='MirrorPage' %>`.

![](assets/mirror-page-insert.png){width="800" align="left"}


Para obter mais informações sobre como inserir blocos de conteúdo de personalização, consulte [Blocos de personalização](personalization-blocks.md).

## Gerenciar a geração da mirror page {#mirror-page-generation}

Por padrão, a mirror page é gerada automaticamente pelo Adobe Campaign se o conteúdo do email não estiver vazio e se contiver um link para a mirror page (também conhecida como Mirror link).

Você pode controlar o modo de geração da mirror page de email. As opções estão disponíveis nas propriedades de entrega. Para acessar essas opções:

1. Navegue até a guia **[!UICONTROL Validity]** das propriedades de email.
1. Na seção **Gerenciamento da mirror page**, verifique a lista suspensa **[!UICONTROL Mode]**.

![](assets/mirror-page-generation.png){width="800" align="left"}

Além do modo padrão, as seguintes opções estão disponíveis:

* **[!UICONTROL Force the generation of the mirror page]**: use esse modo para gerar a mirror page mesmo se nenhum link para a mirror page for inserido na entrega.
* **[!UICONTROL Do not generate the mirror page]**: use esse modo para evitar a geração de uma mirror page, mesmo se o link estiver presente na entrega.
* **[!UICONTROL Generates a mirror page accessible using only the message identifier]**: quando o link da mirror page não estiver presente no conteúdo do email, use essa opção para habilitar o acesso ao conteúdo da mirror page, na janela de log da entrega, conforme detalhado abaixo.

## Verificar se há um destinatário na mirror page {#mirror-page-access}

É possível acessar o conteúdo da mirror page para um recipient específico de um delivery, com dados de personalização.

Para acessar essa mirror page:

1. Depois que a entrega for enviada, abra-a e navegue até a guia **[!UICONTROL Delivery]**.

1. Selecione um destinatário e clique no link **[!UICONTROL Display the mirror page for this message...]**.

   ![](assets/mirror-page-display.png){width="800" align="left"}

   A mirror page é exibida em uma tela dedicada, com dados de personalização para o recipient selecionado.
