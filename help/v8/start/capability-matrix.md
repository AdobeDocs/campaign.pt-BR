---
title: Campaign Classic v7 - Matriz de recursos do Campaign v8
description: Entender as diferenças entre o Campaign Classic v7 e o Campaign v8
feature: Overview
role: Data Engineer
level: Beginner
exl-id: 00ba1c43-9558-4adb-83a1-6597c2bbca62
source-git-commit: 6de5c93453ffa7761cf185dcbb9f1210abd26a0c
workflow-type: tm+mt
source-wordcount: '556'
ht-degree: 40%

---

# [!DNL Campaign Classic] v7 - recursos do [!DNL Campaign] v8{#gs-matrix}

Como um ex [!DNL Campaign Classic] Usuário do v7, você não deve esperar nenhuma grande interrupção na maneira com a qual você normalmente interage [!DNL Adobe Campaign]. A maioria das alterações na v8 não é visível, exceto pequenas alterações que surgiram na interface e nas etapas de configuração.

Adobe Campaign v8 está disponível como um **Cloud Service gerenciado**. A nova oferta combina os melhores serviços do setor com supervisão pró-ativa e alerta em tempo hábil, concentrando-se em três áreas:

* **Agilidade da nuvem** — automação por Adobe, com implantações em nuvem otimizadas e padronizadas para proporcionar desempenho mais previsível, maior agilidade e produtividade de autoatendimento aprimorada.
* **Experiência de serviço** — disponibilidade proativa, capacidade e monitoramento e resposta de desempenho para evitar interrupções, resolver incidentes mais rápido e analisar o serviço regularmente para melhorar continuamente.
* **Profundo conhecimento sobre o Campaign** — serviço de alta afinidade de equipes especializadas de engenharia de clientes para atender às necessidades funcionais, técnicas ou de deliverability, reduzir o risco de implantação e melhorar o gerenciamento de alterações.

Como um ex [!DNL Campaign Classic] usuário, observe que a maioria das [!DNL Campaign Classic] Os recursos do v7 estão disponíveis com [!DNL Campaign] v8, exceto um pequeno conjunto, listado em [esta seção](#gs-removed). Outros serão lançados em versões futuras. [Saiba mais nesta seção](#gs-unavailable-features)

>[!NOTE]
>
> O Campaign v8 depende de uma arquitetura híbrida. Se estiver fazendo a transição do Campaign Classic v7, observe que todos os deliveries passam pelo servidor mid-sourcing. [Saiba mais](../architecture/architecture.md)
>
> Como consequência, o roteamento interno é **não é possível** no Campaign v8 e a conta externa foi desativada adequadamente.


## [!DNL Campaign] e [!DNL Snowflake] {#ac-gs-snowflake}

O Campaign v8 funciona com [!DNL Snowflake]. Dois modelos de implantação estão disponíveis.

![](../assets/do-not-localize/glass.png) Saiba mais sobre a arquitetura do [!DNL Campaign] v8 [nesta página](../architecture/architecture.md).


## Usar sua Adobe ID para se conectar ao Campaign{#adobe-id}

Os usuários do Campaign se conectam por meio da Adobe ID. A mesma Adobe ID é usada para manter todos os seus planos de Adobe e produtos associados a uma única conta, para todas as soluções da Adobe Experience Cloud.

![](../assets/do-not-localize/glass.png)Saiba como se conectar ao [!DNL Campaign] [nesta página](connect.md).

## Analisar dados com cubos{#adobe-reporting}

Use o módulo Marketing Analytics para analisar e medir dados, calcular estatísticas, simplificar e otimizar a criação e o cálculo do relatório. Além disso, crie relatórios e crie populações do target: uma vez identificados, eles são armazenados em listas que podem ser usadas no Adobe Campaign (direcionamento, segmentação etc.).

Os relatórios de cubo do Adobe Campaign são otimizados e proporcionam recursos de melhor escala que o Campaign Classic v7. Antigas limitações em cubos não se aplicam ao Campaign v8.

## Alterar fonte de dados {#change-data-source}

O Campaign v8 oferece uma atividade adicional de fluxo de trabalho para direcionamento: **[!UICONTROL Change data source]**.

A atividade **[!UICONTROL Change data source]** permite alterar a fonte de dados de um fluxo de trabalho **[!UICONTROL Working table]** para gerenciar dados em diferentes fontes de dados, como FDA, FFDA e banco de dados local.

![](../assets/do-not-localize/glass.png) Saiba mais sobre a atividade **[!UICONTROL Change data source]** [nesta página](../config/workflows.md#change-data-source-activity).

## Recursos indisponíveis{#gs-unavailable-features}

Observe que alguns recursos ainda não estão disponíveis nessa versão do Campaign, como:

* Gerenciamento de recursos de marketing
* Marketing distribuído
* Gestor de Resposta
* Modelos de implantação híbridos/no local

>[!CAUTION]
>
>* Por enquanto, o Campaign v8 está disponível **apenas** como um serviço na nuvem gerenciado e não pode ser implantado em um ambiente local ou híbrido.
>
>* A migração de um ambiente do Campaign Classic v7 existente ainda não está disponível.
>
>* Se não tiver certeza do modelo de implantação ou se tiver dúvidas, entre em contato com o executivo da sua conta Adobe.


## Recursos incompatíveis{#gs-removed}

Para alinhar-se à nova arquitetura e ao novo modelo de implantação do Campaign v8, alguns recursos históricos do Campaign Classic v7 não são mais compatíveis com o Campaign v8, como:

* Cupons
* Rastreamento web
* Pesquisas
* Marketing social o Facebook
* Conector ACS (oferta principal)
* Integração com o LDAP
* Logon de usuário/senha

>[!NOTE]
>
>Alguns recursos não disponíveis ou não compatíveis ainda podem estar visíveis na interface do usuário do .
