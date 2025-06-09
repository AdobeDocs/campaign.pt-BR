---
product: campaign
title: Nota técnica - Guia de rotação de credenciais
description: Nota técnica da Adobe Campaign - Guia de rotação de credenciais
hide: true
hidefromtoc: true
exl-id: 0848ee2d-3506-4167-9aea-a1589aa82805
source-git-commit: 14e49a0b4de1b82239113bd670213449f464c27f
workflow-type: tm+mt
source-wordcount: '324'
ht-degree: 1%

---

# Nota técnica: Guia de rotação de credenciais {#ac-customer-credentials}

Como cliente do, você é responsável pela substituição de suas credenciais por um novo conjunto periodicamente para reduzir o risco de comprometimento.

## Credenciais de opções do Adobe Campaign {#ac-options-credentials}

No Adobe Campaign Explorer, o nó **Administration > Platform > Options** permite fazer correções nas opções do Adobe Campaign. Se você armazenou algumas credenciais aqui, gire-as.

![](assets/technote-2.png)

## Credenciais da conta externa {#ac-accounts-credentials}

O nó **Administration > Platform > External Accounts** permite fazer correções nas contas externas do Adobe Campaign.

Gire todas as suas credenciais salvas nas contas externas.

>[!CAUTION]
>
>**Não** modifique as credenciais gerenciadas do Adobe. Nenhuma conta externa com o servidor relacionado `adobe` deve ser modificada.

![](assets/technote-1.png)

Para os operadores técnicos `mc*` (ex: mc1, mc2, etc.) e `Interaction*` (ex: interação1, interação2, etc.) específicos, qualquer uma das duas abordagens abaixo pode ser seguida:

1. O Adobe pode alterar as credenciais desses operadores e compartilhá-las com você. Observe que todas as integrações que usam esses operadores deixarão de funcionar até que as credenciais desses operadores sejam atualizadas.

1. O Adobe pode criar **novos** operadores correspondentes a cada operador existente e compartilhá-los com você. O Adobe excluirá todas as ocorrências de operadores antigos depois que você alternar para esses novos operadores.


## Chave privada/certificado do Mobile Services  {#ac-key-credentials}

Para obter a rotação das chaves privadas e do certificado relacionados aos serviços móveis, consulte os links abaixo.

* Para o Android, consulte [esta documentação](https://experienceleague.adobe.com/en/docs/campaign-classic/using/sending-messages/sending-push-notifications/configure-the-mobile-app/configuring-the-mobile-application-android){target="_blank"}.
Navegue até a seção **Criar o aplicativo Android para dispositivos móveis > Configurar a API versão**.

* Para o iOS, consulte [esta documentação](https://experienceleague.adobe.com/en/docs/campaign-classic/using/sending-messages/sending-push-notifications/configure-the-mobile-app/configuring-the-mobile-application){target="_blank"}.
Navegue até a seção **Criar aplicativo móvel iOS->Modo de autenticação**.

## Chaves GPG {#ac-gpg-credentials}

Para a rotação das chaves GPG, as seguintes etapas precisam ser seguidas:

1. Descriptografar os dados existentes usando a chave existente. [Saiba mais](https://experienceleague.adobe.com/en/docs/control-panel/using/instances-settings/gpg-keys-management#decrypting-data){target="_blank"}.

1. Crie um novo par de chaves GPG. Saiba mais sobre o gerenciamento de chaves GPG em [esta documentação](https://experienceleague.adobe.com/en/docs/control-panel/using/instances-settings/gpg-keys-management#decrypting-data){target="_blank"}.

1. Substitua o uso existente da chave GPG em todos os fluxos de trabalho pela chave recém-criada.

1. Exclua a chave GPG existente.
