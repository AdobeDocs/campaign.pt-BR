---
title: Recursos preditivos de engajamento do usuário
description: Saiba como usar tempo de envio preditivo e pontuação de engajamento
feature: Send Time Optimization
role: User
level: Intermediate
source-git-commit: fdaf107fd22f439a728f32ceb8cfc13a8c5bc1ad
workflow-type: tm+mt
source-wordcount: '759'
ht-degree: 67%

---

# Otimização de tempo de envio e pontuação preditiva de engajamento{#optimize-message-delivery}

Desenvolvido pela IA e pelo aprendizado de máquina, a Otimização de tempo de envio da Adobe Campaign e a Pontuação preditiva de engajamento podem analisar e prever taxas abertas, tempos de envio ideais e churn provável de acordo com as métricas históricas de engajamento.

A Adobe Campaign oferece dois novos modelos de aprendizado de máquina: [Otimização preditiva do tempo de envio](#predictive-send) e [Pontuação preditiva de engajamento](#predictive-scoring). Esses dois modelos são modelos de aprendizado automatizado específicos para projetar e fornecer melhores jornadas para o cliente.

>[!CAUTION]
>
>Esse recurso não está disponível para uso imediato como parte do produto. Ela só está disponível para clientes do Adobe Campaign Managed Cloud Services que executam o Adobe Campaign Classic v7 ou o Adobe Campaign v8.
>
>A implementação exige o engajamento da Adobe Consulting. Para saber mais, entre em contato com o representante do Adobe.


## Otimização preditiva do tempo de envio{#predictive-send}

A Otimização preditiva de tempo de envio prevê qual é o melhor tempo de envio para cada perfil de destinatário para aberturas ou cliques de email e para aberturas de mensagem de push. As pontuações indicam o melhor horário de envio para cada dia da semana e qual o melhor dia para enviar a fim de obter melhores resultados para cada perfil de recipient.

No modelo de Otimização preditiva de tempo de envio, há dois submodelos:

* O tempo preditivo de envio para abrir é o melhor horário para o envio da comunicação ao cliente para maximizar as aberturas

* O tempo preditivo de envio para cliques é o melhor horário para o envio de uma comunicação ao cliente para maximizar os cliques


**Entrada do modelo**: Logs do delivery, logs de rastreamento e atributos de perfil (não PII)

**Saída do modelo**: Melhor horário para o envio de uma mensagem (para aberturas e cliques)

Detalhes da saída:

* Calcule o melhor horário do dia para enviar um email nos 7 dias da semana com intervalos de 1 hora (por exemplo: 9h, 10h, 11h)
* O modelo indicará o melhor dia da semana e o melhor horário do dia
* Cada horário ideal é calculado duas vezes: uma vez para maximizar a taxa de abertura e outra para maximizar a taxa de cliques
* São administrados 16 campos (14 para os dias da semana e 2 para a semana inteira):
   * melhor horário para enviar um email para otimizar cliques na segunda-feira – valores entre 0 e 23
   * melhor horário para enviar um email para otimizar as aberturas na segunda-feira – valores entre 0 e 23
   * ...
   * melhor horário para enviar um email para otimizar cliques no domingo – valores entre 0 e 23
   * melhor horário para enviar um email para otimizar as aberturas no domingo – valores entre 0 e 23
   * ...
   * melhor dia para enviar um email para otimizar as aberturas da semana inteira – de segunda a domingo
   * o melhor horário para enviar um email para otimizar as aberturas da semana inteira – valores entre 0 e 23


A Otimização preditiva do Tempo de Envio é armazenada no nível do perfil:

![](assets/sto-schema.png)


>[!NOTE]
>
>O modelo precisa de pelo menos um mês de dados para produzir resultados significativos. Esses recursos preditivos se aplicam apenas aos canais de email e push.


## Pontuação de envolvimento preditivo {#predictive-scoring}

A Pontuação preditiva de engajamento prevê a probabilidade de um recipient se envolver com uma mensagem, bem como a probabilidade de opt out (cancelamento de inscrição) nos próximos 7 dias após o próximo envio de email. As probabilidades são divididas em compartimentos de acordo com o nível previsto de engajamento com seu conteúdo: alto, médio ou baixo. Esses modelos também fornecem a classificação de percentual de risco de cancelamento de inscrição para que os clientes entendam onde a classificação de um determinado cliente está em relação a outros.

A pontuação preditiva de engajamento permite:

* **Selecionar um público**: ao usar a atividade de query, você pode selecionar o público que vai se engajar com uma mensagem específica
* **Excluir um público**: usando a atividade de query, você pode remover o público para cancelar a inscrição
* **Personalizar**: personalizar mensagem de acordo com o nível de engajamento (usuários altamente engajados receberão uma mensagem diferente daqueles não engajados)

Este modelo usa várias pontuações para indicar:

* **Pontuação de engajamento ao abrir/Pontuação de engajamento ao clicar**: esse valor corresponde à probabilidade de um assinante se engajar com uma mensagem específica (abrir ou clicar). Os valores variam de 0,0 a 1,0.
* **Probabilidade de cancelamento de inscrição**: esse valor corresponde à probabilidade do recipient cancelar a inscrição do canal de email considerando um email aberto. Os valores variam de 0,0 a 1,0.
* **Nível de retenção**: esse valor classifica os usuários em três níveis: baixo, médio e alto. O alto tem mais probabilidade de adesão à marca, enquanto o baixo provavelmente cancelará a assinatura.
* **Classificação de percentual de retenção**: Classificação do perfil em termos de probabilidade de cancelamento de assinatura. Os valores variam de 0,0 a 1,0. Por exemplo, se a classificação de porcentagem de retenção for de 0,953, esse recipient terá maior probabilidade de permanecer com a marca e menos probabilidade de cancelar a assinatura do que 95,3% de todos os recipient.

>[!NOTE]
>
>Esses recursos preditivos se aplicam apenas para deliveries de email.
>
>O modelo precisa de pelo menos um mês de dados para produzir resultados significativos.

**Entrada do modelo**: Logs do delivery, logs de rastreamento e atributos específicos do perfil

**Saída do modelo**: Um atributo de perfil que descreve a pontuação e a categoria do perfil
