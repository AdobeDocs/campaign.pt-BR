---
title: Conecte-se ao Campaign v8
description: Saiba como se conectar ao Adobe Campaign v8 e instalar o console em seu computador para facilitar o acesso.
feature: Client Console
role: User
level: Beginner
exl-id: 176cc4f0-8827-4127-9f03-7d75ac8cf917
source-git-commit: f381a2ec91b7179a51d91f9b7414ea39db03cd71
workflow-type: tm+mt
source-wordcount: '823'
ht-degree: 11%

---

# Conectar-se ao Adobe Campaign v8{#gs-ac-connect}

O Console do Cliente do Campaign é um cliente avançado que permite a conexão com o(s) servidor(es) de aplicativos do Campaign. Saiba mais sobre o Console do cliente do Campaign [nesta página](ac-components.md#presentation-layer).

Antes de começar, é necessário:

* Verifique a compatibilidade do sistema e das ferramentas com o Adobe Campaign no [Matriz de compatibilidade](compatibility-matrix.md)
* Obter o URL do servidor do Campaign
* Crie sua Adobe ID ou obtenha suas credenciais de usuário de sua empresa
* Instale o tempo de execução do Microsoft Edge Webview2 em seu sistema (a partir da versão de build do Campaign Classic 8.4). [Saiba mais](#webview)

## Instalação do tempo de execução do Microsoft Edge Webview2 {#webview}

A partir da versão de build do Campaign Classic 8.4, a instalação do tempo de execução do Microsoft Edge Webview 2 é necessária para qualquer instalação do console.

O Web View é instalado por padrão como parte do sistema operacional Windows 11. Se ele ainda não estiver presente em seu sistema, o Campaign Console Installer solicitará que você o baixe de [Site do desenvolvedor do Microsoft](http://www.adobe.com/go/acc-ms-webview2-runtime-download_br){target=&quot;_blank&quot;}. Observe que o link de download não funciona no navegador Internet Explorer 11, pois o Microsoft substituiu o suporte. Use um navegador diferente para acessar o link.

## Baixe e instale o Console do cliente{#download-ac-console}

Ao usar o Campaign pela primeira vez ou se precisar atualizar para uma versão mais recente, é necessário baixar o Console do cliente e instalá-lo.

Estão disponíveis duas opções:

1. Como administrador do Campaign, conecte-se ao Adobe [Distribuição de software](https://experience.adobe.com/#/downloads/content/software-distribution/br/campaign.html){target=&quot;_blank&quot;} e baixar o programa de instalação do Console do Cliente. Em seguida, você pode instalá-lo em sua máquina local.

1. Como usuário final, o Adobe pode implantar o Console para você: depois que o Console for atualizado, você será solicitado a baixar a versão mais recente do Console do cliente em uma janela pop-up.

>[!CAUTION]
>
>O Adobe recomenda deixar a opção **[!UICONTROL No longer ask this question]** não selecionado para garantir que todos os usuários sejam alertados quando uma nova versão do Console estiver disponível.  Se essa opção for selecionada, o usuário não será informado sobre novas versões disponíveis.

## Criar a conexão{#create-your-connection}

Depois que o Console do cliente for recém-instalado, siga as etapas abaixo para criar a conexão com o servidor de aplicativos:

1. Inicie o Console a partir do Windows **[!UICONTROL Start]** no menu **Adobe Campaign** grupo de programas.

1. Clique no link no canto superior direito dos campos de credenciais para acessar a janela de configuração da conexão.

1. Clique em **[!UICONTROL Add > Connection]** e insira o rótulo e o URL do servidor de aplicativos do Adobe Campaign.

1. Especifique uma conexão com o servidor de aplicativos do Adobe Campaign por meio de um URL. Use um DNS ou um alias da máquina ou seu endereço IP.

   Por exemplo, você pode usar a variável [`https://<machine>.<domain>.com`](https://myserver.adobe.com) digite URL.

1. Marque a opção **[!UICONTROL Connect with an Adobe ID]**.

1. Clique em **[!UICONTROL Ok]** para salvar suas configurações.

Você pode adicionar quantas conexões forem necessárias para se conectar aos ambientes de teste, estágio e produção, por exemplo.

>[!NOTE]
>
>O **[!UICONTROL Add]** permite criar **[!UICONTROL folders]** para organizar todas as suas conexões. Basta arrastar e soltar cada conexão em uma pasta.

## Faça logon no Adobe Campaign {#logon-to-ac}

Para fazer logon em uma instância existente, siga as etapas abaixo:

1. Inicie o Console a partir do Windows **[!UICONTROL Start]** no menu **Adobe Campaign** grupo de programas.

1. Clique no link no canto superior direito dos campos de credenciais para acessar a janela de configuração da conexão.

   ![](assets/connectToCampaign.png)

1. Selecione a instância do Campaign na qual você precisa fazer logon.

1. Clique em **[!UICONTROL Ok]**.

1. Você pode fazer logon no Campaign com [seu Adobe ID](#connect-ims).

   ![](assets/adobeID.png)

>[!NOTE]
>
>Para versões de build do campaign classic 8.4, o console do cliente Adobe Campaign pode solicitar credenciais de proxy duas vezes durante a autenticação de proxy. Isso ocorre porque o Microsoft Edge Webview2 não salva as credenciais de proxy no armazenamento de cache/senha, ao contrário do Internet Explorer.

## Conceder acesso aos usuários{#grant-access}

O Adobe Campaign permite definir e gerenciar os direitos atribuídos aos diversos operadores.

Como administrador do Campaign, você é responsável por criar os operadores e compartilhar suas credenciais com os usuários.

Saiba mais sobre os usuários e como definir suas permissões em [esta seção](gs-permissions.md).


## Conecte-se ao Campaign com sua Adobe ID{#connect-ims}

Os usuários do Campaign se conectam ao console do Adobe Campaign usando a Adobe ID, por meio do Adobe Identity Management System (IMS). Eles podem usar a mesma ID para todas as soluções do Adobe. A conexão é salva ao usar o Adobe Campaign com outras soluções.

Saiba mais sobre o Adobe IMS na [esta página](https://helpx.adobe.com/br/enterprise/using/identity.html){target=&quot;_blank&quot;}.

## Acesso à Web{#web-access}

Certas partes do aplicativo podem ser acessadas por um navegador da Web usando uma interface de usuário do HTML: relatórios, aprovação de delivery, monitoramento de instância e muito mais.

O acesso via Web fornece uma interface semelhante ao console, mas com um conjunto reduzido de funcionalidades.

Por exemplo, para um determinado operador, uma campanha será exibida com as seguintes opções no console:

![](assets/campaign-from-console.png)

Considerando o acesso via Web, as opções permitirão principalmente a visualização dos seguintes elementos:

![](assets/campaign-from-web.png)

O acesso à Web também é usado para no processo de validação: Os operadores podem clicar no email de solicitação de aprovação e se conectar ao Campaign por meio de seu navegador da Web para validar ou rejeitar um conteúdo ou orçamento de delivery.

Para acessar a instância do Campaign a partir da Web, o URL é:  `https://<your adobe campaign server>:<port number>/view/home`.
