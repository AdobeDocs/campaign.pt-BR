---
title: Adicionar um link à mirror page
description: Saiba como adicionar e gerenciar o link para a mirror page
feature: Email
role: User
level: Beginner
source-git-commit: 34af97ae01f7dba418fd0a8c950fc549dfbbd98b
workflow-type: tm+mt
source-wordcount: '432'
ht-degree: 0%

---

# Link para a mirror page{#mirror-page}

## Sobre a mirror page{#about-mirror-page}

A mirror page é uma versão online do seu email.

Embora a maioria dos clientes de email renderize imagens sem problemas, algumas predefinições podem evitar a exibição de imagens por motivos de segurança. Os usuários podem navegar até a mirror page de um email, por exemplo, se estiverem enfrentando problemas de renderização ou imagens quebradas ao tentar exibi-lo em sua caixa de entrada. Também é recomendável fornecer uma versão online por motivos de acessibilidade ou incentivar o compartilhamento em redes sociais.

A mirror page gerada pelo Adobe Campaign contém todos os dados de personalização.

![amostra de link espelho](assets/mirror-page-link.png){width="600" align="left"}

## Adicionar um link à mirror page{#link-to-mirror-page}

Inserir um link para a mirror page é uma boa prática. Esse link pode ser, por exemplo, &quot;Exibir este email em seu navegador&quot; ou &quot;Leia online&quot;. Geralmente, ela está localizada no cabeçalho ou no rodapé do email.

No Adobe Campaign, você pode inserir um link para a mirror page no conteúdo do email usando o **bloco de personalização**. O **Link para mirror page** o bloco de personalização insere o seguinte código no conteúdo do email: `<%@ include view='MirrorPage' %>`.

![](assets/mirror-page-insert.png){width="800" align="left"}


Para obter mais informações sobre a inserção de blocos de conteúdo personalizados, consulte [Blocos de personalização](personalization-blocks.md).

## Geração de mirror page{#mirror-page-generation}

Por padrão, a mirror page é gerada automaticamente pelo Adobe Campaign se o conteúdo do email não estiver vazio e se contiver um link para a mirror page (também conhecido como Mirror link).

Você pode controlar o modo de geração da mirror page de email. As opções estão disponíveis nas propriedades de delivery. Para acessar essas opções:

1. Navegue até o **[!UICONTROL Validity]** das propriedades de email.
1. No **Gerenciamento de mirror pages** verifique a seção **[!UICONTROL Mode]** lista suspensa.

![](assets/mirror-page-generation.png){width="800" align="left"}

Além do modo padrão, as seguintes opções estão disponíveis:

* **[!UICONTROL Force the generation of the mirror page]**: use esse modo para gerar a mirror page, mesmo se nenhum link para a mirror page for inserido no delivery.
* **[!UICONTROL Do not generate the mirror page]**: use esse modo para evitar a geração de uma mirror page, mesmo se o link estiver presente no delivery.
* **[!UICONTROL Generates a mirror page accessible using only the message identifier]**: quando o link da mirror page não estiver presente no conteúdo do email, use essa opção para habilitar o acesso ao conteúdo da mirror page, na janela de log do delivery, conforme detalhado abaixo.

## Verificar a mirror page de um recipient{#mirror-page-access}

Você pode acessar o conteúdo da mirror page de um recipient específico de um delivery, com dados de personalização.

Para acessar essa mirror page:

1. Depois que o delivery for enviado, abra-o e navegue até sua **[!UICONTROL Delivery]** guia .

1. Selecione um recipient e clique no botão **[!UICONTROL Display the mirror page for this message...]** link .

   ![](assets/mirror-page-display.png){width="800" align="left"}

   A mirror page é exibida em uma tela dedicada, com dados de personalização do recipient selecionado.

