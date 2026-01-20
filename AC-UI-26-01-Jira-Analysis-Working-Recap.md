---
source-git-commit: 548b4be24e26a6970f953f92af1f89d829689592
workflow-type: tm+mt
source-wordcount: '2430'
ht-degree: 3%

---
# Análise de tíquetes Jira AC-UI - Resumo de trabalho&#x200B;**Data:** 12 de janeiro de 2026&#x200B;**Tipo de Documento:** Documento de Trabalho/Análise Interna

&#x200B;---

## Resumo executivo

Este documento analisa os tíquetes do Jira de produtos de várias consultas relacionadas às versões da interface do usuário do AC (janeiro de 2026 e novembro de 2025). A análise se concentra em identificar requisitos de documentação, propor tíquetes DOCAC e destacar perguntas em aberto.

**Total de Tíquetes Exclusivos Analisados:** 19
**Tíquetes que Exigem Documentação:** 14
**Tíquetes Já Documentados:** 5
**Tíquetes sem Necessidade de Documento:** 5

&#x200B;---

## &#x200B;1. Lista de tickets analisados

### 1.1 AC-UI-26-01-Monthly Release (Janeiro de 2026)

| ID do tíquete | Título | Status | Prioridade | Componentes |
|-----------|-------|--------|----------|------------|
| NEO-91565 | [Interface do usuário da Web] Adicionar suporte para campos de personalização (Integração avançada do AEM) | Resolvido | Normal | ACS para ACC, PIX UI/UX |
| NEO-80973 | Disponibilidade de relatórios dinâmicos para todos os usuários da interface do usuário da Web | Em andamento | Normal | ACS para ACC, PIX UI/UX |
| NEO-86754 | Teste A/B de [UX/IU] | Em andamento | Bloqueador | PIX UI/UX |
| NEO-76126 | Criação de esquemas - crie uma nova tabela, estenda esquemas e acesse o BD externo | Em andamento | Crítico | PIX UI/UX |
| NEO-93487 | [Interface do usuário da Web] Processo de computação de agendamento de entrega semelhante ao do ACS | Novo | Crítico | PIX UI/UX |
| NEO-92400 | Melhorias na versão - 26 de janeiro | Novo | Normal | PIX UI/UX |
| NEO-88838 | Editor de conteúdo: usar variáveis de tema no fragmento | Novo | Normal | PIX UI/UX |
| NEO-92668 | Web Analytics [UX/IU] | Novo | Normal | PIX UI/UX |
| NEO-86753 | Integração do AEM [UX/UI] para Live Copies/Cópias de idioma | Novo | Bloqueador | ACS para ACC, PIX UI/UX |

### Tíquetes vinculados para melhorias na versão 1.2 (NEO-92400)

| ID do tíquete | Título | Status | Prioridade | Componentes |
|-----------|-------|--------|----------|------------|
| NEO-92942 | [Construtor de regras] Filtros predefinidos - Opção compartilhada | Resolvido | Normal | PIX UI/UX |
| NEO-91299 | Interface do usuário da Web - Atividade de entrega contínua | Fechado | Grave | PIX UI/UX |
| NEO-90130 | Habilitar upload de arquivo OOTB para deliveries de notificação por push multilíngue | Fechado | Crítico | ACS para ACC, PIX UI/UX |

### 1.3 Versão mensal do AC-UI-25-11 (novembro de 2025)

| ID do tíquete | Título | Status | Prioridade | Componentes |
|-----------|-------|--------|----------|------------|
| NEO-91566 | Suporte da [Interface do Usuário da Web] para rastreamento do CTA na webui | Fechado | Normal | ACS para ACC, PIX UI/UX |
| NEO-91564 | [Interface do usuário da Web] [AEM multilíngue no ACC] suporte para AEM multilíngue | Fechado | Normal | ACS para ACC, PIX UI/UX |
| NEO-90183 | [UX/UI] Rich Push Multilíngue - UI | Fechado | Bloqueador | PIX UI/UX |
| NEO-91567 | [Interface do Usuário da Web] Adicionar suporte para Recurso NRT | Resolvido | Normal | ACS para ACC, PIX UI/UX |
| NEO-91563 | API Rest transacional para enriquecimento baseado em perfil - Interface do usuário da Web | Resolvido | Normal | ACS para ACC, PIX UI/UX |
| NEO-92151 | [UI/UX] Mensagens Transacionais de Enriquecimento baseadas em Perfil - Fase 2 | Resolvido | Grave | ACS para ACC, PIX UI/UX |
| NEO-84916 | [UX/IU] Configurar e gerenciar o processo de aprovação | Resolvido | Crítico | PIX UI/UX |

&#x200B;---

## &#x200B;2. Bilhetes Que Exigem Documentação

### 2.1 ALTA PRIORIDADE - Desenvolvimento ativo (AC-UI-26-01)

#### **NEO-86754: Teste A/B**- **Status:** Em Andamento (No Caminho)- **Por que a documentação era necessária:** novo recurso importante para experimentação de conteúdo de email com recursos de teste A/B- **DOCAC existente:** DOCAC-13104 (Novo status)- **Escopo da Documentação:**   - Criação de experimentos de teste A/B em deliveries   - Definição de variantes de conteúdo/entrega   - Definição de proporções de amostra e envio de variantes de teste   - Definição dos critérios de avaliação   - Análise dos resultados do experimento e seleção dos vencedores   - Práticas recomendadas e limitações- **Público-alvo:** usuários de marketing, gerentes de campanha- **Versão:** 8.9.1, AC-UI-26-01-Monthly- **Abrir Perguntas:**   - Status final da validação da interface do usuário/UX?   - Há limitações para mensagens transacionais?   - Integração com a pré-visualização de conteúdo do Acrite?

#### **NEO-80973: Disponibilidade de Relatórios Dinâmicos**- **Status:** Em Andamento (Pronto para Revisão)- **Por que a documentação precisava:** Expandir os relatórios dinâmicos para todos os usuários da interface do usuário da Web (não apenas ACS 8.7 para clientes ACC)- **DOCAC existente:** DOCAC-11070 (fechado), DOCAC-13432 (resolvido - limitações de idioma)- **Escopo da Documentação:**   - Requisitos de disponibilidade e acesso   - Documentação de idiomas suportados   - Limitações conhecidas em relação aos relatórios herdados   - Métricas conflitantes são exibidas com relatórios herdados   - Configuração do ambiente de demonstração- **Público-alvo:** Todos os usuários da Interface do Usuário da Web, Analistas- **Versão:** 8.8.1, AC-UI-26-01-Monthly- **Abrir Perguntas:**   - Status de disponibilidade do ambiente de demonstração?   - Lista completa de métricas conflitantes com relatórios herdados?   - Matriz de suporte de idiomas?

#### **NEO-76126: Criação de Esquemas**- **Status:** Em Andamento (No Caminho)- **Por que a documentação era necessária:** recurso administrativo significativo para gerenciamento de modelo de dados- **DOCAC Existente:** DOCAC-13826 (Novo status)- **Escopo da Documentação:**   - Criação de novas tabelas   - Extensão de esquemas existentes   - Acesso a bancos de dados externos   - Definição de formulário para entidades personalizadas   - Navegação e operações CRUD   - Recursos da fase 3 (criar e estender esquemas) - ETA Fim de fevereiro- **Público-alvo:** usuários administradores, administradores técnicos- **Versão:** AC-UI-26-01-Monthly- **Data de vencimento:** 28 de fevereiro de 2026- **Abrir Perguntas:**   - Quando a Fase 2 será concluída para a ativação do FF?   - Confirmação do cronograma de entrega da fase 3?   - Requisitos de configuração de ambiente?

#### **NEO-93487: Processo de Computação de Agendamento de Entrega (H&amp;M)**- **Status:** Novo- **Por que a documentação era necessária:** Escalonamento crítico do cliente - agendamento de entrega baseado em fuso horário- **DOCAC existente:** nenhum identificado- **Escopo da Documentação:**   - Agendamento de entregas com base no fuso horário do usuário   - Utilização de fórmulas calculadas para regiões com vários fusos horários   - Exemplos de configuração (por exemplo, EUA com vários fusos horários)   - Práticas recomendadas para campanhas globais   - Comparação de recursos com o ACS- **Público-alvo:** gerentes de campanha, usuários de marketing- **Impacto no cliente:** H&amp;M (mais de 50 mercados)- **Versão:** 8.9.1, AC-UI-26-01-Monthly, 8.8.2.NEO-90300- **Abrir Perguntas:**   - Demonstração de recursos agendada com o PM?   - Especificações funcionais completas disponíveis?   - Os modelos de interface do usuário foram finalizados?

#### **NEO-86753: Integração do AEM para Live Copies/Cópias de idioma**- **Status:** Novo- **Documentação Necessária:** recurso específico do Microsoft para gerenciamento de conteúdo multilíngue- **DOCAC Existente:** DOCAC-13829 (Resolvido)- **Escopo da Documentação:**   - Navegação por modelos de entrega do AEM   - Criação de Live copies   - Criação de variantes de conteúdo de cópias de idioma   - Fluxo de trabalho e práticas recomendadas   - Requisitos de configuração de integração- **Público-alvo:** usuários de marketing que trabalham com equipes da AEM e da Microsoft- **Versão:** AC-UI-26-01-Monthly- **Prioridade:** Bloqueador- **Abrir Perguntas:**   - Trabalho transferido para a equipe de Himanshu - status atual?   - Cronograma de conclusão?

#### **NEO-92668: Análise da Web**- **Status:** Novo (No Caminho)- **Documentação Necessária:** Configuração de conta externa para integração de análise da web- **DOCAC existente:** nenhum identificado- **Escopo da Documentação:**   - Criação de conta externa do Web Analytics   - Parâmetros de configuração   - Integração com o rastreamento de delivery   - Recursos de relatórios- **Público-alvo:** usuários administradores, analistas de marketing- **Versão:** AC-UI-26-01-Monthly- **Abrir Perguntas:**   - Status de disponibilidade do ambiente?   - Etapas de configuração necessárias?

### 2.2 PRIORIDADE DO MEDIUM - Entregue recentemente (AC-UI-25-11)

#### **NEO-90183: Push Avançado Multilíngue**- **Status:** Fechado- **Por que a documentação era necessária:** Novo recurso para push avançado de iOS/Android com suporte multilíngue- **DOCAC Existente:** DOCAC-13565 (Novo status)- **Escopo da Documentação:**   - Configuração de notificação por push avançada para iOS e Android   - Variantes de conteúdo multilíngue   - Seleção de modelo   - Campos adicionais para conteúdo avançado   - Recursos de upload de arquivo   - Práticas recomendadas e limitações- **Público-alvo:** usuários de marketing, gerentes de canais móveis- **Versão:** AC-UI-25-11-Monthly, 8.8.2- **Cliente:** H&amp;M

#### **NEO-84916: Gerenciamento do Processo de Aprovação**- **Status:** Resolvido- **Por que a Documentação Necessária:** Recurso principal do fluxo de trabalho para validação de entrega- **DOCAC existente:** DOCAC-13827 (Novo status)- **Escopo da Documentação:**   - Configuração de operadores de aprovação em remessas/campanhas   - Configuração da aprovação de conteúdo   - Configuração da aprovação de target   - Gerenciamento de fluxos de trabalho de aprovação em canais (Email, SMS, Push iOS/Android, Correspondência direta, Call Center)   - Aceitar/rejeitar processos   - Relatórios e rastreamento de aprovação- **Público-alvo:** gerentes de campanha, usuários administradores- **Versão:** AC-UI-25-11-Monthly- **Prioridade:** Crítica- **Cliente:** Pierre Fabre

#### **NEO-91299: Atividade de Entrega Contínua**- **Status:** Fechado- **Por que a Documentação Necessária:** Nova atividade de fluxo de trabalho para cenários de entrega recorrentes- **DOCAC existente:** DOCAC-13586 (Novo status), DOCAC-13808 (Fechado - ajuda contextual)- **Escopo da Documentação:**   - Configuração de atividade de entrega contínua   - Requisitos do seletor de modelo de entrega   - Processar tratamento de erros   - Integração do fluxo de trabalho   - Casos de uso e exemplos- **Público-alvo:** usuários técnicos, designers de fluxo de trabalho- **Versão:** AC-UI-26.01.06

#### **NEO-90130: Carregamento de Arquivo Push Multilíngue (H&amp;M)**- **Status:** Fechado- **Por que a documentação era necessária:** paridade de recursos OOTB com ACS para push multilíngue baseado em arquivo- **DOCAC Existente:** DOCAC-13606 (Novo status)- **Escopo da Documentação:**   - Upload de arquivo CSV para notificações por push multilíngues   - Especificações de formato de arquivo   - Mapeamento de campo   - Configurações específicas do iOS e Android   - Manuseio de tipo de mensagem de dados   - Solução de problemas e problemas conhecidos- **Público-alvo:** usuários de marketing, gerentes de campanha- **Versão:** AC-UI-25-10-Monthly, AC-UI-25.11.03- **Prioridade:** Crítica- **Cliente:** H&amp;M (ACS para migração ACC)

#### **NEO-92942: Filtros Predefinidos - Opção Compartilhada**- **Status:** Resolvido- **Por que a documentação precisava:** aprimoramento da funcionalidade do construtor de regras- **DOCAC existente:** DOCAC-13697 (status de Revisão do Código), DOCAC-13522 (Fechado - auxiliar)- **Escopo da Documentação:**   - Opção compartilhada para filtros predefinidos   - Gerenciamento da visibilidade de filtros com outros operadores   - Comportamentos de Jornada ACC vs Brand   - Gerenciamento de lista de filtros- **Público-alvo:** Todos os usuários, designers de consulta- **Versão:** Versão Principal- **FF:** enable-query-filter-shared

### 2.3 PRIORIDADE BAIXA - Aprimoramento do Editor de conteúdo

#### **NEO-88838: Variáveis de Tema em Fragmentos**- **Status:** Novo (Em Espera)- **Por que a documentação era necessária:** funcionalidade do tema de email do Designer- **DOCAC existente:** DOCAC-12941 (Novo status)- **Escopo da Documentação:**   - Uso de variáveis de tema em fragmentos de email   - Configuração do tema   - Gerenciamento de variáveis   - Práticas recomendadas- **Público-alvo:** designers de email, usuários de marketing- **Versão:** AC-UI-26-01-Monthly- **Observação:** o recurso está suspenso e a visita do lado de Acrite está pendente

&#x200B;---

## &#x200B;3. Os bilhetes NÃO exigem documentação

### 3.1 Cancelado/Não Mais Aplicável

| ID do tíquete | Título | Motivo |
|-----------|-------|--------|
| NEO-91566 | Rastreamento do CTA na web | Nenhum trabalho de interface esperado; informações pendentes da MSFT |
| NEO-91564 | Suporte à interface multilíngue do AEM | Trabalho da interface do usuário gerenciado por uma equipe diferente |
| NEO-91567 | Suporte a recurso NRT | Nenhum impacto na interface da Web; especificação disponível |
| NEO-91563 | API Rest transacional | Nenhum trabalho de interface da Web; atualização de instância pendente |
| NEO-92151 | Enriquecimento de perfil Fase 2 | A história não tem tarefas; está marcada como não se aplica mais |

### 3.2 Tickets de rastreamento/espaço reservado

| ID do tíquete | Título | Motivo |
|-----------|-------|--------|
| NEO-92400 | Melhorias na versão - 26 de janeiro | Espaço reservado para rastrear a conclusão de melhorias |

&#x200B;---

## &#x200B;4. Tíquetes DOCAC propostos

### 4.1 Novos tíquetes DOCAC necessários

#### **DOCAC-XXXX: Agendamento de Entrega com Suporte a Fuso Horário**&#x200B;**Tíquete Pai:** NEO-93487&#x200B;**Prioridade:** Crítica&#x200B;**Versão do Target:** AC-UI-26-01-Monthly&#x200B;**Descrição:**&#x200B;Documente o novo processo de computação de agendamento de delivery que permite o agendamento de delivery com base em fuso horário semelhante à funcionalidade ACS. Esse recurso permite que os profissionais de marketing enviem comunicações com base nos fusos horários dos recipients usando fórmulas calculadas, especialmente importantes para mercados de vários fusos horários, como os EUA.

**Escopo:**
- Guia de configuração para agendamento com base no fuso horário
- Exemplos de fórmulas calculadas
- Cenários de mercado com vários fusos horários
- Guia de migração do ACS
- Práticas recomendadas e limitações

**Cliente:** H&amp;M (essencial para migração de ACS para ACC)

#### **DOCAC-XXXX: Configuração de Conta Externa do Web Analytics**&#x200B;**Tíquete Pai:** NEO-92668&#x200B;**Prioridade:** Normal&#x200B;**Versão do Target:** AC-UI-26-01-Monthly&#x200B;**Descrição:**&#x200B;Documente a configuração e o uso do tipo de conta externa do Web Analytics na interface do usuário da Web.

**Escopo:**
- Etapas de criação da conta externa
- Parâmetros de configuração
- Integração com o rastreamento de delivery
- Recursos de relatórios
- Solução de problemas

&#x200B;---

### 4.2 Tíquetes DOCAC EXISTENTES a serem atualizados

#### **DOCAC-13104: Teste A/B**&#x200B;**Status:** Novo&#x200B;**Tíquete Pai:** NEO-86754&#x200B;**Ação necessária:** Iniciar documentação - recurso no desenvolvimento ativo&#x200B;**Entrega estimada:** fevereiro de 2026 (conclusão de desenvolvimento pendente)

#### **DOCAC-11070 &amp; DOCAC-13432: Relatórios Dinâmicos**&#x200B;**Status:** Fechado/Resolvido&#x200B;**Tíquete Pai:** NEO-80973&#x200B;**Ação necessária:**- Atualização para disponibilidade geral (não apenas 8.7)- Documentar métricas conflitantes com relatórios herdados- Verificar documentação de suporte de idioma

#### **DOCAC-13826: Criação de Esquemas**&#x200B;**Status:** Novo&#x200B;**Tíquete Pai:** NEO-76126&#x200B;**Ação necessária:**- Documentação da fase 2 (navegar + CRUD + definição de formulário)- Preparação para a Fase 3 (criar/estender esquemas) - Fim do ETA fev

#### **DOCAC-13829: Cópias online/Cópias de idioma do AEM**&#x200B;**Status:** Resolvido&#x200B;**Tíquete Pai:** NEO-86753&#x200B;**Ação necessária:** verifique o status atual e atualize conforme necessário

#### **DOCAC-13565: Rich Push Multilíngue**&#x200B;**Status:** Novo&#x200B;**Tíquete Pai:** NEO-90183&#x200B;**Ação necessária:** Concluir documentação - recurso entregue em novembro de 2025

#### **DOCAC-13827: Processo de Aprovação**&#x200B;**Status:** Novo&#x200B;**Tíquete Pai:** NEO-84916&#x200B;**Ação necessária:** Concluir documentação - recurso entregue em novembro de 2025

#### **DOCAC-13586 &amp; DOCAC-13808: entrega contínua**&#x200B;**Status:** Novo/Fechado&#x200B;**Tíquete Pai:** NEO-91299&#x200B;**Ação necessária:** Conclua a documentação principal (13586) - recurso entregue

#### **DOCAC-13606: Carregamento de Arquivo Push Multilíngue**&#x200B;**Status:** Novo&#x200B;**Tíquete Pai:** NEO-90130&#x200B;**Ação necessária:** Concluir documentação - recurso entregue

#### **DOCAC-13697 &amp; DOCAC-13522: Filtros Compartilhados Predefinidos**&#x200B;**Status:** Revisão/Fechamento de Código&#x200B;**Tíquete Pai:** NEO-92942&#x200B;**Ação necessária:** finalizar documentação (13697)

#### **DOCAC-12941: Temas em Designer de Email**&#x200B;**Status:** Novo&#x200B;**Tíquete Pai:** NEO-88838&#x200B;**Ação necessária:** Em espera pendente revisitar recurso

&#x200B;---

## &#x200B;5. Perguntas abertas e informações ausentes

### 5.1 Por recurso

#### **Teste A/B (NEO-86754)**- [ ] Qual é o status final de validação da interface do usuário/UX?- [ ] Existem limitações específicas para mensagens transacionais?- [ ] Como isso se integra à visualização de conteúdo Acrite (bloqueio NEO-92516)?- [ ] Quais são os recursos de simulação/visualização de cada variante?

#### **Relatórios Dinâmicos (NEO-80973)**- [ ] Qual é o status da reativação do ambiente de demonstração?- [ ] Lista completa de métricas conflitantes com relatórios herdados?- [ ] Matriz detalhada de suporte a idiomas?- [ ] Comparação de desempenho com relatórios herdados?

#### **Criação de esquemas (NEO-76126)**- [ ] Quando a Fase 2 FF será ativada?- [ ] ETA confirmado para a Fase 3 (criar/estender esquemas)?- [ ] Quais são os requisitos de configuração do ambiente?- [ ] Alguma limitação em relação à funcionalidade do Console do Cliente?

#### **Agendamento de Entrega (NEO-93487)**- [ ] A demonstração de recursos com o PM está agendada?- [ ] As especificações funcionais completas estão disponíveis?- [ ] modelos de interface do usuário finalizados e revisados?- [ ] Qual é a sintaxe/estrutura da fórmula exata?

#### **AEM Live/Cópias de Idioma (NEO-86753)**- [ ] Qual é o status atual da equipe do Himanshu?- [ ] Atualizou a linha do tempo de entrega?- [ ] Alguma dependência da versão do AEM?

#### **Web Analytics (NEO-92668)**- [ ] O que é o status de disponibilidade do ambiente?- [ ] Concluir os requisitos de configuração?- [ ] Plataformas de análise com suporte?

#### **Variáveis de tema em fragmentos (NEO-88838)**- [ ] Quando o Acrite revisitará o recurso?- [ ] Isso ainda está planejado para AC-UI-26-01?

### 5.2 Por versão

#### **AC-UI-26-01-Monthly (Janeiro de 2026)**- [ ] Confirmação da data de lançamento oficial?- [ Data de congelamento do recurso ]?- [ ] Testando a linha do tempo de conclusão?- [ ] Prazo de entrega da documentação?

#### **Recursos Entregues em novembro de 2025**- [ ] Quais recursos já estão ativados na produção?- [ ] Problemas conhecidos ou limitações descobertas após o lançamento?- [ ] Comentários de clientes recebidos?

### 5.3 Processo de documentação

- [ ] Quem são os SMEs de cada recurso?
- [ ] Qual é o processo de revisão da documentação?
- [ ] Idioma da documentação do Target (somente EN ou multilíngue)?
- [ Requisitos de plataforma/formato da documentação do ]?
- [ ] Capturas de tela e demonstração da disponibilidade do ambiente?

&#x200B;---

## &#x200B;6. Impacto e escalonamentos no cliente

### 6.1 Tíquetes Críticos do Cliente

| Cliente | Tíquete | Recurso | Impacto |
|----------|--------|---------|--------|
| **H&amp;M** | NEO-93487 | Agendamento de entrega | Mais de 50 mercados; requisitos de entrega em vários fusos horários; bloqueador de migração de ACS para ACC |
| **H&amp;M** | NEO-90130 | Upload de arquivo push multilíngue | Essencial para migração de ACS para ACC; reduz os custos operacionais |
| **Pierre Fabre** | NEO-84916 | Processo de aprovação | Requisitos normativos e de fluxo de trabalho |

### 6.2 Recursos específicos do Microsoft

| Tíquete | Recurso | Status | Observações |
|--------|---------|--------|-------|
| NEO-86753 | AEM Live/Cópias de idioma | Novo | Altamente usado pelo Microsoft |
| NEO-91566 | Rastreamento CTA | Fechado/Não mais se aplica | Informações pendentes da MSFT |
| NEO-91567 | Recurso NRT | Resolvido/Sem impacto na interface do usuário | Novo recurso ACS para MSFT |

&#x200B;---

## &#x200B;7. Prioridades de documentação e cronograma

### 7.1 Ação imediata necessária (janeiro de 2026)

**ALTA PRIORIDADE - Entregue mas não documentado:**
1. **NEO-90183** - Rich Push Multilíngue (DOCAC-13565)
2. **NEO-84916** - Processo de Aprovação (DOCAC-13827)
3. **NEO-91299** - Entrega contínua (DOCAC-13586)
4. **NEO-90130** - Carregamento de arquivo de push multilíngue (DOCAC-13606)

### 7.2 Em andamento - Desenvolvimento em andamento (fevereiro-março de 2026)

**PRIORIDADE CRÍTICA:**
1. **NEO-86754** - Teste A/B (DOCAC-13104) - Vencimento: fevereiro de 2026
2. **NEO-76126** - Criação de Esquemas (DOCAC-13826) - Fase 2: fevereiro, Fase 3: Fim de fevereiro
3. **NEO-93487** - Agendamento de entrega (NOVO DOCAC) - Escalonamento crítico do cliente

**PRIORIDADE NORMAL:**
1. **NEO-80973** - Relatórios Dinâmicos (Atualização DOCAC-11070)
2. **NEO-92668** - Web Analytics (NOVO DOCAC)
3. **NEO-86753** - AEM Live/Cópias de Idioma (DOCAC-13829)

### 7.3 Em espera/futuro

1. **NEO-88838** - Variáveis de tema (DOCAC-12941) - Revisita de autor pendente

&#x200B;---

## &#x200B;8. Próximas etapas

### 8.1 Ações da equipe de documentação1. **Priorizar recursos entregues** sem documentação (Seção 7.1)2. **Criar novos tíquetes DOCAC** para NEO-93487 e NEO-926683. **Atualizar tíquetes DOCAC** existentes com escopo detalhado (Seção 4.2)4. **Agendar entrevistas com SME** para Teste A/B, Esquemas e Agendamento de Entrega5. **Colete capturas de tela** e prepare ambientes de demonstração6. **Revisar e finalizar** limitações de idioma para Relatórios Dinâmicos

### 8.2 Coleta de informações1. **Contate os líderes de engenharia** para obter atualizações de status sobre:   - Validação final do teste A/B   - Linha do tempo da Fase 2/3 dos esquemas   - Especificações do Agendamento de entrega2. **Agendar demonstrações de recursos** com o Gerenciamento de produtos3. **Colete o feedback do cliente** da H&amp;M e da Pierre Fabre4. **Verifique a disponibilidade do ambiente** para o Web Analytics e Dynamic Reporting

### 8.3 Coordenação1. **Sincronizar com a equipe do Himanshu** no AEM Live/Language Copies2. **Coordenar com a equipe Acrite** sobre o status das Variáveis de Tema3. **Acompanhe os recursos específicos do Microsoft** com a equipe de conta

&#x200B;---

## Histórico do documento

| Data | Autor | Versão | Alterações |
|------|--------|---------|---------|
| 01-2026-12 | Assistente de IA | 1,0 | Análise inicial de consultas Jira |

&#x200B;---

## Apêndice: Consultas Jira analisadas

1. `project = NEO AND fixVersion = AC-UI-26-01-Monthly and type = story order by status`
2. `issueFunction in linkedIssuesOf('key=NEO-92400', 'is implemented by')`
3. `project = NEO AND fixVersion = AC-UI-25-11-Monthly and type = story order by status`
4. `project = NEO AND fixVersion = AC-UI-25-11-Monthly and fixVersion != 8.8.2 and type = story order by status`

**Total de Resultados:** 19 tíquetes exclusivos analisados

