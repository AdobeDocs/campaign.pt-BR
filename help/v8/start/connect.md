---
title: Conectar-se ao Campaign v8
description: Saiba como se conectar ao Adobe Campaign v8 e instalar o console em seu computador para facilitar o acesso.
feature: Client Console
role: User
level: Beginner
exl-id: 176cc4f0-8827-4127-9f03-7d75ac8cf917
source-git-commit: b71197027d9521fd648a0c2657b6b76a1aa7fc9a
workflow-type: tm+mt
source-wordcount: '905'
ht-degree: 10%

---

# Conectar-se ao Adobe Campaign v8{#gs-ac-connect}

Para começar a trabalhar com o Campaign, você deve instalar e configurar o Console do cliente.

O Console do cliente é um aplicativo nativo que se comunica com o servidor de aplicativos do Adobe Campaign, por meio de protocolos padrão de Internet, como SOAP e HTTP. O console do cliente do Campaign centraliza todos os recursos e configurações e requer largura de banda mínima, pois depende de um cache local. Projetado para facilitar a implantação, o Console do cliente do Campaign pode ser implantado a partir de um navegador da Internet, atualizado automaticamente e não requer nenhuma configuração de rede específica, pois gera apenas tráfego HTTP(S).

Antes de começar, é necessário:

* Verifique a compatibilidade do sistema e das ferramentas com o Adobe Campaign na [Matriz de compatibilidade](compatibility-matrix.md)
* Obter o URL do servidor do Campaign
* Crie sua Adobe ID ou obtenha suas credenciais de usuário da empresa
* Instale o Webview2 Runtime do Microsoft Edge em seu sistema. [Saiba mais](#webview)

## Instalar o console do cliente{#download-ac-console}

### Tempo de execução do Microsoft Edge Webview2 {#webview}

A partir da versão de build do Campaign Classic 8.4, a instalação do Webview 2 runtime do Microsoft Edge é necessária para qualquer instalação do Console do cliente.

O Modo de Exibição da Web é instalado por padrão como parte do sistema operacional Windows 11. Se ainda não estiver presente no sistema, o programa de instalação do Console do cliente do Campaign solicitará que você o baixe em [Site do desenvolvedor do Microsoft](http://www.adobe.com/go/acc-ms-webview2-runtime-download_br){target="_blank"}. Observe que o link de download não funciona no navegador Internet Explorer 11, pois o Microsoft descontinuou seu suporte. Use um navegador diferente para acessar o link.

### Baixar o console{#install-ac-console}

Ao usar o Campaign pela primeira vez, é necessário baixar o Console do cliente e instalá-lo.

Duas opções estão disponíveis para baixar o Console do cliente:

1. Como administrador do Campaign, conecte-se ao Adobe [Distribuição de software](https://experience.adobe.com/#/downloads/content/software-distribution/br/campaign.html){target="_blank"}.

1. Como usuário final, o administrador do Campaign implanta o Console do cliente para você e o disponibiliza por meio de um URL dedicado.

Depois que o programa de instalação do Console do cliente for baixado, instale-o no computador local.

Observe que não é possível alterar o idioma do Console do cliente após sua instalação.

## Criar sua conexão{#create-your-connection}

Depois que o console do cliente estiver instalado, siga as etapas abaixo para criar a conexão com o servidor de aplicativos:

1. Inicie o Console do e navegue pelo link no canto direito para acessar a tela de configuração da conexão.

1. Clique em **[!UICONTROL Add > Connection]** e insira o rótulo e o URL do servidor de aplicativos do Adobe Campaign.

1. Especifique uma conexão com o servidor de aplicativos Adobe Campaign por meio de um URL. Use um DNS ou um alias da máquina, ou seu endereço IP.

   Por exemplo, você pode usar a variável [`https://<machine>.<domain>.com`](https://myserver.adobe.com) digite o URL.

1. Marque a opção **[!UICONTROL Connect with an Adobe ID]**.

1. Clique em **[!UICONTROL Ok]** para salvar suas configurações.

Você pode adicionar quantas conexões forem necessárias para se conectar aos ambientes de teste, preparo e produção, por exemplo.

>[!NOTE]
>
>A variável **[!UICONTROL Add]** permite criar **[!UICONTROL folders]** para organizar todas as suas conexões. Basta arrastar e soltar cada conexão em uma pasta.

## Fazer logon no Adobe Campaign {#logon-to-ac}

Os usuários do Campaign se conectam ao console do Adobe Campaign usando a Adobe ID, por meio do Adobe Identity Management System (IMS). Eles podem usar a mesma ID em todas as soluções Adobe. A conexão é salva ao usar o Adobe Campaign com outras soluções. Saiba mais sobre o Adobe IMS no [esta página](https://helpx.adobe.com/br/enterprise/using/identity.html){target="_blank"}.

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

Quando seu sistema é atualizado para uma versão mais recente, você deve atualizar seu console do cliente para essa mesma versão. Essa é uma prática recomendada e, para algumas versões, essa atualização é obrigatória. Nesse caso, é mencionado no [Notas de versão](release-notes.md).

Como usuário do Managed Cloud Service, o Adobe implanta o console do cliente para você. Ao se conectar ao ambiente atualizado, você será solicitado a baixar a versão mais recente do Console do cliente em uma janela pop-up. Você deve aceitar essa atualização e atualizar o Console do cliente conforme solicitado.

>[!CAUTION]
>
>O Adobe recomenda deixar a opção **[!UICONTROL No longer ask this question]** desmarcada para garantir que você seja alertado quando uma nova versão do Console estiver disponível. Se essa opção for selecionada, o usuário não será informado de que é necessária uma atualização do Console.
>



## Conceder acesso aos usuários{#grant-access}

O Adobe Campaign permite definir e gerenciar os direitos atribuídos aos diversos operadores.

Como administrador do Campaign, você é responsável por criar os operadores e compartilhar suas credenciais com os usuários.

Saiba mais sobre usuários e como definir suas permissões no [nesta seção](gs-permissions.md).


## Acesso à Web{#web-access}

Certas partes do aplicativo podem ser acessadas por meio de um navegador da Web usando uma interface do usuário HTML: relatórios, aprovação de entrega, monitoramento de instâncias e muito mais.

O acesso via Web fornece uma interface semelhante ao console, mas com um conjunto reduzido de funcionalidades.

Por exemplo, para um determinado operador, uma campanha será exibida com as seguintes opções no console:

![](assets/campaign-from-console.png)

Considerando o acesso via Web, as opções permitirão principalmente a visualização dos seguintes elementos:

![](assets/campaign-from-web.png)

O acesso via Web também é usado no processo de validação: os operadores podem clicar no email de solicitação de aprovação e se conectar ao Campaign por meio do navegador da Web para validar ou rejeitar um conteúdo ou orçamento de delivery.

Para acessar sua instância do Campaign pela Web, o URL é:  `https://<your adobe campaign server>:<port number>/view/home`.
