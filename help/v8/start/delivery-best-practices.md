---
title: Práticas recomendadas de entrega
description: Saiba mais sobre as práticas recomendadas ao projetar e enviar deliveries com o Adobe Campaign
feature: Email, Push, SMS, Direct Mail
role: User
level: Beginner
version: Campaign v8, Campaign Classic v7
exl-id: cb6094eb-0010-4c62-9589-3b52fd60c2c2
source-git-commit: 7bfe0ac7ba99ebf26844d2cea14a75f32ecb8b74
workflow-type: tm+mt
source-wordcount: '3068'
ht-degree: 64%

---

# Práticas recomendadas de entrega {#delivery-best-practices}

Leia as seguintes práticas recomendadas com os recursos de delivery do Campaign.

## Otimizar a entrega {#optimize-delivery}

Antes mesmo de começar a criar os deliveries, você pode realizar várias ações para proteger e otimizar o fluxo do processo de envio. A seção a seguir descreve as práticas recomendadas e os procedimentos recomendados para a configuração ideal do Adobe Campaign.

### Desempenho da plataforma

Vários fatores podem afetar diretamente o desempenho do servidor e retardar sua plataforma do Campaign:

* O número e o tipo de elementos [personalização](../send/personalize.md): a personalização em emails extrai dados do banco de dados para cada destinatário. no caso de muitos elementos de personalização, a quantidade de dados necessária para preparar o delivery é maior. Isso pode tornar sua plataforma lenta. Saiba mais sobre as medidas de proteção de personalização em [esta seção](../send/personalize.md#perso-guardrails).

* A carga do servidor: quando o servidor de marketing estiver lidando com várias tarefas diferentes ao mesmo tempo, o desempenho poderá ser retardado. O servidor de marketing precisa coordenar todos os dados de entrada e saída de todos os deliveries para garantir que os dados estejam corretos no momento correto.
Para evitar isso, coordene a programação de deliveries com os outros membros da equipe, garantindo um melhor desempenho.

* A execução do fluxos de trabalho: o monitoramento de seus fluxos de trabalho é essencial para evitar problemas de desempenho na plataforma. Siga as diretrizes listadas [neste documento](../../automation/workflow/workflow-best-practices.md#execution-and-performance).

* Conecte-se aos seus [recursos do Painel de Controle do Campaign](https://experienceleague.adobe.com/en/docs/control-panel/using/discover-control-panel/key-features){target="_blank"} para monitorar sua plataforma, usando as funcionalidades de [monitoramento de desempenho](https://experienceleague.adobe.com/en/docs/control-panel/using/performance-monitoring/about-performance-monitoring){target="_blank"}.

#### Gerenciamento de quarentena {#quarantine-management}

É de seu interesse manter bons processos de gerenciamento de quarentena.

Ao começar a enviar e-mails em uma nova plataforma, você pode usar uma lista de endereços que não são totalmente qualificados. Se você enviar para endereços inválidos ou endereços honeypot (caixas de correio criadas apenas para enganar spammers), a reputação da sua plataforma será afetada. Bons processos de gerenciamento de quarentena ajudam a manter a qualidade do endereço, evitar a lista de bloqueios de provedores de acesso à internet, reduzir a taxa de erro acelerando as entregas e a taxa de transferência.


Saiba mais sobre como iniciar uma nova plataforma no [Manual de práticas recomendadas de capacidade de delivery do Adobe](https://experienceleague.adobe.com/en/docs/deliverability-learn/deliverability-best-practice-guide/additional-resources/campaign/ac-starting-new-platform){target="_blank"}.

As recomendações técnicas estão listadas em [esta seção](https://experienceleague.adobe.com/en/docs/deliverability-learn/deliverability-best-practice-guide/additional-resources/campaign/acc-technical-recommendations){target="_blank"}.


+++ **Leia algumas práticas recomendadas**

* Se você tiver uma lista de endereços inválidos, a Adobe recomenda importá-la para a tabela de quarentena, por meio de **[!UICONTROL Administration]** > **[!UICONTROL Campaign Management]** > **[!UICONTROL Non deliverables Management]** > **[!UICONTROL Non deliverables and addresses]**.

* Os destinatários cujos endereços estão em quarentena são excluídos por padrão durante a análise de entrega: não são direcionados. Isso acelera os deliveries, pois a taxa de erro tem um efeito significativo na velocidade do delivery. Um endereço de email pode ser colocado em quarentena, por exemplo, quando a caixa de entrada estiver cheia ou se o endereço não existir.
O Adobe Campaign gerencia endereços incorretos de acordo com o tipo de erro retornado. [Saiba mais sobre quarentenas](../send/quarantines.md)

* Alguns provedores de acesso à Internet consideram automaticamente emails como spam se a taxa de endereços inválidos for muito alta. A quarentena, portanto, evita que você seja adicionado à lista de bloqueios por esses provedores.

+++

### Entrega e manutenção {#delivery-maintenance}

A manutenção regular de seus deliveries é essencial para o desempenho ideal da plataforma.

+++ **Leia algumas práticas recomendadas**

* **Remover entregas com falha e desnecessárias**: não mantenha as entregas em estado de falha na instância, pois isso mantém tabelas temporárias e afeta o desempenho. Remova regularmente deliveries que não são mais necessários para liberar recursos do sistema.

* **Limpar destinatários inativos**: destinatários inativos nos últimos 12 meses devem ser removidos do banco de dados para manter a qualidade do endereço. Os ISPs desativam endereços após um período de inatividade e as mensagens com rejeição são enviadas aos remetentes para informá-los sobre esse novo status. A limpeza regular de listas melhora a capacidade de entrega e reduz os custos.

* **Agende deliveries grandes sabiamente**: não agende deliveries grandes juntos. Coordene a programação de deliveries com os outros membros da equipe para distribuir a carga uniformemente pelo sistema. Quando vários deliveries grandes estão sendo enviados simultaneamente, isso pode afetar o desempenho geral da plataforma.

+++

### Mecanismo de dupla aceitação {#double-opt-in}

Para evitar o envio de mensagens para endereços inválidos, limitar as comunicações inadequadas e melhorar a reputação do remetente, a Adobe recomenda a implementação de um mecanismo de aceitação de duplicação para confirmação pós-subscrição. Isso ajuda a garantir que um destinatário seja inscrito intencionalmente.

## Usar modelos {#use-templates}

Os modelos da entrega oferecem mais eficiência ao fornecer cenários prontos para os tipos mais comuns de atividades. Com modelos, os profissionais de marketing podem implantar novas campanhas com personalização mínima em um período de tempo menor. [Saiba mais sobre modelos de entrega](../send/create-templates.md).

### Subdomínios e marcas {#subdomains-and-branding}

Quando você gerencia várias marcas no Adobe Campaign, a Adobe recomenda ter um subdomínio por marca. Por exemplo, um banco pode ter vários subdomínios correspondentes a cada uma de suas agências regionais. Se um banco for proprietário do domínio bluebank.com, seus subdomínios podem ser @ny.bluebank.com, @ma.bluebank.com, @ca.bluebank.com, etc. Ter um template do delivery por subdomínio permite usar sempre os parâmetros pré-configurados certos para cada marca, o que evita erros e economiza tempo. Saiba mais sobre a identidade visual do subdomínio na [documentação do Painel de Controle do Campaign](https://experienceleague.adobe.com/en/docs/control-panel/using/subdomains-and-certificates/subdomains-branding){target="_blank"}.

### Configurar endereços {#configure-addresses}

Certifique-se de aplicar as seguintes diretrizes:

* O endereço do remetente é obrigatório para o envio de um email. Alguns ISPs (provedores de serviço de internet) verificam a validade do endereço do remetente antes de aceitarem mensagens.
* Um endereço formado incorretamente pode resultar na rejeição pelo servidor de recebimento. Você precisa ter certeza de que o endereço informado está correto.
* O endereço deve identificar explicitamente o remetente. O domínio deve ser de propriedade e registrado pelo remetente.
* A Adobe recomenda a criação de contas de email que correspondam aos endereços especificados para entrega e respostas. Verifique com o administrador do sistema de mensagens.

+++ **Etapas para configurar endereços na interface do Campaign**

Para configurar endereços na interface do Campaign, siga os passos abaixo:

1. No [modelo da entrega](../send/create-templates.md), clique no link **[!UICONTROL From]**. Na janela **[!UICONTROL Email header parameters]**, insira as configurações.

1. No campo **[!UICONTROL Sender address]**, verifique se o domínio de endereço é o mesmo que o subdomínio que você delegou à Adobe. Você pode alterar a parte anterior a “@&#39;” mas não o endereço do domínio.

1. No campo **[!UICONTROL From]**, use um nome facilmente identificável pelos destinatários, como o nome da sua marca, para aumentar a taxa de abertura das entregas. Para melhorar ainda mais a experiência do destinatário, você pode adicionar o nome de uma pessoa, por exemplo “Emma da Megastore”.

1. Nos campos **[!UICONTROL Reply address text]**, o endereço do remetente é usado por padrão para respostas. No entanto, a Adobe recomenda o uso de um endereço real, como o atendimento ao cliente da sua marca. Nesse caso, se um destinatário enviar uma resposta, o atendimento ao cliente poderá resolvê-lo.

+++

### Configurar um grupo de controle {#set-up-control-group}

Depois que a entrega é enviada, você pode comparar o comportamento dos destinatários excluídos com os destinatários que receberam a entrega. Você pode então medir a eficiência de suas campanhas. Saiba mais sobre grupos de controle [nesta seção](../../automation/campaigns/marketing-campaign-target.md#add-a-control-group).

### Usar tipologias para aplicar filtros ou regras de controle {#create-typologies}

Uma tipologia contém regras de verificação aplicadas durante a fase de análise, antes de enviar qualquer mensagem.

Na guia **[!UICONTROL Typology]** das propriedades do modelo, você pode selecionar uma tipologia personalizada, se necessário.

Por exemplo, para controlar melhor o tráfego de saída, você pode definir quais endereços IP podem ser usados, estabelecendo uma afinidade por subdomínio e criando uma tipologia por afinidade. As afinidades são definidas no arquivo de configuração da instância. Entre em contato com o administrador do Adobe Campaign.

Para obter mais informações sobre tipologias, consulte [esta seção](../../automation/campaign-opt/campaign-typologies.md).

## Otimizar seu conteúdo {#optimize-content}

### Criar conteúdo personalizado {#perso-content}

Para personalizar suas mensagens, você pode usar os dados dos recipients armazenados no banco de dados ou coletados por meio de rastreamento, landing pages, assinaturas, etc. As noções básicas de personalização são apresentadas [nesta seção](../send/personalize.md).

+++ **Leia algumas práticas recomendadas**

* Verifique as configurações de personalização - verifique se o conteúdo da sua mensagem foi projetado corretamente para evitar erros que possam estar relacionados à personalização. Uma tag de personalização do Adobe Campaign sempre tem o seguinte formato: `<%=table.field%>`. O uso incorreto de parâmetros em blocos de personalização pode ser um problema. Por exemplo, as variáveis em JavaScript devem ser usadas da seguinte forma:

  ``
  <%
  var brand = "xxx"
  %>
  ``

  Para obter mais informações sobre blocos de personalização, consulte [esta seção](../send/personalization-blocks.md).

* Preparar dados de personalização - Você pode preparar dados de personalização em um workflow para melhorar a análise de preparação de delivery. Isso deve ser usado se os dados de personalização vierem de uma tabela através do Federated Data Access (FDA). Esta opção está descrita nesta [seção](../send/personalization-data.md#optimize-personalization)
+++

### Criar conteúdo otimizado {#build-optimized-content}

Ao criar seus emails, aplique as práticas recomendadas gerais para conteúdo de email.

+++ **Leia algumas práticas recomendadas**

* Mantenha o design simples

* Lembre-se dos usuários de dispositivos móveis

* Evite criar emails só com imagens

* Use fontes seguras para emails

* Codifique caracteres especiais

+++


### Linha de assunto  {#subject-line-check}

Trabalhe na [linha de assunto](../send/personalization-fields.md#personalization-fields-uc) do email para melhorar as taxas de abertura.


+++ **Leia algumas práticas recomendadas**


* Evite assuntos muito longos. Use no máximo 50 caracteres

* Evite usar palavras repetitivas como “grátis” ou “oferta”, que podem ser consideradas spam

* Evite letras maiúsculas

* Não use caracteres especiais como &quot;!&quot;, &quot;£&quot;, &quot;€&quot;, &quot;$&quot;

+++

### Mirror page {#mirror-page-check}

Sempre inclua um link de mirror page. A posição preferencial é a parte superior do email. Saiba mais sobre a mirror page em [esta página](../send/mirror-page.md)

### Link de unsubscription {#unsub-link-check}

O link de unsubscription é essencial. Deve ser visível e válido e o formulário deve ser funcional. Por padrão, quando a mensagem é analisada, uma **[!UICONTROL Unsubscription link approval]** [regra de tipologia](../../automation/campaign-opt/control-rules.md) interna verifica se um link para opção de não participação foi incluído e gera um aviso caso ele esteja ausente.

Saiba como inserir um link para opção de não participação [nesta seção](../send/personalization-blocks.md)

+++ **Aplicar esta prática recomendada**

Como o erro humano é sempre possível, verifique se o link para opção de não participação funciona corretamente antes de cada envio. Por exemplo, ao enviar a prova, verifique se o link é válido, se o formulário está online e se o campo `No longer contact this recipient ` foi alterado para `Yes`.

+++

### Tamanho do email {#email-size-check}

Para evitar problemas de desempenho ou de entrega, o tamanho máximo recomendado de um email é de aproximadamente **35 KB**. Para verificar o tamanho da mensagem, navegue pela guia **[!UICONTROL Preview]** e escolha um perfil de teste. Depois de gerada, o tamanho da mensagem é exibido no canto superior direito.


+++ **Leia algumas práticas recomendadas**

* Remover estilos redundantes ou em desuso

* Mover um conteúdo de email para uma página de destino

* Minimizar o uso de código

Certifique-se de que testou as alterações antes do envio final.

+++


### Duração do SMS {#sms-length-check}

Por padrão, o número de caracteres em um SMS atende aos padrões do GSM (Global System for Mobile Communications). As mensagens SMS que usam a codificação GSM são limitadas a 160 caracteres ou a 153 caracteres por SMS para as mensagens enviadas em várias partes.


+++ **Leia algumas práticas recomendadas**

* Para manter todos os caracteres inalterados nas mensagens SMS, a fim de não alterar os nomes próprios por exemplo, não habilite a transliteração.

* No entanto, se suas mensagens SMS contiverem muitos caracteres que não forem considerados pelo padrão GSM, habilite a transliteração para limitar os custos de envio das mensagens. Saiba mais [nesta seção](../send/sms/smpp-external-account.md#smpp-transliteration).

* Você pode aplicar a transliteração de SMS, que consiste em substituir um caractere de um SMS por outro quando esse caractere não é considerado pelo padrão GSM. Observe que a inserção de campos de personalização no conteúdo da mensagem SMS pode inserir caracteres que não são considerados pela codificação GSM. Como Administrador do Campaign, você pode habilitar a transliteração de caracteres marcando a caixa correspondente na guia Configurações do canal SMPP do **[!UICONTROL External account]** correspondente. [Saiba mais](../send/sms/smpp-external-account.md#smpp-transliteration)

+++

### Evitar anexos

Os anexos continuam sendo um dos vetores mais comuns para a proliferação de malware, principalmente quando enviados em massa. Inclua um link seguro no documento em vez de anexá-lo. Isso garante uma camada adicional de segurança para impedir a redistribuição não intencional e reduz amplamente a chance de a mensagem ser rejeitada em gateways de entrada de email devido ao tamanho da mensagem ou por questões de segurança.

<!--
## Work on formatting {#formatting}

To avoid common formatting errors, check the following elements:

* Correct **date formatting**: Adobe Campaign provides date formatting functions for the JavaScript templates and XSL stylesheets. [Learn more](formatting.md#date-display)

* Usage of **authorized characters** in emails: the list of valid characters for email addresses is defined in the "XtkEmail_Characters" option. Learn how to access Campaign options [in this section](../../installation/using/configuring-campaign-options.md). To correctly handle special characters, Adobe Campaign needs to be installed in Unicode. 

* Configuration of **Email Authentication**: make sure that the email headers contain the DKIM signature. DKIM (Domain Keys Identified Mail) authentication allows the receiving email server to verify that a message was indeed sent by the person or entity it claims it was sent by, and whether the message content was altered in between the time it was originally sent (and DKIM "signed") and the time it was received. This standard typically uses the domain in the From or Sender header. For more on this, refer to the [Adobe Deliverability Best Practice Guide](https://experienceleague.adobe.com/docs/deliverability-learn/deliverability-best-practice-guide/transition-process/infrastructure.html#authentication).-->

## Gerenciamento de imagens {#manage-images}

Estas são algumas diretrizes específicas para otimizar imagens para sua campanha de marketing por email.

### Impedir o bloqueio de imagens {#image-blocking}

Alguns clientes de email bloqueiam imagens por padrão, e os usuários podem alterar suas configurações para bloquear imagens para salvar no uso de dados.  Portanto, se as imagens não forem baixadas, a mensagem inteira poderá ser perdida.

+++ Para evitar isso, é possível aplicar essas práticas recomendadas

* Evite emails totalmente baseados em imagens. Equilibre o conteúdo com imagem e texto.

* Se o texto precisa estar contido em uma imagem, use alt e title para garantir que sua mensagem seja exibida. Estilize o texto alt/title para melhorar a aparência.

* Evite o uso de imagens de fundo, pois elas não são suportadas por alguns clientes de e-mail.
+++

### Tornar as imagens responsivas {#responsive-images}

Tente tornar as imagens responsivas e redimensionáveis para torná-las visíveis em todos os contextos e dispositivos. Observe que isso pode ter um impacto no custo, pois demora mais para ser criado.

### Usar referência de imagem absoluta {#absolute-images}

Para serem acessadas de fora, as imagens usadas em emails e recursos públicos vinculados a campanhas devem estar presentes em um servidor acessível externamente.

* No assistente de entrega, você pode importar uma página HTML que contenha imagens ou inserir imagens diretamente usando o editor de HTML por meio do ícone **[!UICONTROL Image]**.

* Caso as imagens não sejam exibidas, verifique se elas estão disponíveis no servidor. Para fazer isso, navegue até a guia **Source** da sua entrega. Localize suas imagens e copie e cole o URL de cada imagem em um navegador da web. Caso as imagens não sejam exibidas, entre em contato com o administrador de TI ou fornecedor terceirizado e disponibilize seu conteúdo de entrega.

### Pré-visualizar e testar a mensagem {#preview-msg}

A Adobe recomenda visualizar a mensagem para verificar a personalização e como os destinatários verão a entrega.

No assistente de entrega, a subguia **[!UICONTROL Preview]** permite visualizar a renderização de cada conteúdo para um destinatário. Os campos de personalização e os elementos condicionais do conteúdo são substituídos pelas informações correspondentes para o perfil selecionado. [Saiba mais](../send/preview-and-proof.md).


<!--
*  An automatic anti-spam checking is performed during each preview. In the **[!UICONTROL Preview]** sub-tab, check [SpamAssassin](spamassassin.md) spam scoring.  Click **[!UICONTROL More...]** to find out more about the warning.  Before doing so, make sure SpamAssassin is correctly installed and configured on the Adobe Campaign application server. [Learn more](../../installation/using/configuring-spamassassin.md)
-->

## Definir o público-alvo correto {#define-the-right-audience}

A população de destino é fundamental: crie suas listas cuidadosamente, teste seus emails em clientes de email populares e dispositivos móveis e verifique se suas listas de email estão atualizadas (sem endereços desconhecidos ou obsoletos). Você também pode enviar provas que ajudam a configurar um ciclo de validação completo. Saiba mais sobre públicos-alvo [nesta seção](../audiences/gs-audiences.md).

### Direcionar ao público-alvo correto {#target-the-right-audience}

Quando seu conteúdo estiver pronto, será necessário definir com cuidado quem receberá sua mensagem.

Para que sua entrega seja bem-sucedida, o conteúdo personalizado mais relevante deve ser enviado aos destinatários corretos. O Adobe Campaign permite criar o público mais preciso: você pode selecionar os destinatários de acordo com a idade, localização, o que compraram, se clicaram em um link em uma entrega anterior, etc. Com o Adobe Campaign, também é possível definir perfis de teste, grupos de controle e endereços de seed para verificar se o público-alvo está correto.

### Direcionar mapeamentos {#target-mappings}

No Campaign, por padrão, os modelos de entrega visam **Destinatários**. O Adobe Campaign oferece outros target mappings para seus deliveries, que podem ser alterados conforme suas necessidades. Você pode, por exemplo, entregar deliveries a visitantes cujos perfis tenham sido coletados nas redes sociais, ou a visitantes que estejam inscritos em um serviço de informação.

Esses mapeamentos são apresentados [nesta seção](../audiences/target-mappings.md).

### Destinatários externos {#external-recipients}

Você pode enviar entregas para destinatários armazenados em um arquivo externo em vez de salvos no banco de dados. Saiba mais [nesta seção](create-message.md#select-external-recipients-selecting-external-recipients).

<!--
### Send to your subscribers {#send-to-subscribers}

To send messages to the subscribers of a newsletter, you can directly target the subscribers to the corresponding information service. Learn more [in this section](../audiences/).-->

### Destinatários de teste {#test-recipients-seed-addresses}

Para testar sua entrega, use provas antes de enviar para o público-alvo principal.

Selecione os destinatários de prova apropriados, porque eles validam a forma e o conteúdo da mensagem. As etapas para definir os destinatários de prova são apresentadas [nesta seção](create-message.md#select-the-recipients-of-proof-messages-select-the-proof-target).


### Cancelar endereços duplicados {#deduplicate-addresses}

É importante evitar emails duplicados, pois eles podem afetar seu público-alvo:

* A mesma mensagem pode ser enviada mais de uma vez quando um público-alvo é dividido.

* Se um destinatário cancelar a assinatura após receber uma mensagem, seu perfil duplicado ainda receberá mensagens futuras.

O cancelamento da duplicação de endereços protege a reputação de envio e garante um bom gerenciamento de quarentena.

**Tópicos relacionados:**

* [Atividade de desduplicação](../../automation/workflow/deduplication.md).
* [Caso de uso: uso da funcionalidade de mesclagem da atividade de desduplicação](../../automation/workflow/deduplication-merge.md).


## Executar todas as verificações antes de enviar {#perform-all-checks}

Quando a mensagem estiver pronta, verifique se o conteúdo é exibido corretamente, em todos os dispositivos, e se não contém erros, como personalização incorreta ou links quebrados. Antes de enviar a mensagem, verifique também se os parâmetros e a configuração estão consistentes com a entrega.

As etapas para validar uma entrega são apresentadas [nesta seção](../send/preview-and-proof.md).

<!--
### Inbox rendering {#inbox-and-email-rendering}

Inbox rendering enables you to preview your messages on major email clients, scan content and reputation, discover how recipients are reading messages.

**Tips**:

* You can view the sent message in the different contexts in which it may be received: webmail, message service, mobile, etc.

* Inbox rendering capabilities are crucial to identifying whether your email campaigns successfully make it past the filters of major ISPs (Internet Service Providers) and webmail services. Such tools send a pre-flight copy of an email to a network of test inboxes, so you can see how the message will display, or render, across these services. They may also include reports and code correction options that help you quickly identify and make fixes that improve deliverability.

Learn more [in this section](inbox-rendering.md).-->

### Mensagens de prova {#proof-messages}

O envio de provas permite a verificação do link de opção de não participação, a mirror page e quaisquer outros links, validação da mensagem, verificação da exibição das imagens, detecção de possíveis erros, etc. Você também pode verificar seu design e renderização em diferentes dispositivos.

<!--
### Set up A/B testing deliveries {#a-b-testing-deliveries}

If you have several contents for an email delivery, you can use A/B testing to find out which version will have the biggest impact on the targeted population.

**Tips**:

* Send the different versions to some of your recipients

* Select the one with the highest success rate and send it to the rest of your target

Learn more [in this section](get-started-a-b-testing.md).-->

### Verificar se a mensagem foi entregue {#make-sure-your-message-is-delivered}

Como etapa final, maximize suas chances e aproveite o poder do Adobe Campaign para garantir que sua mensagem seja de fato entregue aos recipients relevantes.

#### Passar por um processo de validação

Você pode definir um processo de validação completo, envolvendo operadores e grupos do Adobe Campaign, para validar tanto o público-alvo quanto o conteúdo da mensagem. Dessa forma, será possível monitorar e controlar totalmente os diversos processos da campanha: direcionamento, conteúdo, orçamento, extração e envio de prova. Dependendo das suas permissões, os usuários serão notificados, receberão provas e poderão validar ou rejeitar a mensagem. Saiba mais [nesta seção](../../automation/campaigns/marketing-campaign-approval.md).

#### Usar ondas

Você pode aumentar progressivamente o volume enviado usando ondas. Esse aumento evitará que sua mensagem seja marcada como spam ou pode ser usado quando você quiser restringir o número de mensagens diárias. Ao usar ondas, você pode dividir as entregas em vários lotes, em vez de enviar grandes volumes de mensagens ao mesmo tempo. Saiba mais [nesta seção](../send/configure-and-send.md#sending-using-multiple-waves).

#### Priorizar mensagens

Você pode definir a ordem de envio para suas entregas, informando o nível de prioridade. Para fazer isso:

1. Edite as propriedades da entrega e selecione a guia **[!UICONTROL Delivery]**.

1. Defina o nível de prioridade da entrega em uma escala de **[!UICONTROL Very low]** a **[!UICONTROL Very high]**.

>[!NOTE]
>
>Não é possível definir a ordem de envio de mensagens a partir de uma entrega.

<!--
#### Setup IP Affinities

To better control the outbound SMTP traffic, you can manage affinities by defining which specific IP addresses can be used for each affinity. This lets you restrict the number of emails for specific deliveries towards machines or output addresses. For example, you can use one affinity per country or sub-domain. You can then create one typology per country and link each affinity to the corresponding typology.

You can:

* Define the IP affinities in the serverConf.xml configuration file. [Learn more](../../installation/using/configuring-campaign-server.md#managing-outbound-smtp-traffic-with-affinities)

* For each IPAffinity element, declare the IP addresses that can be used. [Learn more](../../installation/using/email-deliverability.md#list-of-ip-addresses-to-use)

* In the [typology](../../campaign-opt/using/about-campaign-typologies.md) of your choice, use the **[!UICONTROL Managing affinities with IP addresses]** field to link deliveries to the delivery server (MTA) which manages the said affinity. [Learn more](../../campaign-opt/using/applying-rules.md#control-outgoing-smtp-traffic).

* Once the email is sent, check the header to verify which IP address the delivery was sent from. Your email administrator should help you obtain the header information.

* For SMS deliveries, make sure that the SMS channel has a dedicated affinity limited to **one** application server container. [Learn more](../../installation/using/configure-delivery-settings.md#managing-outbound-smtp-traffic-with-affinities)

>[!NOTE]
>
>Most of these steps can only be performed by an expert user.-->

#### Usar tipologias

Você pode usar as regras de tipologia para excluir parte do público-alvo com base em critérios específicos. Isso garante que as mensagens enviadas atendam melhor às necessidades e expectativas dos clientes, de acordo com as políticas de comunicação da empresa. Por exemplo, você pode filtrar os destinatários menores de idade do público-alvo do seu informativo. Saiba mais [neste exemplo](../../automation/campaign-opt/filtering-rules.md).


## Rastrear e monitorar {#track-and-monitor}

Você clicou no botão **Enviar**? Vamos ver o que acontece. Depois que a entrega é enviada, o Adobe Campaign permite acompanhar as mensagens enviadas e descobrir como os destinatários reagem a sua entrega. Isso o ajudará a melhorar o envio futuro e a otimizar as próximas campanhas.

## Monitorar entregas {#monitoring-deliveries}

Para controlar suas campanhas, você deve garantir que a mensagem tenha sido entregue aos destinatários.

No painel de delivery do Campaign, é possível verificar as mensagens processadas e os logs de auditoria do delivery. Você também pode controlar o status das mensagens nos logs do delivery.

## Rastrear comportamento {#track-behaviour}

Para conhecer melhor o comportamento dos destinatários, você pode acompanhar como eles reagem a uma entrega: recebimento, abertura, cliques em links, assinaturas canceladas etc. No Campaign, essas informações são exibidas na guia **Tracking** dos destinatários direcionados pela entrega e na guia Tracking da entrega.

O rastreamento de mensagens é habilitado por padrão. Para configurar URLs, selecione a opção “Exibir URLs” na seção inferior do assistente de entrega. Para cada URL da mensagem, você pode escolher se deseja ativar o rastreamento.


[Saiba mais sobre os recursos de rastreamento](../send/tracking.md)
