---
product: campaign
title: Nota técnica - Adobe Campaign - Atualização de segurança da versão Apache
description: Adobe Campaign - Atualização de segurança da versão do Apache
hide: true
hidefromtoc: true
exl-id: 68e42fe4-7fb6-4b53-9f39-e77374e3753d
source-git-commit: 50dcdf1f6bcc8c8a195a0bf0a37af254f33b80d5
workflow-type: tm+mt
source-wordcount: '466'
ht-degree: 0%

---

# Adobe Campaign - Atualização de segurança da versão do Apache {#apache-update}

>[!CAUTION]
>Este artigo se aplica a: clientes do Campaign Classic v7 Managed Cloud Service, clientes do Campaign v8 e clientes do Campaign Standard.

O Adobe Campaign funciona com ferramentas de terceiros e a compatibilidade é atualizada regularmente, a fim de implementar somente as versões compatíveis e se beneficiar das correções e melhorias mais recentes.

O Adobe Campaign inclui o Apache Tomcat, que atua como ponto de entrada no servidor de aplicativos via HTTP e é integrado ao Apache Web Server. O Apache Software Foundation lançou o Apache HTTP Server 2.4.53. Esta versão aborda vulnerabilidades que podem permitir que um invasor remoto assuma o controle de um sistema afetado. Saiba mais em [Comunicado do Apache 2.4.53](https://downloads.apache.org/httpd/Announcement2.4.html){target="_blank"}.

A equipe do Adobe Campaign conduzirá a atividade de atualização de segurança da versão do Apache até **15 de junho de 2022** para atenuar essa vulnerabilidade do Apache e tornar seu ambiente de instância mais seguro. Essa atualização se aplica a todos os clientes do Campaign Classic v7 Managed Cloud Service, Campaign v8 e clientes do Campaign Standard que executam uma versão vulnerável do Apache HTTP Server. Se você for afetado, o Adobe já entrará em contato com você para informá-lo sobre essa atualização.

Espera-se que essa atualização seja executada automaticamente fora do horário comercial normal para que você continue usando o serviço do Campaign sem interrupções.

Suas instâncias de não produção serão atualizadas por nossas equipes primeiro antes de atualizarmos suas instâncias de produção. Como esse é um processo de atualização automático de propriedade do Adobe, nenhuma ação é necessária da sua parte. No entanto, se você tiver algum problema, entre em contato com o [Atendimento ao cliente do Adobe](https://experienceleague.adobe.com/pt-br?support-solution=Campaign#support){target="_blank"}.


>[!NOTE]
>Esta atualização requer a reinicialização do servidor Web Apache. O tempo de inatividade não excederá 10 minutos dentro do período mencionado abaixo.
> 

## Perguntas frequentes {#apache-faq}

* **Por que esta é uma atualização obrigatória?**

  A versão atual do Apache está vulnerável e tem uma possível ameaça à segurança. É importante que suas instâncias do Campaign sejam atualizadas para a versão mais recente do Apache aplicável para lidar com o risco de segurança.


* **Quais clientes são direcionados para atualizações de segurança?**

  Todos os clientes que usam ambientes do Campaign implementados em versões mais antigas do Apache são atualizados para a versão mais recente aplicável do Apache.

* **Qual é o tempo de inatividade esperado?**

  O tempo de inatividade esperado é de menos de 10 minutos.

* **O cliente precisa realizar alguma ação para esta atualização de segurança?**

  Nenhuma ação é necessária, pois a atualização de segurança será executada automaticamente.

* **Que validações precisam ser executadas pelos clientes?**

  Nenhum teste específico é necessário para esta atualização de segurança. Caso algum problema seja observado, entre em contato com o [Adobe Customer Care](https://experienceleague.adobe.com/pt-br?support-solution=Campaign#support){target="_blank"}.


* **É possível solicitar uma alteração em Data/Hora no slot de atualização de segurança agendado?**

  Como essa é uma correção de segurança, recomendamos que você se adapte à programação existente.


Para qualquer outra pergunta, entre em contato com o [Adobe Customer Care](https://experienceleague.adobe.com/pt-br?support-solution=Campaign#support){target="_blank"}.
