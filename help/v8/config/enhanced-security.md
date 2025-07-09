---
title: Complemento de segurança aprimorada do Campaign
description: Introdução ao complemento de segurança aprimorada do Campaign
feature: Configuration
role: Developer
level: Experienced
exl-id: 7c586836-82e1-45fb-9c28-18361572e1fa
source-git-commit: 3f36d7c425dd5a9a13e1de7a77371b29a462dbea
workflow-type: tm+mt
source-wordcount: '727'
ht-degree: 3%

---


# Complemento de segurança aprimorada do Campaign {#enhanced-security}

Para tornar sua conexão de rede mais segura e melhorar a segurança de seus recursos, o [!DNL Adobe Campaign] oferece um novo complemento **Segurança aprimorada**.

Esse complemento inclui dois recursos do ecossistema:

* [Integração segura de Chave gerenciada pelo cliente (CMK)](#secure-cmk-integration)

* [Encapsulamento de VPN (Virtual Private Network) seguro](#secure-vpn-tunneling)

Esses recursos estão detalhados abaixo.

Algumas medidas de proteção e limitações relacionadas aos recursos de segurança aprimorados estão listadas nesta página. Além disso, verifique se todos os casos de uso de integração de Secure CMK / encapsulamento Secure VPN estão funcionando.

Depois que esses recursos forem implementados, o Adobe monitorará:

* A disponibilidade da instância e continue com o alerta se a chave não estiver disponível.

* Os túneis VPN são usados e continue com os alertas caso surja algum problema.

## Integração segura de chaves gerenciadas pelo cliente {#secure-cmk-integration}

A **integração CMK (Secure Customer-Managed Key)** permite criptografar dados em repouso usando sua própria chave por meio da conta do Amazon Web Services (AWS).

As chaves gerenciadas pelo cliente são chaves do Serviço de gerenciamento de chaves (KMS) na conta da AWS que você cria, possui e gerencia. Você tem controle total sobre essas chaves KMS e as usa para criptografar e descriptografar dados. Ao torná-lo responsável pela geração e gerenciamento de chaves de criptografia, essa capacidade permite que você tenha mais controle sobre elas, incluindo a revogação de uma chave.

>[!CAUTION]
>
>Caso revogue uma chave, você deve estar ciente dos impactos. [Saiba mais](#cmk-callouts)

Para habilitar a integração CMK com o Campaign, siga as etapas abaixo:

1. Conecte-se à sua conta do [Amazon Web Services (AWS)](https://aws.amazon.com/){target="_blank"}.

1. Gere uma chave com rotação automática ao usar o Serviço de Gerenciamento de Chaves (KMS) da AWS. [Saiba como](https://docs.aws.amazon.com/kms/latest/developerguide/create-keys.html){target="_blank"}.

1. Aplique a política fornecida a você pelo Adobe em sua conta do AWS para conceder acesso aos recursos. [Saiba mais](https://docs.aws.amazon.com/kms/latest/developerguide/key-policy-services.html){target="_blank"}. <!--link TBC-->

1. Compartilhe seu [Nome do Recurso do Amazon (chave ARN)](https://docs.aws.amazon.com/kms/latest/developerguide/find-cmk-id-arn.html){target="_blank"} com [!DNL Adobe Campaign]. Para fazer isso, entre em contato com o representante da Adobe. <!--or Adobe transition manager?-->

1. Crie e teste as regras do Amazon EventBridge para habilitar o monitoramento das chaves pelo Adobe.&#x200B; [Saiba mais](https://docs.aws.amazon.com/eventbridge/latest/userguide/eb-rules.html){target="_blank"}.


### Medidas de proteção e limitações {#cmk-callouts}

As seguintes medidas de proteção e limitações se aplicam à integração do CMK com o Adobe Campaign v8:

* A Adobe não fornece uma conta do [Amazon Web Services (AWS)](https://aws.amazon.com/){target="_blank"}. Você deve ter sua própria conta da AWS e configurá-la para gerar e compartilhar sua chave com a Adobe.

* Somente [há suporte para chaves KMS (Serviço de Gerenciamento de Chaves) do AWS](https://docs.aws.amazon.com/kms/latest/developerguide/overview.html){target="_blank"}. Nenhuma chave gerada pelo cliente fora do KMS pode ser usada.&#x200B;

* O tempo de inatividade é esperado durante a primeira configuração. &#x200B;A duração do tempo de inatividade depende do tamanho do banco de dados.

* Como cliente do, você é o proprietário e mantém a chave do. Você deve entrar em contato com a Adobe em caso de alteração na sua chave.&#x200B;

* Você pode auditar sua chave usando a [AWS CloudTrail](https://docs.aws.amazon.com/awscloudtrail/latest/userguide/cloudtrail-user-guide.html){target="_blank"} e revogá-la se necessário.&#x200B;

* Caso revogue, desative ou exclua a chave, os recursos e a instância criptografados ficarão inacessíveis até que você reverta a ação correspondente.

  >[!CAUTION]
  >
  >Se você desabilitar a chave e não reverter esta ação em 7 dias, o banco de dados só poderá ser recuperado do backup.
  >
  >Se você excluir a chave e não reverter essa ação em 30 dias, todos os seus dados serão excluídos permanentemente e serão perdidos.&#x200B;

## Túnel de Rede Virtual Privada Segura {#secure-vpn-tunneling}

O **encapsulamento de VPN (Rede Virtual Privada Segura)** é uma VPN site a site que fornece acesso seguro aos seus dados em trânsito por uma rede privada, das suas instalações à instância [!DNL Adobe Campaign].

<!--As it connects two networks together, it is a site-to-site VPN.-->

Para garantir alta disponibilidade (HA), ele usa dois túneis para evitar qualquer interrupção caso ocorra um problema em um túnel.

Há suporte para três casos de uso:

* Federated Data Access (FDA) over VPN, para acessar o banco de dados local pela instância do Campaign via VPN

* Logon de instância via VPN de um cliente thick

* Acesso SFTP da instância via VPN

>[!CAUTION]
>
>Os bancos de dados no local e na nuvem são compatíveis. [Saiba mais](#vpn-databases)

Para garantir o uso correto desse recurso, siga as diretrizes abaixo:

* Configure sua VPN lateral com base na configuração da VPN do lado do Adobe.

* Mantenha os dois túneis ativos para alta disponibilidade.

* Monitore o túnel lateral.

* Você deve ser o iniciador do túnel e estar alinhado para reiniciar a conexão se o túnel ficar inativo.

* Configure um mecanismo de repetição na sua extremidade caso ocorram falhas de conexão.

### Bancos de dados e dispositivos compatíveis {#vpn-databases}

Os seguintes bancos de dados locais são compatíveis:

* MySQL
* Netezza
* Oracle
* SAP HANA
* SQL Server
* Sybase
* Teradata
* Hadoop via HiveSQL
* PostgreSQL

Os bancos de dados em nuvem são compatíveis. Consulte a [matriz de compatibilidade](../start/compatibility-matrix.md#FederatedDataAccessFDA).

>[!NOTE]
>
>* Não há suporte para conectividade VPN com terceiros ou fornecedores externos.
>
>* VPNs adicionais gerenciadas pela Adobe para bancos de dados privados na nuvem não estão incluídas.
