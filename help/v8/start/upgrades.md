---
title: Versões e atualizações do Campaign
description: Saiba mais sobre versões e atualizações do Campaign
feature: Release Notes
role: User
level: Beginner
exl-id: 04bda36f-051f-41a3-84b3-6af3c5e34ab2
TQID: https://experienceleague.adobe.com/EaoWEmt7vNplA6Cs6CdMvP-iwia6BkaDRjawsPoa6fs
product_v2:
  - id: dfc56824-e8b9-499e-85d4-21aedb507314
role_v2:
  - id: b69b2659-1057-424e-8fc5-ed9e016dc554
level_v2:
  - id: e8ccd51f-da0d-4e3b-939b-e30d5ebb1ea5
topic_v2:
  - id: d095671a-1355-40aa-8b5f-06c33c68080b
  - id: f4e6943a-c91a-4134-a2c7-f4f20cfff2f0
source-git-commit: 59a1ad4bbb194222f0c2b86117cc7dc6ecc3335d
workflow-type: tm+mt
source-wordcount: 1190
ht-degree: 10%

---

# Versões e atualizações {#upgrades}

O Adobe Campaign v8 é oferecido exclusivamente como uma solução **Managed Cloud Services**. O Adobe gerencia e executa todas as atualizações do lado do servidor para você — não há implantação local ou híbrida do v8 e nenhuma atualização do servidor para agendar ou executar você mesmo.

O Adobe Campaign é atualizado regularmente. Essa frequência regular de atualizações tem como objetivo fazer com que você tenha disponível as mais recentes e melhores atualizações, além de manter seu ambiente protegido e melhorar sua experiência com nosso produto.

Como usuário do Managed Cloud Services:

* A instância do servidor do Campaign é atualizada pela Adobe a cada nova versão, automaticamente e sem exigir nenhuma ação da sua parte.
* O representante da Adobe entra em contato com você antes de uma atualização que afeta seu ambiente.
* **O console do cliente é o único componente pelo qual você é responsável.** Ele deve ser atualizado para a mesma versão que o servidor do Campaign. Saiba como atualizar seu console do cliente nesta [página](../start/connect.md#upgrade-ac-console).

Além disso, como cliente, verifique se você está usando a versão compatível mais recente dos sistemas listados na [Matriz de compatibilidade](compatibility-matrix.md).

>[!IMPORTANT]
>
>A Adobe se reserva o direito de aplicar patches de segurança críticos ao seu ambiente hospedado a qualquer momento, sem aviso prévio, a fim de corrigir vulnerabilidades o mais rápido possível. Esses patches são implantados sem interrupção do serviço. A correção de uma vulnerabilidade crítica tem prioridade sobre a notificação prévia.

## Versões do Campaign {#versions}

A Adobe Campaign lança periodicamente versões de produtos que melhoram o desempenho, a segurança, a lógica e a usabilidade da infraestrutura do Campaign.

Essas atualizações podem ser:

* **Atualizações principais**, de uma versão principal para outra, por exemplo, da v7 para a v8. Essas atualizações trazem novos recursos, melhorias, atualizações de compatibilidade e segurança e correções.
* **Pequenas atualizações**, de uma versão secundária para outra, por exemplo, da v8.5 para a v8.6. Essas atualizações trazem melhorias, atualizações de compatibilidade e segurança e correções.
* **Atualizações de patch**, de uma versão de patch para outra, por exemplo, da v8.5.1 para v8.5.2. Essas atualizações trazem atualizações e correções de segurança.

Informações detalhadas sobre cada nova versão estão disponíveis nas [Notas de versão](release-notes.md). As correções relacionadas à segurança são feitas nas notas de cada versão — consulte [Como posso ser informado sobre o lançamento de uma nova versão?](#upgrades-0) abaixo.

Para garantir uma configuração estável, a Adobe recomenda instalar o **exatamente a mesma versão** em todos os servidores do Campaign. Além disso, exceto quando mencionado o contrário nas [Notas de versão](release-notes.md), o console do cliente deve estar na **mesma versão** da instância do servidor. Saiba como atualizar seu console do cliente [nesta página](../start/connect.md#upgrade-ac-console).

## Mantenha seu console do cliente atualizado {#ac-upgrades}

Como cliente do Campaign Managed Services, quando uma nova versão do Campaign está disponível, sua infraestrutura de servidor é atualizada pela Adobe sem nenhuma outra ação da sua parte.

Como a atualização do servidor acontece automaticamente, o **console do cliente** é o único local em que uma lacuna pode aparecer se não for atualizada ao mesmo tempo. Se a versão do console não corresponder à versão do servidor:

* Você pode perder a capacidade de se conectar à instância do Campaign até que o console seja atualizado.
* O console deixa de se beneficiar das correções e atualizações de segurança fornecidas na versão para a qual o servidor já foi movido — mesmo que o próprio servidor seja atual.

Para evitar isso, atualize o console do cliente assim que for notificado de uma nova versão. Saiba como [atualizar seu console do cliente](../start/connect.md#upgrade-ac-console).

Observe que, como cliente, você também deve garantir que esteja usando as versões mais recentes com suporte dos sistemas listados na [Matriz de compatibilidade](compatibility-matrix.md).

## Perguntas frequentes {#upgrades-faq}

### Como verificar minha versão do Campaign? {#version}

Para verificar sua versão do Campaign, acesse o menu **Ajuda > Sobre...** no console do cliente.

![](assets/ac-version.png)

Você acessa as seguintes informações:

* O número **versão** do console do cliente e do servidor de aplicativos. Na amostra acima, a versão é 8.1.5 para o console do cliente e para o servidor de aplicativos.
* O número SHA, entre parênteses.
* Um link para entrar em contato com o Atendimento ao cliente da Adobe.
* Links para Política de privacidade da Adobe, Termos de uso e Política de cookies.

>[!NOTE]
>
>Se a versão mostrada para o console do cliente não corresponder à versão mostrada para o servidor de Aplicativos, atualize o console conforme descrito em [Mantenha o console do cliente atualizado](#ac-upgrades).

### Como posso ser informado do lançamento de uma nova versão? {#upgrades-0}

Novas versões e quais alterações elas trazem — incluindo correções de segurança — estão listadas nas [Notas de Versão](release-notes.md). Quando uma nova versão estiver disponível, o representante da Adobe entrará em contato com você e atualizará os ambientes de servidor. Você precisará atualizar separadamente o console do cliente (consulte [Manter o console do cliente atualizado](#ac-upgrades)).

Para ser informado sobre novos lançamentos de soluções da Experience Cloud e seu conteúdo, inscreva-se na comunicação [Atualizações Prioritárias de Produtos da Adobe](https://www.adobe.com/br/subscription/priority-product-update.html){target="_blank"}.

Você também pode visitar a [Comunidade do Campaign](https://experienceleaguecommunities.adobe.com/t5/custom/page/page-id/Community-TopicsPage?profile.language=pt&style=all&sort=date&order=desc&filters=adobe-campaign-classic-community&topic=Campaign+v8){target="_blank"} para ser informado sobre atualizações de lançamento.

### Por que minha organização precisa de uma atualização? {#upgrades-1}

A atualização garante que sua conta esteja protegida contra vulnerabilidades e use uma tecnologia de desempenho atualizada.

Normalmente, a atualização para a versão mais recente traz:

* **Segurança aprimorada**

  A segurança precisa de foco constante e manutenção proativa. Os riscos de segurança estão presentes e não podem ser ignorados — cada atualização do Campaign melhora a segurança. Uma combinação de tecnologias trabalha em conjunto para potencializar o Adobe Campaign, e todas elas devem ser mantidas atualizadas. A Adobe aplica essas atualizações ao seu servidor automaticamente; atualizar o console do cliente em etapas garante que a mesma proteção se estenda a ele.

* **Suporte avançado**

  A maioria dos problemas críticos é resolvida com atualizações e pode ser evitada completamente. Atualizações regulares ajudam a reduzir os desafios enfrentados e aumentar a eficiência. O volume de atendimento ao cliente é reduzido, permitindo resoluções mais rápidas e mais atenção a problemas que não estão relacionados a atualizações.

* **Manutenção e estabilidade aprimoradas**

  Com o tempo, a equipe do Adobe Campaign identifica maneiras de melhorar a estabilidade e o desempenho do produto, bem como de corrigir problemas conhecidos. A atualização permite que sua instância esteja sempre alinhada a essas melhorias, eliminando desafios comuns enfrentados por organizações que enfrentam rápido crescimento e/ou complexidade em suas instâncias do Campaign. As melhorias na pilha de tecnologia que alimentam o Campaign se refletem nas equipes de marketing e de TI da sua organização.

* **Permaneça conectado**

  O console do cliente só pode se comunicar de forma confiável com um servidor que esteja executando a mesma versão. Manter o console atualizado — cada vez que o servidor é atualizado — é o que mantém essa conexão e a segurança e as correções que a acompanham, intactas.

### Qual é o processo e o cronograma de uma atualização? {#upgrades-2}

Como cliente do v8, a Adobe gerencia a atualização completa do seu servidor:

1. Quando uma nova versão estiver disponível ou sua conta for identificada com a necessidade de mudar para uma, o representante da Adobe o notificará.
1. A Adobe atualiza sua infraestrutura de servidor — nenhuma ação é necessária para esta etapa.
1. Da sua parte, a única ação necessária é atualizar o console do cliente para corresponder e confirmar os sistemas na sua [Matriz de compatibilidade](compatibility-matrix.md) ainda são suportados. Consulte [Manter o console do cliente atualizado](#ac-upgrades).

Uma equipe dedicada de representantes do Atendimento ao cliente, gerentes de produtos, engenheiros, especialistas em TechOps e consultores de produtos está aqui para ajudar e garantir que a experiência seja tranquila.

>[!NOTE]
>
>É possível aplicar patches de segurança críticos ao ambiente hospedado fora deste ciclo de notificação — consulte a observação na parte superior desta página.
