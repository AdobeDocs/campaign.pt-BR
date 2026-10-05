---
title: Versões, atualizações e segurança do Campaign
description: Saiba mais sobre versões e atualizações do Campaign
feature: Release Notes
role: User
level: Beginner
hide: true
product_v2:
  - id: dfc56824-e8b9-499e-85d4-21aedb507314
    internal-label: Campaign
role_v2:
  - id: b69b2659-1057-424e-8fc5-ed9e016dc554
    internal-label: User
level_v2:
  - id: e8ccd51f-da0d-4e3b-939b-e30d5ebb1ea5
    internal-label: Beginner
topic_v2:
  - id: d095671a-1355-40aa-8b5f-06c33c68080b
    internal-label: Security
  - id: f4e6943a-c91a-4134-a2c7-f4f20cfff2f0
    internal-label: Privacy
source-git-commit: 2b29b51ec0ddb0331afe7e8222f1f2a466c71e6c
workflow-type: tm+mt
source-wordcount: '1621'
ht-degree: 7%
---
# Versões, atualizações e segurança {#upgrades}

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

## Versões e atualizações do Campaign {#versions}

A Adobe Campaign lança periodicamente versões de produtos que melhoram o desempenho, a segurança, a lógica e a usabilidade da infraestrutura do Campaign.

Essas atualizações podem ser:

* **Atualizações principais**, de uma versão principal para outra, por exemplo, da v7 para a v8. Essas atualizações trazem novos recursos, melhorias, atualizações de compatibilidade e segurança e correções.
* **Pequenas atualizações**, de uma versão secundária para outra, por exemplo, da v8.5 para a v8.6. Essas atualizações trazem melhorias, atualizações de compatibilidade e segurança e correções.
* **Atualizações de patch**, de uma versão de patch para outra, por exemplo, da v8.5.1 para v8.5.2. Essas atualizações trazem atualizações e correções de segurança.

Informações detalhadas sobre cada nova versão estão disponíveis nas [Notas de versão](release-notes.md). As correções relacionadas à segurança são feitas nas notas de cada versão. Para obter mais informações sobre notificações de segurança, consulte [Manter-se informado](#security-staying-informed).

Para garantir uma configuração estável, a Adobe recomenda instalar o **exatamente a mesma versão** em todos os servidores do Campaign. Além disso, exceto quando mencionado o contrário nas [Notas de versão](release-notes.md), o console do cliente deve estar na **mesma versão** da instância do servidor. Saiba como atualizar seu console do cliente [nesta página](../start/connect.md#upgrade-ac-console).

### Mantenha seu console do cliente atualizado {#ac-upgrades}

Como cliente do Campaign Managed Services, quando uma nova versão do Campaign está disponível, sua infraestrutura de servidor é atualizada pela Adobe sem nenhuma outra ação da sua parte.

Como a atualização do servidor acontece automaticamente, o **console do cliente** é o único local em que uma lacuna pode aparecer se não for atualizada ao mesmo tempo. Se a versão do console não corresponder à versão do servidor:

* Você pode perder a capacidade de se conectar à instância do Campaign até que o console seja atualizado.
* O console deixa de se beneficiar das correções e atualizações de segurança fornecidas na versão para a qual o servidor já foi movido — mesmo que o próprio servidor seja atual.

Para evitar isso, atualize o console do cliente assim que for notificado de uma nova versão. Saiba como [atualizar seu console do cliente](../start/connect.md#upgrade-ac-console).

Observe que, como cliente, você também deve garantir que esteja usando as versões mais recentes com suporte dos sistemas listados na [Matriz de compatibilidade](compatibility-matrix.md).

### Confira a sua versão do Campaign {#version}

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

### Anúncios de versão do produto {#upgrades-0}

As novas versões e suas alterações estão listadas nas [Notas de Versão](release-notes.md).

Para obter atualizações de lançamentos de produtos, assine as [Atualizações de Produtos Prioritárias da Adobe](https://www.adobe.com/br/subscription/priority-product-update.html){target="_blank"} ou visite a [Comunidade do Campaign](https://experienceleaguecommunities.adobe.com/t5/custom/page/page-id/Community-TopicsPage?profile.language=pt&style=all&sort=date&order=desc&filters=adobe-campaign-classic-community&topic=Campaign+v8){target="_blank"}.

Para obter notificações de segurança e orientação sobre como preparar sua organização para atualizações de segurança, consulte [Mantenha-se informado](#security-staying-informed).

### Benefícios do upgrade {#upgrades-1}

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

### Processo e linha do tempo de atualização {#upgrades-2}

Como cliente do v8, a Adobe gerencia a atualização completa do seu servidor:

1. Quando uma nova versão estiver disponível ou sua conta for identificada com a necessidade de mudar para uma, o representante da Adobe o notificará.
1. A Adobe atualiza sua infraestrutura de servidor — nenhuma ação é necessária para esta etapa.
1. Da sua parte, a única ação necessária é atualizar o console do cliente para corresponder e confirmar os sistemas na sua [Matriz de compatibilidade](compatibility-matrix.md) ainda são suportados. Consulte [Manter o console do cliente atualizado](#ac-upgrades).

Uma equipe dedicada de representantes do Atendimento ao cliente, gerentes de produtos, engenheiros, especialistas em TechOps e consultores de produtos está aqui para ajudar e garantir que a experiência seja tranquila.

>[!NOTE]
>
>É possível aplicar patches de segurança críticos ao ambiente hospedado fora deste ciclo de notificação — consulte a observação na parte superior desta página.

## Proteção mais rápida dos clientes do Adobe Campaign: como a Adobe acompanha a segurança {#campaign-security}

### Encontrar mais, mais rápido {#finding-more-faster}

Conforme compartilhamos no [Protegendo clientes mais rapidamente: como a Adobe está respondendo à descoberta de vulnerabilidades acelerada por IA](https://blog.adobe.com/security/protecting-customers-faster-how-adobe-is-responding-to-ai-accelerated-vulnerability-discovery), as equipes de segurança da Adobe usam ferramentas assistidas por IA para identificar e solucionar vulnerabilidades com mais rapidez. Nós aplicamos essa abordagem em nossos produtos, incluindo o Adobe Campaign.

Esta seção explica como avaliamos e priorizamos problemas de segurança, como implantamos correções e o que isso significa para você.

### Como avaliamos e priorizamos os problemas de segurança {#assess-security-issues}

Nem todos os problemas de segurança apresentam o mesmo risco. A Adobe qualifica cada problema por gravidade e essa gravidade define o nível de prioridade.

Uma vulnerabilidade &quot;zero-day&quot; é uma falha anteriormente desconhecida que os invasores poderiam explorar antes que uma correção estivesse disponível, portanto, pode exigir ação urgente fora de nosso cronograma de lançamento regular. Solucionamos a maioria das outras vulnerabilidades por meio dos [Boletins de Segurança do Adobe](https://www.adobe.com/trust/security/bulletins-and-advisories.html), normalmente publicados na segunda e quarta terças-feiras de cada mês.

Nossas metas de resposta seguem essa avaliação de gravidade. Para os problemas mais graves, fechamos a janela de exposição primeiro e compartilhamos os detalhes de suporte assim que pudermos posteriormente. É por isso que algumas correções chegam a você com pouco ou nenhum aviso prévio. O momento é determinado pela gravidade da vulnerabilidade. Cada atualização, incluindo as urgentes, passa por uma validação de qualidade antes de ser enviada.

### Como implantamos correções {#deploy-security-fixes}

Validamos as atualizações de segurança antes do lançamento e escolhemos uma abordagem de implantação com base no escopo da alteração. Nosso objetivo é minimizar a interrupção.

Dependendo do escopo da atualização, usamos uma das duas abordagens de implantação:

* **Manutenção da pilha de segurança**: atualizações direcionadas que não alteram o número de compilação nem introduzem alterações pretendidas à funcionalidade do produto. Os clientes com configurações padrão normalmente não precisam tomar providências.
* **Atualizações de compilação orientadas por segurança**: atualizações que alteram seu número de compilação e seguem os processos padrão de notificação, nota de versão e implantação da Adobe.

Para configurações padrão e prontas para uso, suas integrações e campanhas em execução continuam funcionando como antes.

Projetamos atualizações de segurança para manter a compatibilidade com as configurações padrão do Adobe Campaign e minimizar a interrupção das operações do cliente. Se o ambiente incluir integrações personalizadas, scripts ou outras modificações, siga o processo de validação da organização após uma atualização de build. Se você tiver um comportamento inesperado, entre em contato com o Suporte ao cliente da Adobe.

### Manter-se informado {#security-staying-informed}

Você não precisa tomar medidas imediatas, mas essas etapas podem ajudar sua organização a permanecer informada e responder com eficiência:

* Mantenha sua conta e contatos técnicos atualizados no Adobe Admin Console para que as notificações cheguem às pessoas certas.
* Assine as [Notificações de segurança do Adobe](https://www.adobe.com/subscription/adobesecuritynotifications.html) para obter novos marcadores e conselhos.
* Revise o processo de gerenciamento de alterações da sua organização para que você possa avaliar e responder às atualizações de segurança imediatamente.

### Nosso compromisso {#security-commitment}

A Adobe tem o compromisso de ajudar a proteger seu ambiente Adobe Campaign e responder rapidamente quando surgirem problemas de segurança. Continuaremos a fortalecer nossos processos de segurança enquanto trabalhamos para minimizar a interrupção de suas operações.