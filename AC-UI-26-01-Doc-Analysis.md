---
source-git-commit: 548b4be24e26a6970f953f92af1f89d829689592
workflow-type: tm+mt
source-wordcount: '1522'
ht-degree: 0%

---
# AC-UI-26-01 Análise de documentação

## Conteúdo da próxima versão

Este documento analisa os JIRAs de produtos para as versões mensais AC-UI-26-01 e AC-UI-25-11 para planejar ações de documentação.

### Filtros JIRA

1. **[AC-UI-26-01-Monthly Stories](https://jira.corp.adobe.com/issues/?jql=project%20%3D%20NEO%20AND%20fixVersion%20%3D%20AC-UI-26-01-Monthly%20and%20type%20%3D%20story%20order%20by%20status)** - Principais histórias de lançamento
2. **[Melhorias do NEO-92400](https://jira.corp.adobe.com/issues/?jql=issueFunction%20in%20linkedIssuesOf(%27key%3DNEO-92400%27%2C%20%27is%20implemented%20by%27))** - Melhorias na versão de problemas vinculados
3. **[AC-UI-25-11-Monthly Stories](https://jira.corp.adobe.com/issues/?jql=project%20%3D%20NEO%20AND%20fixVersion%20%3D%20AC-UI-25-11-Monthly%20and%20type%20%3D%20story%20order%20by%20status)** - versão anterior transferida
4. **[AC-UI-25-11 Excluindo 8.8.2](https://jira.corp.adobe.com/issues/?jql=project%20%3D%20NEO%20AND%20fixVersion%20%3D%20AC-UI-25-11-Monthly%20and%20fixVersion%20!%3D%208.8.2%20and%20type%20%3D%20story%20order%20by%20status)** - Versão anterior filtrada

&#x200B;---

## 🟢 Criar DOCAC

### [NEO-91565](https://jira.corp.adobe.com/browse/NEO-91565) - Adicionar suporte para campos de personalização (Integração avançada do AEM)**Status:** Resolvido\**Doc necessário:** Sim\**DOCAC Existente:** Nenhum\**Ação:** Criar DOCAC

**Escopo:**
- Suporte de documentos para campos de personalização na Integração avançada do AEM
- Fluxo de trabalho da interface do usuário e etapas de configuração
- Recursos de integração multilíngue do AEM

**Descrição do Recurso:**
Suporte para adicionar campos de personalização em deliveries usando a Integração avançada de AEM, permitindo a inserção dinâmica de conteúdo dos dados do Campaign em modelos de email criados pela AEM.

**Contexto:** ACS para paridade ACC, requisito específico de MSFT

**Referências:** [wiki multilíngue do AEM](https://wiki.corp.adobe.com/pages/viewpage.action?pageId=2988189953)

&#x200B;---

### [NEO-93487](https://jira.corp.adobe.com/browse/NEO-93487) - Processo de computação do agendamento de entrega (paridade ACS)**Status:** Novo\**Doc necessário:** Sim\**DOCAC Existente:** Nenhum\**Ação:** Criar DOCAC

**Escopo:**
- Processo de computação de agendamento de entrega de documentos para notificações por push
- Fórmulas de agendamento baseadas em fuso horário
- Upload de arquivo para direcionamento de vários fusos horários

**Descrição do Recurso:**
Habilite o agendamento de delivery baseado em arquivo OOTB com tempos de envio calculados com base no fuso horário do recipient, permitindo direcionamento de delivery único em vários fusos horários com tempos de envio otimizados por região.

**Contexto:** orientado pelo cliente (H&amp;M), ACS para requisito de paridade ACC

**Referências:** [Documentação do ACS](https://experienceleague.adobe.com/pt-br/docs/campaign-standard/using/testing-and-sending/scheduling-messages/computing-the-sending-date)

&#x200B;---

## 🔄 Atualizar DOCAC

### [NEO-80973](https://jira.corp.adobe.com/browse/NEO-80973) - Disponibilidade do Dynamic Reporting para todos os usuários da interface do usuário da Web&#x200B;**Status:** Em Andamento\**Doc necessário:** Sim\**DOCAC Existente:** [DOCAC-11070](https://jira.corp.adobe.com/browse/DOCAC-11070) (Fechado), [DOCAC-13432](https://jira.corp.adobe.com/browse/DOCAC-13432) (Resolvido)\**Ação:** Revisar DOCAC

**Escopo:**
- Atualizar informações de disponibilidade (agora para todos os usuários da interface da Web, não apenas para a versão 8.7)
- Limitações do idioma do documento
- Esclarecer a exibição de métricas conflitantes com os relatórios herdados

**Descrição do Recurso:**
Os Relatórios dinâmicos agora estão disponíveis para todos os usuários da interface da Web do Campaign (antes limitados ao ACS 8.7 para clientes do ACC), fornecendo recursos avançados de análise e relatórios personalizados com interface no estilo ACS.

**Contexto:** expansão de recursos, dependência de compilação de back-end (8.8.1)

**Referências:** [Wiki - Comparação de relatórios](https://wiki.corp.adobe.com/display/~kumarvishal/Reports+-+Client+console+vs+WebUI)

&#x200B;---

### [NEO-86754](https://jira.corp.adobe.com/browse/NEO-86754) - Teste A/B&#x200B;**Status:** Em Andamento\**Doc necessário:** Sim\**DOCAC Existente:** [DOCAC-13104](https://jira.corp.adobe.com/browse/DOCAC-13104) (Novo)\**Ação:** Atualizar DOCAC

**Escopo:**
- Concluir a documentação do fluxo de trabalho de teste A/B
- Configuração de experimentação de conteúdo e configuração de variantes
- Definição da proporção de amostra e critérios de seleção do vencedor
- Coleta e avaliação de estatísticas

**Descrição do Recurso:**
Experimentação de conteúdo e testes A/B para deliveries de email, permitindo que os profissionais de marketing testem diferentes variantes de conteúdo, definam tamanhos de amostra, coletem estatísticas de desempenho e enviem automaticamente a variante vencedora para os recipients restantes.

**Contexto:** projeto Europa, requisito Microsoft, sinalizador de recurso habilitado

**Referências:** [Wiki](https://wiki.corp.adobe.com/pages/viewpage.action?pageId=3017705719), [Figma mocks](https://www.figma.com/design/4EfXEaA6OIV0D8rauuXSWX/A-B-Testing)

&#x200B;---

### [NEO-76126](https://jira.corp.adobe.com/browse/NEO-76126) - Criação de esquemas (criar nova tabela, estender esquemas, acessar banco de dados externo)**Status:** Em Andamento\**Doc necessário:** Sim\**DOCAC Existente:** [DOCAC-13826](https://jira.corp.adobe.com/browse/DOCAC-13826) (Novo)\**Ação:** Atualizar DOCAC

**Escopo:**
- Fluxo de trabalho de criação do esquema do documento (apenas 3 opções: criar tabela, estender esquema, acessar banco de dados externo)
- Definição de formulário para entidades personalizadas
- Navegar e CRUD operações em esquemas personalizados
- Recursos das fases 2 e 3

**Descrição do Recurso:**
Os recursos de criação de esquemas na interface da Web permitem que os administradores criem novas tabelas de banco de dados, estendam os esquemas existentes com campos personalizados e se conectem a bancos de dados externos, o que é essencial para a personalização do modelo de dados.

**Contexto:** Requisito do Microsoft, projeto Europa, entrega em fases (Fase 2 ativa, Fase 3 Fim de fevereiro)

**Referências:** [PRD](https://wiki.corp.adobe.com/pages/viewpage.action?spaceKey=neolane&title=AC+Web+UI+-+Schemas+PRD), [Figma](https://www.figma.com/design/lZkJso2HvXPbNjG0TmQTrC/Schemas)

&#x200B;---

### [NEO-92668](https://jira.corp.adobe.com/browse/NEO-92668) - Análise da Web&#x200B;**Status:** Novo\**Doc necessário:** Sim\**DOCAC Existente:** Nenhum\**Ação:** Criar DOCAC

**Escopo:**
- Configuração da conta externa do Web Analytics
- Configuração e autenticação da integração
- Uso de dados do Analytics em campanhas

**Descrição do Recurso:**
Integração do Web Analytics, permitindo a conexão com plataformas de análise da Web para rastreamento e relatórios sobre o desempenho da campanha e o comportamento do visitante do site.

**Contexto:** solicitação do cliente (P2E-RSC), disponibilidade pendente do ambiente

**Referências:** nenhuma fornecida

&#x200B;---

### [NEO-86753](https://jira.corp.adobe.com/browse/NEO-86753) - Integração do AEM para Live Copies/Cópias de idioma&#x200B;**Status:** Novo\**Doc necessário:** Sim\**DOCAC Existente:** [DOCAC-13829](https://jira.corp.adobe.com/browse/DOCAC-13829) (Resolvido)\**Ação:** Revisar DOCAC

**Escopo:**
- Procurar modelos de entrega do AEM
- Crie Live Copies e Cópias de idioma com um clique
- Fluxo de trabalho de criação de variante de conteúdo multilíngue

**Descrição do Recurso:**
Integração simplificada do AEM, permitindo a criação de Live Copies com um clique e de Cópias de idioma de templates de delivery do AEM, simplificando a criação de campanhas multilíngues para usuários do AEM.

**Contexto:** Requisito do Microsoft, trabalho transferido para a equipe do Himanshu

**Referências:** [Documentação do ACS](https://experienceleague.adobe.com/docs/campaign-standard/using/integrating-with-adobe-cloud/working-with-campaign-and-experience-manager/creating-multilingual-email-aem.html?lang=pt-BR)

&#x200B;---

### [NEO-88838](https://jira.corp.adobe.com/browse/NEO-88838) - Editor de conteúdo: usar variáveis de tema no fragmento&#x200B;**Status:** Novo\**Doc necessário:** Sim\**DOCAC Existente:** [DOCAC-12941](https://jira.corp.adobe.com/browse/DOCAC-12941) (Novo)\**Ação:** Atualizar DOCAC

**Escopo:**
- Variáveis de tema no designer de email (Beta)
- Uso de temas em fragmentos
- Ativação do recurso Acrite

**Descrição do Recurso:**
Suporte para usar variáveis de tema em fragmentos de conteúdo, permitindo uma identidade visual consistente e um aplicativo de sistema de design em componentes de email com gerenciamento de tema centralizado.

**Contexto:** Em espera, recurso Acrite a ser revisitado

**Referências:** [ATU-5460](https://jira.corp.adobe.com/browse/ATU-5460)

&#x200B;---

## ➕ Criar DOCAC (melhorias)

### [NEO-92942](https://jira.corp.adobe.com/browse/NEO-92942) - Filtros predefinidos - Opção compartilhada&#x200B;**Status:** Resolvido\**Doc necessário:** Sim\**DOCAC Existente:** [DOCAC-13697](https://jira.corp.adobe.com/browse/DOCAC-13697) (Revisão do Código), [DOCAC-13522](https://jira.corp.adobe.com/browse/DOCAC-13522) (Fechado - Auxiliar)\**Ação:** Revisar DOCAC

**Escopo:**
- Opção compartilhada para filtros predefinidos
- Visibilidade de filtro com outros operadores (comportamento de Jornada ACC vs Brand)
- Gerenciamento de usuários de filtros compartilhados

**Descrição do Recurso:**
Agora os filtros predefinidos podem ser marcados como &quot;compartilhados&quot; para torná-los visíveis para outros operadores, com comportamentos diferentes para ACC (padrão) e Jornada de marca (filtragem específica do usuário).

**Contexto:** Aprimoramento do construtor de regras, sinalizador de recursos: enable-query-filter-shared

**Referências:** Relacionadas a [NEO-88441](https://jira.corp.adobe.com/browse/NEO-88441)

&#x200B;---

### [NEO-91299](https://jira.corp.adobe.com/browse/NEO-91299) - Atividade de entrega contínua&#x200B;**Status:** Fechado\**Doc necessário:** Sim\**DOCAC Existente:** [DOCAC-13586](https://jira.corp.adobe.com/browse/DOCAC-13586) (Novo), [DOCAC-13808](https://jira.corp.adobe.com/browse/DOCAC-13808) (Fechado - ajuda contextual)\**Ação:** Atualizar DOCAC

**Escopo:**
- Atividade de workflow de delivery contínuo
- Configuração do seletor de modelo de entrega
- Geração automática de transição de saída
- Opções de direcionamento (sem acesso ao conteúdo)

**Descrição do Recurso:**
A atividade contínua do delivery para workflows permite a execução recorrente do delivery a partir de modelos, gerando automaticamente transições de saída para a orquestração do workflow sem modificação do conteúdo.

**Contexto:** Sinalizador de recurso: enable-continuous-delivery

**Referências:** épico relacionado [NEO-67972](https://jira.corp.adobe.com/browse/NEO-67972)

&#x200B;---

### [NEO-90130](https://jira.corp.adobe.com/browse/NEO-90130) - Habilitar Carregamento de Arquivo OOTB para Notificações por Push Multilíngues&#x200B;**Status:** Fechado\**Doc necessário:** Sim\**DOCAC Existente:** [DOCAC-13606](https://jira.corp.adobe.com/browse/DOCAC-13606) (Novo)\**Ação:** Atualizar DOCAC

**Escopo:**
- Upload de arquivo para notificações por push multilíngues (iOS e Android)
- Formato CSV e mapeamento de campos
- Suporte avançado a push com recursos multilíngues

**Descrição do Recurso:**
Recurso de upload de arquivo OOTB para criar deliveries de notificação por push multilíngue por meio da importação de CSV, corresponder à funcionalidade ACS e permitir configuração de campanha multilíngue eficiente.

**Contexto:** orientado pelo cliente (H&amp;M), ACS para paridade ACC, crítico para migração

**Referências:** [Documentação do ACS](https://experienceleague.adobe.com/pt-br/docs/campaign-standard/using/communication-channels/push-notifications/generating-csv-multilingual-push)

&#x200B;---

## ❌ Cancelada / Não Se Aplica Mais

### [NEO-91566](https://jira.corp.adobe.com/browse/NEO-91566) - Suporte para rastreamento CTA em webui&#x200B;**Status:** Fechado (Não Se Aplica Mais)\**Doc Necessário:** Não\**DOCAC Existente:** [DOCAC-13821](https://jira.corp.adobe.com/browse/DOCAC-13821) (Novo)\**Ação:** Fechar DOCAC

**Motivo:** novo recurso ACS para dar suporte à MSFT - não iniciado, informações pendentes da MSFT, nenhum trabalho de interface esperado

**Contexto:** Requisito de rastreamento do CTA específico do Microsoft

&#x200B;---

### [NEO-91564](https://jira.corp.adobe.com/browse/NEO-91564) - Suporte à interface multilíngue do AEM&#x200B;**Status:** Fechado (Não Se Aplica Mais)\**Doc Necessário:** Não\**DOCAC Existente:** [DOCAC-13822](https://jira.corp.adobe.com/browse/DOCAC-13822) (Novo)\**Ação:** Fechar DOCAC

**Motivo:** trabalho de interface gerenciado pela equipe do Himanshu (história diferente)

**Contexto:** requisito do Microsoft, trabalho transferido

&#x200B;---

### [NEO-91567](https://jira.corp.adobe.com/browse/NEO-91567) - Adicionar suporte para Recurso NRT&#x200B;**Status:** Resolvido (Não Se Aplica Mais)\**Doc Necessário:** Não\**DOCAC Existente:** [DOCAC-13824](https://jira.corp.adobe.com/browse/DOCAC-13824) (Novo)\**Ação:** Fechar DOCAC

**Motivo:** novo recurso específico do ACS para MSFT - especificação disponível, mas sem impacto na interface da Web

**Contexto:** Requisito de Microsoft, mensagens transacionais

&#x200B;---

### [NEO-91563](https://jira.corp.adobe.com/browse/NEO-91563) - API Rest Transacional para Enriquecimento Baseado em Perfil&#x200B;**Status:** Resolvido (Não Se Aplica Mais)\**Doc Necessário:** Não\**DOCAC Existente:** [DOCAC-13825](https://jira.corp.adobe.com/browse/DOCAC-13825) (Novo)\**Ação:** Fechar DOCAC

**Motivo:** Nenhum trabalho de interface do usuário da Web, instância atualizada pendente, atualização de compilação obrigatória para a versão

**Contexto:** recurso de ponto de extremidade REST API

&#x200B;---

### [NEO-92151](https://jira.corp.adobe.com/browse/NEO-92151) - Enriquecimento baseado em Perfil - Fase 2 de Mensagens Transacionais&#x200B;**Status:** Resolvido (Não Se Aplica Mais)\**Doc Necessário:** Não\**DOCAC Existente:** [DOCAC-13823](https://jira.corp.adobe.com/browse/DOCAC-13823) (Novo)\**Ação:** Fechar DOCAC

**Motivo:** a história não tem tarefas, marcadas como &quot;não se aplica mais&quot;

**Contexto:** Requisito do Microsoft, projeto Europa

&#x200B;---

## 🟢 Documentação pronta (do AC-UI-25-11)

### [NEO-90183](https://jira.corp.adobe.com/browse/NEO-90183) - Rich Push Multilíngue - Interface do Usuário&#x200B;**Status:** Fechado\**Doc necessário:** Sim\**DOCAC Existente:** [DOCAC-13565](https://jira.corp.adobe.com/browse/DOCAC-13565) (Novo)\**Ação:** Revisar DOCAC

**Escopo:**
- Campos de push avançados para deliveries multilíngues
- Suporte à plataforma iOS e Android
- Configuração de modelo e conteúdo

**Descrição do Recurso:**
Suporte avançado a notificações por push com recursos multilíngues, permitindo que os profissionais de marketing criem notificações por push aprimoradas com imagens, botões e mídia avançada para iOS e Android em vários idiomas.

**Contexto:** orientado pelo cliente (H&amp;M), entregue em 25-11, trabalho de back-end concluído

**Referências:** [Wiki](https://wiki.corp.adobe.com/pages/viewpage.action?spaceKey=neolane&title=Rich+push+fields+in+multilingual)

&#x200B;---

### [NEO-84916](https://jira.corp.adobe.com/browse/NEO-84916) - Configurar e gerenciar o processo de aprovação&#x200B;**Status:** Resolvido\**Doc necessário:** Sim\**DOCAC Existente:** [DOCAC-13827](https://jira.corp.adobe.com/browse/DOCAC-13827) (Novo)\**Ação:** Atualizar DOCAC

**Escopo:**
- Configurar operadores de validação no delivery/campanha
- Configuração do fluxo de trabalho de aprovação
- Processo de aprovação de conteúdo e público alvo
- Suporte a vários canais (email, SMS, push, correspondência direta, call center, personalizado)

**Descrição do Recurso:**
Gerenciamento de processo de aprovação, permitindo workflows de validação para conteúdo e direcionamento de entrega, com atribuição de operador e rastreamento de aprovação em todos os canais de entrega.

**Contexto:** orientado pelo cliente (Pierre Fabre), requisito do Microsoft, desenvolvimento concluído e em teste

**Referências:** [Documentação clássica](https://experienceleague.adobe.com/pt-br/docs/campaign-classic/using/orchestrating-campaigns/orchestrate-campaigns/marketing-campaign-approval), [Mocks de figuras](https://www.figma.com/design/r2vpqXoVyI3aucKgkt8TLN/Approvals)

&#x200B;---

## Resumo de 📊 por ação

| Ação | Contagem |
|--------|-------|
| 🟢 Criar DOCAC | 3 |
| 🔄 Atualizar DOCAC | 6 |
| DOCAC de revisão de ✅ | 3 |
| ❌ Fechar DOCAC | 5 |
| **Total** | **17** |

&#x200B;---

## ⚠️ Perguntas abertas

1. NEO-93487 - escalonamento H&amp;M - requer atenção urgente para o processo de computação de programação
2. NEO-92668 - Web Analytics - aguardando a disponibilidade do ambiente antes que a documentação possa ser concluída
3. NEO-76126 - Schemas Fase 3 - ETA Fim de fevereiro, é necessária uma história de documentação separada
4. NEO-88838 - Variáveis de tema - em espera pendente revisão de recurso Acrite
5. Relatórios dinâmicos - esclarecer orientações de exibição de métricas conflitantes com relatórios herdados

&#x200B;---

## 🔗 Épicos relacionados

- NEO-85263 - Épica principal do ACS para ACC (EUROPA)
- NEO-67972 - Melhorias no fluxo de trabalho
- NEO-87980 - Integração avançada do AEM
- NEO-90199 - Disponibilidade da versão do Dynamic Reporting
- NEO-63067 - UX/IU de experimentação de conteúdo
- NEO-67726 - Teste A/B e experimentação de conteúdo
- NEO-85274 - Esquema e formulário (Fase 2)
- NEO-87993 - Esquema e formulário (Fase 3)
