---
title: Complemento de segurança aprimorado
description: Introdução ao complemento de segurança aprimorada do Campaign
feature: Configuration
role: Developer
level: Experienced
hide: true
hidefromtoc: true
exl-id: 7c586836-82e1-45fb-9c28-18361572e1fa
source-git-commit: f9b064dffa0f8792e8653760cb2ac44cfdf43848
workflow-type: tm+mt
source-wordcount: '696'
ht-degree: 1%

---

# Complemento de segurança aprimorado {#enhanced-security}

Para tornar sua conexão de rede mais segura e oferecer maior segurança para seus recursos, [!DNL Adobe Campaign] oferece um novo **Segurança aprimorada** complementar.

Esse complemento inclui dois recursos do ecossistema:

* [Integração segura do CMK](#secure-cmk-integration)

* [Encapsulamento de VPN seguro](#secure-vpn-tunneling)

Esses recursos estão detalhados abaixo.

## Integração segura do CMK {#secure-cmk-integration}

A variável **Integração segura de Chave gerenciada pelo cliente (CMK)** O permite criptografar sua instância e dados usando sua própria chave por meio da conta do Amazon Web Services (AWS).

As chaves gerenciadas pelo cliente são chaves do Serviço de gerenciamento de chaves (KMS) na conta da AWS que você cria, possui e gerencia. Você tem controle total sobre essas chaves KMS e as usa para criptografar e descriptografar dados. Ao torná-lo responsável pela geração e gerenciamento de chaves de criptografia, essa capacidade permite que você tenha mais controle sobre elas, incluindo a revogação de uma chave.

>[!CAUTION]
>
>Caso revogue uma chave, você deve estar ciente dos impactos. [Saiba mais](#cmk-callouts)

Para habilitar a integração CMK com o Campaign, siga as etapas abaixo:

1. Conecte-se ao seu [Amazon Web Services (AWS)](https://aws.amazon.com/){target="_blank"} conta.

1. Gere uma chave com rotação automática ao usar o Serviço de Gerenciamento de Chaves (KMS) da AWS. [Saiba como](https://docs.aws.amazon.com/kms/latest/developerguide/create-keys.html){target="_blank"}.

1. Aplique a política fornecida pelo Adobe à sua conta do AWS para conceder acesso aos seus recursos. [Saiba mais](https://docs.aws.amazon.com/kms/latest/developerguide/key-policy-services.html){target="_blank"}. <!--link TBC-->

1. Compartilhe seu [Nome do recurso Amazon (chave ARN)](https://docs.aws.amazon.com/kms/latest/developerguide/find-cmk-id-arn.html){target="_blank"} com [!DNL Adobe Campaign]. Para fazer isso, entre em contato com o representante da Adobe. <!--or Adobe transition manager?-->

1. Crie e teste as regras do Amazon EventBridge para habilitar o monitoramento das chaves por Adobe&#x200B; [Saiba mais](https://docs.aws.amazon.com/eventbridge/latest/userguide/eb-rules.html){target="_blank"}.

## Encapsulamento de VPN seguro {#secure-vpn-tunneling}

A variável **Encapsulamento de VPN (Virtual Private Network) seguro** O é uma VPN site a site que fornece acesso seguro aos seus dados em trânsito por uma rede privada, das suas instalações à [!DNL Adobe Campaign] instância.

<!--As it connects two networks together, it is a site-to-site VPN.-->

Para garantir alta disponibilidade (HA), ele usa dois túneis para evitar qualquer interrupção caso ocorra um problema em um túnel.

Há suporte para três casos de uso:

* Federated Data Access (FDA) via VPN<!--to access your on-premise database from the Campaign instance over VPN-->

* Logon de instância via VPN de um cliente thick

* Acesso SFTP da instância via VPN

>[!CAUTION]
>
>Somente bancos de dados locais e dispositivos VPN compatíveis com o AWS são suportados. [Saiba mais](#vpn-callouts)

Para garantir o uso correto desse recurso, siga as diretrizes abaixo:

* Configure sua VPN lateral com base na configuração da VPN do lado do Adobe.

* Mantenha os dois túneis ativos para alta disponibilidade.

* Monitore o túnel lateral.

* Você deve ser o iniciador do túnel e estar alinhado para reiniciar a conexão se o túnel ficar inativo.

* Configure um mecanismo de repetição na sua extremidade caso ocorram falhas de conexão.

## Medidas de proteção {#callouts}

Algumas medidas de proteção e limitações relacionadas aos recursos de segurança aprimorados estão listadas abaixo.

* Certifique-se de que todos os casos de uso de integração de Secure CMK / encapsulamento Secure VPN estejam funcionando.

<!--* Adobe shall reach out to you or your technical team if any issue is found on your side.

* Currently, when using Enhanced security features, any communication with Adobe must be performed manually via email.-->

* O Adobe monitorará:

   * A disponibilidade da instância e continue com o alerta se a chave não estiver disponível.

   * Os túneis VPN são usados e continue com os alertas caso surja algum problema.

### Proteções de integração CMK segura {#cmk-callouts}

* O Adobe não fornece uma conta AWS. Você deve ter sua própria conta da AWS e configurá-la para gerar e compartilhar sua chave com o Adobe.

* Somente [Serviço de Gerenciamento de Chaves da AWS](https://docs.aws.amazon.com/kms/latest/developerguide/overview.html){target="_blank"} (KMS) são compatíveis. Nenhuma chave gerada pelo cliente fora do KMS pode ser usada.&#x200B;

* Algum tempo de inatividade será envolvido na primeira configuração. &#x200B;A duração do tempo de inatividade dependerá do tamanho do banco de dados.

* Como você é o proprietário e mantém a chave, entre em contato com o Adobe em caso de alteração na chave&#x200B;

* Você pode auditar sua chave usando [AWS CloudTrail](https://docs.aws.amazon.com/awscloudtrail/latest/userguide/cloudtrail-user-guide.html){target="_blank"} e revogá-la, se necessário&#x200B;

* Caso revogue, desative ou exclua a chave, os recursos e a instância criptografados ficarão inacessíveis até que você reverta a ação correspondente.

  >[!CAUTION]
  >
  >Se você desabilitar a chave e não reverter esta ação em 7 dias, o banco de dados só poderá ser recuperado do backup.
  >
  >Se você excluir a chave e não reverter essa ação em 30 dias, todos os seus dados serão excluídos permanentemente e serão perdidos.&#x200B;

### Proteções de encapsulamento VPN seguro {#vpn-callouts}

* Atualmente, somente os bancos de dados locais são compatíveis, como<!--Richa to check the list with PM-->:

   * MySQL
   * Netezza 
   * Oracle 
   * SAP HANA 
   * SQL Server 
   * Sybase 
   * Teradata 
   * Hadoop via HiveSQL

* Somente dispositivos VPN compatíveis com o AWS são suportados. Uma lista de dispositivos compatíveis está disponível em [esta página](https://docs.aws.amazon.com/vpn/latest/s2svpn/your-cgw.html#example-configuration-files){target="_blank"}<!--check which list should be communicated-->.

* Não há suporte para conectividade VPN com terceiros ou fornecedores externos.

* VPNs adicionais gerenciadas por Adobe para bancos de dados privados na nuvem não estão incluídas.
