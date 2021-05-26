---
solution: Campaign v8
product: Adobe Campaign
title: Saiba como se conectar ao Campaign v8
description: Conecte-se ao Campaign v8
feature: Públicos
role: Data Engineer
level: Beginner
exl-id: 176cc4f0-8827-4127-9f03-7d75ac8cf917
source-git-commit: ab7e458db5ad5696d144c17f6e89e4437a476d11
workflow-type: tm+mt
source-wordcount: '756'
ht-degree: 10%

---

# Conecte-se ao Adobe Campaign v8{#gs-ac-connect}

O Console do Cliente do Campaign é um cliente avançado que permite a conexão com o(s) servidor(es) de aplicativos do Campaign.

Antes de começar, é necessário:

* Verifique a compatibilidade do sistema e das ferramentas com o Adobe Campaign na [Matriz de Compatibilidade](compatibility-matrix.md)
* Obter o URL do servidor do Campaign
* Obter suas credenciais de usuário

## Baixe e instale o Console do cliente

Ao usar o Campaign pela primeira vez ou se precisar atualizar para uma versão mais recente, é necessário baixar o Console do cliente e instalá-lo.

Estão disponíveis duas opções:

1. Como administrador do Campaign, conecte-se ao Adobe [Software Distribution](https://experience.adobe.com/#/downloads/content/software-distribution/encampaign.html) e baixe o programa de instalação do Console do Cliente. Em seguida, você pode instalá-lo em sua máquina local.

1. Como usuário final, o Adobe pode implantar o Console para você: depois que o Console for atualizado, você será solicitado a baixar a versão mais recente do Console do cliente em uma janela pop-up.

>[!CAUTION]
>
>O Adobe recomenda deixar a opção **[!UICONTROL No longer ask this question]** desmarcada para garantir que todos os usuários sejam alertados quando uma nova versão do Console estiver disponível.  Se essa opção for selecionada, o usuário não será informado sobre novas versões disponíveis.

## Criar a conexão

Depois que o Console do cliente for recém-instalado, siga as etapas abaixo para criar a conexão com o servidor de aplicativos:

1. Inicie o Console no menu **[!UICONTROL Start]** do Windows, no grupo de programas **Adobe Campaign**.

1. Clique no link no canto superior direito dos campos de credenciais para acessar a janela de configuração da conexão.

1. Clique em **[!UICONTROL Add > Connection]** e insira o rótulo e o URL do servidor de aplicativos do Adobe Campaign.

1. Especifique uma conexão com o servidor de aplicativos do Adobe Campaign por meio de um URL. Use um DNS ou um alias da máquina ou seu endereço IP.

   Por exemplo, você pode usar o URL tipo [`https://<machine>.<domain>.com`](https://myserver.adobe.com).

1. Se o Adobe Identity Management System (IMS) estiver configurado para sua organização, marque a opção **[!UICONTROL Connect with an Adobe ID]** .

1. Clique em **[!UICONTROL Ok]** para salvar suas configurações.

Você pode adicionar quantas conexões forem necessárias para se conectar aos ambientes de teste, estágio e produção, por exemplo.

>[!NOTE]
>
>O botão **[!UICONTROL Add]** permite criar **[!UICONTROL folders]** para organizar todas as suas conexões. Basta arrastar e soltar cada conexão em uma pasta.

## Faça logon no Adobe Campaign

Para fazer logon em uma instância existente, siga as etapas abaixo:

1. Inicie o Console no menu **[!UICONTROL Start]** do Windows, no grupo de programas **Adobe Campaign**.

1. Clique no link no canto superior direito dos campos de credenciais para acessar a janela de configuração da conexão.

1. Selecione a instância do Campaign na qual você precisa fazer logon.

1. Clique em **[!UICONTROL Ok]**.

1. Insira suas credenciais de logon de usuário e clique em **[!UICONTROL LOG IN]**.

   ![](assets/sign-in-v8.png)

Dependendo da configuração, suas credenciais podem ser:

* fornecido pelo administrador do Campaign que concedeu acesso a você
* seu Adobe ID

## Conceder acesso aos usuários

O Adobe Campaign permite definir e gerenciar os direitos atribuídos aos diversos operadores. Veja um conjunto de direitos e restrições que autorizam ou negam:

* Acesso a certas funcionalidades (por meio dos direitos nomeados),
* Acesso a certos elementos,
* Criar, modificar e/ou excluir elementos (delivery, contatos, campanhas, grupos, etc.).

Saiba mais sobre usuários e como definir suas permissões em [esta seção](permissions.md).

Como administrador do Campaign, você é responsável por criar os operadores e compartilhar suas credenciais com os usuários.

## Conecte-se ao Campaign com seu Adobe ID{#connect-ims}

Os usuários do Campaign podem se conectar ao console do Adobe Campaign usando sua Adobe ID, por meio do Adobe Identity Management System (IMS). Essa implementação oferece as seguintes vantagens:

* A mesma ID pode ser usada para todas as soluções Experience Cloud.
* Ao usar o Adobe Campaign com diferentes integrações, a conexão é memorizada.
* Política de gerenciamento de senhas mais forte.
* Uso de contas de Federated ID (provedor de ID externo).

:voice_balloon: Como um usuário do Managed Cloud Services, [entre em contato com o Adobe](campaign-faq.md#support) para implementar o Adobe IMS com o Campaign.

## Conecte-se ao Campaign com seu logon LDAP

O Adobe Campaign pode ser configurado para que o usuário acesse a plataforma por meio de sua autenticação LDAP.

:voice_balloon: Como um usuário do Managed Cloud Services, [entre em contato com o Adobe](campaign-faq.md#support) para configurar a integração LDAP com o Campaign.


## Acesso à Web{#web-access}

Certas partes do aplicativo podem ser acessadas por um navegador da Web simples usando uma interface de usuário HTML: Painel de campanha, relatório de Cubo, monitoramento de instância e muito mais.

[!DNL :arrow_upper_right:] Saiba mais sobre o acesso à Web na documentação do  [Campaign Classic v7](https://experienceleague.adobe.com/docs/campaign-classic/using/getting-started/starting-with-adobe-campaign/campaign-workspace/adobe-campaign-workspace.html?lang=en#console-and-web-access)

O acesso à Web também é usado para no processo de validação: Os operadores podem clicar no email de solicitação de aprovação e se conectar ao Campaign por meio de seu navegador da Web para validar ou rejeitar um conteúdo ou orçamento de delivery.

[!DNL :arrow_upper_right:] Saiba como configurar e gerenciar aprovações na documentação do  [Campaign Classic v7](https://experienceleague.adobe.com/docs/campaign-classic/using/orchestrating-campaigns/orchestrate-campaigns/marketing-campaign-approval.html?lang=en#orchestrating-campaigns)
