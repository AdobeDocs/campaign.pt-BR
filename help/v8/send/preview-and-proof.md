---
title: Pré-visualizar e testar o email
description: Saiba como validar seu delivery antes de enviar
feature: Personalization
role: User
level: Beginner
exl-id: 5b9fa90c-c23e-47a7-b2ca-de75da4da2ab
source-git-commit: 70af3bceee67082d6a1bb098e60fd2899dc74600
workflow-type: tm+mt
source-wordcount: '703'
ht-degree: 21%

---

# Pré-visualizar e testar o email {#preview-test}

Depois que o conteúdo da mensagem for definido, você poderá usar perfis de teste para pré-visualizá-la e testá-la. Se você inseriu [conteúdo personalizado](personalize.md), é possível verificar como esse conteúdo é exibido na mensagem, usando os dados do perfil de teste. Além disso, para detectar possíveis erros no conteúdo da mensagem ou nas configurações de personalização, envie provas para perfis de teste. Uma prova deve ser enviada sempre que uma alteração for feita, para validar o conteúdo mais recente.

## Visualização de conteúdo {#preview-content}

Antes de enviar provas, uma prática recomendada é verificar o conteúdo da mensagem na seção de pré-visualização da janela de delivery.

Para visualizar o conteúdo da mensagem, siga as etapas abaixo:

1. Navegue até a guia **Visualização** da entrega.
1. Clique no botão **[!UICONTROL Test personalization]** para selecionar um perfil para preencher os dados de personalização. Você pode escolher um recipient específico no banco de dados, um seed address ou selecionar um perfil do público-alvo, caso ele já tenha sido definido. Você também pode verificar o conteúdo sem personalização.

   ![](assets/test-personalization.png)

1. A pré-visualização é gerada para que você possa verificar a renderização da mensagem. Na pré-visualização da mensagem, os elementos personalizados são substituídos pelos dados do perfil de teste selecionado.

   ![](assets/test-personalization-with-a-recipient.png)

1. Selecione outros perfis de teste para visualizar a renderização de email para cada variante da mensagem.

## Enviar provas {#send-proofs}

Para entregas de email, é possível enviar provas para validar o conteúdo da mensagem. O envio de provas permite a verificação do link de opção de não participação, a mirror page e quaisquer outros links, validação da mensagem, verificação da exibição das imagens, detecção de possíveis erros, etc. Você também pode verificar seu design e renderização em diferentes dispositivos.

Uma prova é uma mensagem específica que permite testar uma mensagem antes de enviá-la ao público-alvo principal. Os destinatários da prova são responsáveis pela aprovação da mensagem: renderização, conteúdo, configurações de personalização, configuração.

### Destinatários de prova {#proofs-recipients}

O target de prova pode ser definido no template de delivery ou específico para um delivery. Em ambos os casos, navegue até a tela de definição de destino no link **[!UICONTROL To]** e selecione a guia **[!UICONTROL Target of the proofs]**.

![](assets/target-of-proofs.png)

O tipo de destino de prova está selecionado na lista suspensa **[!UICONTROL Targeting mode]**.

* Use a opção **[!UICONTROL Definition of a specific proof target]** para selecionar recipients no banco de dados como o target da prova.
* Use a opção **[!UICONTROL Substitution of the address]** para inserir endereços de email e usar os dados do recipient de destino para validar o conteúdo. Os endereços de substituição podem ser inseridos manualmente ou selecionados na lista suspensa. A enumeração associada é Substitution address (rcpAddress).
Por padrão, a substituição é executada aleatoriamente, mas você pode selecionar um recipient específico do público-alvo principal, por meio do ícone **[!UICONTROL Detail]**.

  ![](assets/target-of-proofs-substitution-details.png){width="800" align="left"}

  Escolha a opção **[!UICONTROL Select a profile (must be included in the target)]** e selecione um recipient.

  ![](assets/target-of-proofs-substitution.png){width="800" align="left"}


* Use a opção **[!UICONTROL Seed addresses]** para usar seed addresses como target de prova. Esses endereços podem ser importados de um arquivo ou inseridos manualmente.

  >[!NOTE]
  >
  >Os seed addresses não pertencem à tabela de recipient padrão (nms:recipient), pois são criados em uma tabela separada. Se a tabela de recipients é estendida com novos dados, a tabela de seed addresses também deverá ser ampliada, assim como os mesmos dados.

  Saiba mais sobre seed addresses em [esta seção](../audiences/test-profiles.md).

* Use a opção **[!UICONTROL Specific target and Seed addresses]** para combinar seed addresses e endereços de email específicos. As configurações relacionadas serão então definidas em duas sub-guias separadas.

### Enviar uma prova {#proofs-send}

Para enviar provas de mensagem, siga as etapas abaixo:

1. Na tela de definição da mensagem, clique no botão **[!UICONTROL Send a proof]**.
1. Na janela **[!UICONTROL Send a proof]**, verifique os recipients da prova.
1. Clique em **[!UICONTROL Analyze]** para iniciar a preparação da mensagem de prova.

   ![](assets/send-proof-analyze.png){width="800" align="left"}

1. Quando a preparação da entrega for concluída, use o **[!UICONTROL Confirm delivery]** para começar a enviar mensagens de prova.

Navegue até a guia **[!UICONTROL Audit]** da entrega para verificar a entrega de cópias de prova.

É recomendável enviar provas após cada modificação no conteúdo da mensagem.

>[!NOTE]
>
>Na prova enviada, o link para a mirror page não está ativo. Ele só é ativado nas mensagens finais.

### Propriedades da prova {#proofs-properties}

As propriedades de prova são definidas na guia **[!UICONTROL Advanced]** das janelas de propriedades de entrega. Navegue até o link **[!UICONTROL Proof properties...]** para definir os parâmetros e o rótulo das provas. Você pode optar por manter:

* Endereços duplicados na prova
* endereços ➡ Incluídos na lista de bloqueios na prova
* Endereços em quarentena na prova

Por padrão, as mensagens de prova são identificadas pela menção `Proof #N` no assunto, onde `N` é o número de prova. Esse número é incrementado a cada análise de delivery de prova. Você pode alterar o prefixo `proof`, conforme necessário.

![](assets/proof-parameters.png){width="800" align="left"}


## Vídeo tutorial {#video-proof}

Saiba como enviar e validar uma prova para uma entrega de email.

>[!VIDEO](https://video.tv.adobe.com/v/3447004?captions=por_br)
