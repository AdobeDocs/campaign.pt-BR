---
title: Conectar-se ao Campaign v8
description: Saiba como se conectar ao Adobe Campaign v8 e instalar o console em seu computador para facilitar o acesso.
feature: Client Console
role: User
level: Beginner
exl-id: 176cc4f0-8827-4127-9f03-7d75ac8cf917
source-git-commit: 24ecf598d3d01f7fb59c70e1c8c81e9c086e653e
workflow-type: ht
source-wordcount: '1006'
ht-degree: 100%

---

# Conectar-se ao Adobe Campaign v8{#gs-ac-connect}

Para começar a trabalhar com o Campaign, você deve instalar e configurar o Console do cliente.

O Console do cliente é um aplicativo nativo que se comunica com o servidor de aplicativos do Adobe Campaign por meio de protocolos padrão da Internet, como SOAP e HTTP. O Console do cliente do Campaign centraliza todos os recursos e configurações e requer largura de banda mínima, pois depende de um cache local. Projetado para fácil implantação, o Console do cliente do Campaign pode ser implantado a partir de um navegador da Internet, atualizado automaticamente e não requer nenhuma configuração de rede específica, pois gera apenas tráfego HTTP(S).

Antes de começar, é necessário:

* Verificar a compatibilidade do sistema e das ferramentas com o Adobe Campaign na [Matriz de compatibilidade](compatibility-matrix.md)
* Obter o URL do servidor do Campaign
* Criar sua Adobe ID ou obter suas credenciais de usuário da empresa
* Instalar o Microsft Edge Webview2 Runtime no seu sistema. [Saiba mais](#webview)

## Instalar o Console do cliente{#download-ac-console}

### Microsoft Edge Webview2 Runtime {#webview}

A partir da versão de build 8.4 do Campaign Classic, a instalação do Microsoft Edge Webview 2 Runtime é necessária para qualquer instalação do Console do cliente.

A visualização da web é instalada por padrão como parte do sistema operacional Windows 11. Se ainda não estiver presente no seu sistema, o programa de instalação do Console do cliente do Campaign solicitará que você o baixe do [site do Microsoft Developer](http://www.adobe.com/go/acc-ms-webview2-runtime-download_br){target="_blank"}. Observe que o link para download não funciona no navegador Internet Explorer 11, pois a Microsoft descontinuou seu suporte. Use um navegador diferente para acessar o link.

### Baixar o console{#install-ac-console}

Ao usar o Campaign pela primeira vez, é necessário baixar o Console do cliente e instalá-lo.

Há duas opções disponíveis para baixar o Console do cliente:

1. Como admin do Campaign, conecte-se à [Distribuição de software](https://experience.adobe.com/#/downloads/content/software-distribution/en/campaign.html){target="_blank"} da Adobe.

1. Como usuário final, o(a) admin do Campaign implantará o Console do cliente para você e o disponibilizará por meio de um URL dedicado.

Depois que o programa de instalação do Console do cliente for baixado, instale-o no computador local.

Observe que não é possível alterar o idioma do Console do cliente após a instalação.

## Criar sua conexão{#create-your-connection}

Depois que o Console do cliente estiver instalado, siga as etapas abaixo para criar a conexão com o servidor de aplicativos:

1. Inicie o Console e navegue pelo link no canto direito para acessar a tela de configuração de conexão.

1. Clique em **[!UICONTROL Add > Connection]** e insira o rótulo e o URL do servidor de aplicativos do Adobe Campaign.

1. Especifique uma conexão com o servidor de aplicativos do Adobe Campaign por meio de um URL. Use um DNS, um alias do computador ou seu endereço IP.

   Por exemplo, você pode usar o URL do tipo `https://<machine>.<domain>.com`.

1. Marque a opção **[!UICONTROL Connect with an Adobe ID]**.

1. Clique em **[!UICONTROL Ok]** para salvar suas configurações.

Você pode adicionar quantas conexões forem necessárias para se conectar aos ambientes de teste, preparo e produção, por exemplo.

>[!NOTE]
>
>O botão **[!UICONTROL Add]** permite criar **[!UICONTROL folders]** para organizar todas as suas conexões. Basta arrastar e soltar cada conexão em uma pasta.

## Fazer logon no Adobe Campaign {#logon-to-ac}

Os usuários do Campaign se conectam ao console do Adobe Campaign usando a Adobe ID, por meio do Sistema de gerenciamento de identidades (IMS) da Adobe. É possível usar a mesma ID em todas as soluções da Adobe. A conexão é salva ao usar o Adobe Campaign com outras soluções. Saiba mais sobre o Adobe IMS [nesta página](https://helpx.adobe.com/br/enterprise/using/identity.html){target="_blank"}.

Para fazer logon em uma instância, siga as etapas abaixo:

1. Inicie o Console e navegue pelo link no canto direito para acessar a tela de configuração de conexão.

   ![](assets/connectToCampaign.png)

1. Selecione a instância do Campaign na qual você precisa fazer logon.

1. Clique em **[!UICONTROL Ok]**.

Em seguida, você pode fazer logon no Campaign com sua Adobe ID.

![](assets/adobeID.png)

>[!NOTE]
>
>Como o Microsoft Edge Webview2 não salva as credenciais de proxy, o Console pode solicitar que você se autentique duas vezes na primeira conexão.

## Atualizar o Console do cliente{#upgrade-ac-console}

Após atualizar o sistema para uma versão mais recente, você deve atualizar o Console do cliente para a mesma versão. Essa é uma prática recomendada e a atualização é obrigatória para algumas versões. Nesses casos, isso é mencionado nas [Notas de versão](release-notes.md).

Como usuário do Managed Cloud Services, a Adobe implanta o Console do cliente para você. Ao se conectar ao ambiente atualizado, será solicitado que você baixe a versão mais recente do Console do cliente em uma janela pop-up. Você deve aceitar e realizar a atualização do Console do cliente conforme solicitado.

>[!CAUTION]
>
>A Adobe recomenda deixar a opção **[!UICONTROL No longer ask this question]** desmarcada para garantir o envio de alertas quando uma nova versão do Console estiver disponível. Se essa opção for selecionada, o usuário não será informado de que é necessária uma atualização do Console.
>



## Conceder acesso a usuários{#grant-access}

O Adobe Campaign permite definir e gerenciar os direitos atribuídos aos diversos operadores.

Como admin do Campaign, você é responsável por criar os operadores e compartilhar suas credenciais com os usuários.

Saiba mais sobre usuários e como definir suas permissões [nesta seção](gs-permissions.md).


## Acessar o Campaign com um navegador da web {#connect-web-ac}

### Interface da web {#connect-web-ui}

A partir da versão 8.6 do Campaign, você terá acesso à nova **interface de usuário do Campaign Web**, disponível por meio do ambiente central da Adobe Experience Cloud. A Experience Cloud é a família integrada de aplicativos, produtos e serviços de marketing digital da Adobe. Com sua interface intuitiva, você pode acessar rapidamente os aplicativos em nuvem, recursos do produto e serviços. 

>[!AVAILABILITY]
>
>A interface do Campaign Web só está disponível para usuários que se conectam ao Adobe Campaign com sua Adobe ID. Saiba mais sobre o [Sistema de gerenciamento de identidades (IMS) da Adobe](https://helpx.adobe.com/br/enterprise/using/identity.html){target="_blank"}.
>

Saiba como se conectar à Adobe Experience Cloud e acessar a interface do Adobe Campaign Web [nesta página](campaign-ui.md#ac-web-ui).

Saiba mais na [documentação da interface do Adobe Campaign Web](https://experienceleague.adobe.com/pt-br/docs/campaign-web/v8/campaign-web-home){target="_blank"}.

### Acesso à web {#web-access}

Certas partes do aplicativo podem ser acessadas por meio de um navegador da web usando uma interface de HTML: relatórios, aprovação de entrega, monitoramento de instâncias e muito mais.

O acesso via web fornece uma interface semelhante ao console, mas com um conjunto reduzido de funcionalidades.

Por exemplo, para um determinado operador, uma campanha será exibida com as seguintes opções no console:

![](assets/campaign-from-console.png)

Considerando o acesso via web, as opções permitirão ver principalmente os seguintes elementos:

![](assets/campaign-from-web.png)

O acesso à web também é usado no processo de validação: os operadores podem clicar no email de solicitação de aprovação e se conectar ao Campaign por meio do navegador da web para validar ou rejeitar um conteúdo de entrega ou orçamento.

Para acessar sua instância do Campaign pela web, o URL é: `https://<your adobe campaign server>:<port number>/view/home`.
