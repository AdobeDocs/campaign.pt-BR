---
title: Conectar-se ao Campaign com o console do cliente
description: Saiba como instalar o console do cliente do Campaign em seu computador e conectar-se ao Adobe Campaign
feature: Client Console
role: User
level: Beginner
exl-id: 176cc4f0-8827-4127-9f03-7d75ac8cf917
source-git-commit: 87426a5924e1044faf212631ba868753ae43fad6
workflow-type: tm+mt
source-wordcount: '962'
ht-degree: 16%

---

# Conectar-se ao Campaign com o console do cliente{#gs-ac-connect}

Para se conectar ao Campaign com o console do cliente, primeiro você deve instalá-lo e configurá-lo.

Antes de começar, é necessário:

* Verifique a compatibilidade do sistema e das ferramentas com o Adobe Campaign na [Matriz de compatibilidade](compatibility-matrix.md)
* Obter o URL do servidor do Campaign
* Crie sua Adobe ID ou obtenha suas credenciais de usuário da empresa
* Instale o tempo de execução do Microsoft Edge Webview2 em seu sistema. [Saiba mais](#webview)


>[!NOTE]
>
>Você também pode se conectar à interface da Web do Campaign usando um navegador da Web. Saiba mais sobre a nova interface do usuário da Web do Campaign em [esta documentação](https://experienceleague.adobe.com/docs/campaign-web/v8/campaign-web-home.html?lang=pt-BR){target="_blank"}.


## Instalar o console do cliente{#download-ac-console}

### Tempo de execução do Microsoft Edge Webview2 {#webview}

A partir da versão de build do Campaign Classic 8.4, a instalação do Webview 2 runtime do Microsoft Edge é necessária para qualquer instalação do console do cliente.

O Modo de Exibição da Web é instalado por padrão como parte do sistema operacional Windows 11. Se ainda não estiver presente no sistema, o programa de instalação do console do cliente do Campaign solicitará que você o baixe do [site do Microsoft Developer](http://www.adobe.com/go/acc-ms-webview2-runtime-download_br){target="_blank"}. Observe que o link de download não funciona no navegador Internet Explorer 11, pois o Microsoft descontinuou seu suporte. Use um navegador diferente para acessar o link.

### Baixar o console{#install-ac-console}

Ao usar o Campaign pela primeira vez, é necessário baixar o console do cliente e instalá-lo.

Duas opções estão disponíveis para baixar o console do cliente:

1. Como administrador do Campaign, conecte-se ao Adobe [Distribuição de software](https://experience.adobe.com/#/downloads/content/software-distribution/br/campaign.html){target="_blank"}.

1. Como usuário final, o administrador do Campaign implanta o console do cliente para você e o disponibiliza por meio de um URL dedicado.

Depois que o programa de instalação do console do cliente for baixado, instale-o em seu computador local.

Observe que não é possível alterar o idioma do console do cliente após sua instalação.

## Criar sua conexão{#create-your-connection}

Depois que o console do cliente estiver instalado, siga as etapas abaixo para criar a conexão com o servidor de aplicativos:

1. Inicie o Console do e navegue pelo link no canto direito para acessar a tela de configuração da conexão.

1. Clique em **[!UICONTROL Add > Connection]** e insira o rótulo e a URL do servidor de aplicativos do Adobe Campaign.

1. Especifique uma conexão com o servidor de aplicativos Adobe Campaign por meio de um URL. Use um DNS ou um alias da máquina, ou seu endereço IP.

   Por exemplo, você pode usar o URL do tipo `https://<machine>.<domain>.com`.

1. Marque a opção **[!UICONTROL Connect with an Adobe ID]**.

1. Clique em **[!UICONTROL Ok]** para salvar suas configurações.

Você pode adicionar quantas conexões forem necessárias para se conectar aos ambientes de teste, preparo e produção, por exemplo.

>[!NOTE]
>
>O botão **[!UICONTROL Add]** permite criar **[!UICONTROL folders]** para organizar todas as suas conexões. Basta arrastar e soltar cada conexão em uma pasta.

## Fazer logon no Adobe Campaign {#logon-to-ac}

Os usuários do Campaign se conectam ao console do Adobe Campaign usando a Adobe ID, por meio do Adobe Identity Management System (IMS). Eles podem usar a mesma ID em todas as soluções Adobe. A conexão é salva ao usar o Adobe Campaign com outras soluções. Saiba mais sobre o Adobe IMS em [esta página](https://helpx.adobe.com/br/enterprise/using/identity.html){target="_blank"}.

Para fazer logon em uma instância, siga as etapas abaixo:

1. Inicie o Console do e navegue pelo link no canto direito para acessar a tela de configuração da conexão.

   ![](assets/connectToCampaign.png)

1. Selecione a instância do Campaign para a qual você precisa fazer logon.

1. Clique em **[!UICONTROL Ok]**.

Em seguida, você pode fazer logon no Campaign com sua Adobe ID.

![](assets/adobeID.png)

>[!NOTE]
>
>Como o Microsoft Edge Webview2 não salva as credenciais de proxy, o Console pode solicitar que você se autentique duas vezes na primeira conexão.

## Atualizar o console do cliente{#upgrade-ac-console}

Quando seu sistema é atualizado para uma versão mais recente, você deve atualizar seu console do cliente para essa mesma versão. Essa é uma prática recomendada e, para algumas versões, essa atualização é obrigatória. Nesse caso, ele é mencionado nas [Notas de versão](release-notes.md).

Como usuário do Managed Cloud Service, o Adobe implanta o console do cliente para você. Ao se conectar ao ambiente atualizado, você será solicitado a baixar a versão mais recente do console do cliente em uma janela pop-up. Você deve aceitar essa atualização e atualizar o console do cliente conforme solicitado.

>[!CAUTION]
>
>A Adobe recomenda deixar a opção **[!UICONTROL No longer ask this question]** desmarcada para garantir que você seja alertado quando uma nova versão do Console estiver disponível. Se essa opção for selecionada, o usuário não será informado de que é necessária uma atualização do Console.
>



## Conceder acesso aos usuários{#grant-access}

O Adobe Campaign permite definir e gerenciar os direitos atribuídos aos diversos operadores.

Como administrador do Campaign, você é responsável por criar os operadores e compartilhar suas credenciais com os usuários.

Saiba mais sobre usuários e como definir suas permissões em [esta seção](gs-permissions.md).


## Acessar o Campaign com um navegador da Web {#connect-web-ac}

### Interface da Web {#connect-web-ui}

A partir da versão 8.6 do Campaign, você terá acesso à nova **interface de usuário do Campaign Web**, disponível por meio do ambiente central da Adobe Experience Cloud. A Experience Cloud é a família integrada de aplicativos, produtos e serviços de marketing digital da Adobe. Com sua interface intuitiva, você pode acessar rapidamente os aplicativos em nuvem, recursos do produto e serviços. 

>[!AVAILABILITY]
>A interface da Web do Campaign só está disponível para usuários que se conectam ao Adobe Campaign com sua Adobe ID. Saiba mais sobre o [Adobe Identity Management System (IMS)](https://helpx.adobe.com/br/enterprise/using/identity.html){target="_blank"}.
>

Saiba como se conectar à Adobe Experience Cloud e acessar a interface do Adobe Campaign Web [nesta página](campaign-ui.md#ac-web-ui).

Saiba mais na [Documentação da interface do Adobe Campaign Web](https://experienceleague.adobe.com/pt-br/docs/campaign-web/v8/campaign-web-home){target="_blank"}.

### Acesso à Web {#web-access}

Certas partes do aplicativo podem ser acessadas por meio de um navegador da Web usando uma interface do usuário HTML: relatórios, aprovação de entrega, monitoramento de instâncias e muito mais.

O acesso via Web fornece uma interface semelhante ao console, mas com um conjunto reduzido de funcionalidades.

Por exemplo, para um determinado operador, uma campanha será exibida com as seguintes opções no console:

![](assets/campaign-from-console.png)

Considerando o acesso via Web, as opções permitirão principalmente a visualização dos seguintes elementos:

![](assets/campaign-from-web.png)

O acesso via Web também é usado no processo de validação: os operadores podem clicar no email de solicitação de aprovação e se conectar ao Campaign por meio do navegador da Web para validar ou rejeitar um conteúdo ou orçamento de delivery.

Para acessar sua instância do Campaign pela Web, a URL é: `https://<your adobe campaign server>:<port number>/view/home`.
