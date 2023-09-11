---
title: Migrar operadores do Campaign para o Adobe Identity Management System (IMS)
description: Saiba como migrar operadores do Campaign para o Adobe Identity Management System (IMS)
hide: true
hidefromtoc: true
source-git-commit: 74d97c4c61a305aff1d2f108a8a24cb6943dea07
workflow-type: tm+mt
source-wordcount: '1036'
ht-degree: 4%

---

# Migrar operadores do Campaign para o Adobe Identity Management System (IMS) {#migrate-users-to-ims}

A partir do Campaign v8.6, o processo de autenticação para o Campaign v8 está sendo aprimorado. Todos os operadores usarão [Sistema Adobe Identity Management (IMS)](https://helpx.adobe.com/br/enterprise/using/identity.html){target="_blank"} **somente** para se conectar ao Campaign. A conexão com usuário/senha (também conhecida como autenticação nativa) não será mais permitida. O Adobe recomenda executar essa migração no Campaign v8.5.2 para migrar sem problemas para o Campaign v8.6.

Como cliente de serviços gerenciados do Campaign Classic v7, se estiver migrando para o Campaign v8, esse procedimento também se aplica a você.

Este artigo detalha as etapas necessárias para migrar um operador técnico para uma conta técnica no console do Adobe Developer.

## O que mudou?{#move-to-ims-changes}

Com o Campaign v8, todos os usuários regulares já devem se conectar ao console do cliente do Adobe Campaign usando sua Adobe ID, por meio do Adobe Identity Management System (IMS). No entanto, com algumas configurações mais antigas, as conexões de usuário/senha ainda estavam disponíveis. **Isso não será mais permitido a partir do Campaign v8.6.**

Além disso, como parte do esforço para reforçar a segurança e o processo de autenticação, o aplicativo cliente do Adobe Campaign agora chama as APIs do Campaign diretamente usando o token de conta técnica do IMS. migração para os operadores técnicos é apresentada em pormenor num artigo [esta página](ims-migration.md).

Essa alteração é aplicável a partir do Campaign v8.5.2 e será **obrigatório** a partir do Campaign v8.6.


## Você será afetado?{#migrate-ims-impacts}

Se os operadores em sua organização estiverem se conectando ao console do cliente do Campaign usando seu logon/senha (também conhecido como. autenticação nativa), você será afetado e deverá migrar esse(s) operador(es) para o Adobe IMS conforme detalhado abaixo.

Migração para [Sistema Adobe Identity Management (IMS)](https://helpx.adobe.com/br/enterprise/using/identity.html){target="_blank"} O é uma obrigação de segurança para tornar seus ambientes seguros e padronizados, pois a maioria das outras soluções e aplicativos da Adobe Experience Cloud já está no IMS.

## Como migrar?{#ims-migration-procedure}

### Pré-requisitos{#ims-migration-prerequisites}

Antes de iniciar o processo de migração, entre em contato com o representante do Adobe (Gerenciador de transição) para que as equipes técnicas do Adobe possam migrar seus grupos de operadores e direitos nomeados existentes para o Adobe Identity Management System (IMS).

### Principais etapas {#ims-migration-steps}

As principais etapas dessa migração estão listadas abaixo:

1. O Adobe atualiza seus ambientes para o Campaign v8.5.2.
1. Após a atualização, ainda será possível criar novos usuários com ambos os métodos, como usuário nativo ou com IMS.
1. O administrador interno do Campaign deve adicionar emails exclusivos a todos os usuários nativos no console do cliente do Campaign e confirmar para o Adobe Transition Manager depois de concluído. Essa etapa está detalhada em [nesta seção](#ims-migration-id).
1. Trabalhe com o Adobe para garantir uma data para o Adobe executar a migração automatizada para seus usuários (operadores) e perfis de produto não técnicos. Essa etapa requer uma janela de uma hora sem tempo de inatividade para nenhuma de suas instâncias.
1. O administrador interno do Campaign valida essas alterações e fornece aprovação. Após essa migração, não será mais necessário criar nenhum outro operador autenticado com este logon e senha.

Agora é possível planejar a migração de usuários técnicos para o IMS de acordo com [esta nota técnica](ims-migration.md)e confirme para o Gerenciador de transição do Adobe quando concluído.
O Adobe marcará a migração como concluída e ativará os sinalizadores para bloquear a criação de novos usuários nativos e o logon de usuários nativos.

## Perguntas frequentes {#ims-migration-faq}

### Quando posso iniciar a migração? {#ims-migration-start}

Um pré-requisito para a migração para o [Sistema Adobe Identity Management (IMS)](https://helpx.adobe.com/br/enterprise/using/identity.html){target="_blank"} é atualizar seu ambiente para o Campaign v8.5.2.

Você pode iniciar a migração do IMS no ambiente de preparo depois que ele for atualizado para o Campaign v8.5.2 e planejar adequadamente o ambiente de produção.

### O que acontece após a atualização de build para o Campaign v8.5.2? {#ims-migration-after-upgrade}

Depois que seus ambientes forem atualizados para o Campaign v8.5.2, você poderá iniciar sua transição para [Sistema Adobe Identity Management (IMS)](https://helpx.adobe.com/br/enterprise/using/identity.html){target="_blank"}.

A criação de novos usuários nativos ainda é permitida até que a migração do IMS seja concluída.

### Quando a migração é concluída? {#ims-migration-end}

Quando a migração do usuário final e a migração técnica do usuário para o Adobe Identity Management System (IMS) estiverem concluídas, você deverá entrar em contato com o Gerenciador de transição do Adobe para que o Adobe possa marcar a migração como concluída, bloquear a criação de usuários no console do cliente e desativar o logon do usuário nativo.


### Como criar usuários após a migração? {#ims-migration-native}

Quando a migração completa do IMS for concluída, o Adobe aplicará as restrições que bloquearão a criação de novos usuários nativos. Essas restrições não são aplicadas até que a migração do IMS seja concluída.

Para novos clientes - a criação de novos usuários nativos não é permitida desde o início.

Como administrador do Campaign, você pode conceder permissões aos usuários da organização por meio do Adobe Admin Console e do Console do cliente do Campaign. Os usuários fazem logon no Adobe Campaign com a Adobe ID. Saiba mais [nesta documentação](../../v8/start/gs-permissions.md).

### Como adicionar emails para usuários nativos atuais? {#ims-migration-id}

Como administrador do Campaign, você deve adicionar IDs de email para todos os usuários nativos do console do cliente. Para fazer isso, siga as etapas abaixo:

1. Conecte-se ao console do cliente e navegue até **Administração > Gerenciamento de acesso > Operadores**.
1. Selecione o operador a ser atualizado na lista de operadores.
1. Insira o email do operador nas **Pontos de contato** seção do formulário do operador.
1. Salve as alterações.

Você também pode importar um arquivo CSV para atualizar todos os perfis de operador com os respectivos emails.


### Como fazer logon no Campaign via IMS? {#ims-migration-log}

Saiba como se conectar ao Campaign com sua Adobe ID no [nesta seção](../../v8/start/connect.md).

### Haverá um tempo de inatividade durante essa migração? {#ims-migration-downtime}

Para finalizar a migração (migrar usuários e perfis de produtos), o Adobe requer uma janela de uma hora sem tempo de inatividade para nenhuma de suas instâncias (workflows etc.).

Durante esse período, todos os usuários do Campaign precisam fazer logoff e fazer logon novamente com sua Adobe ID após a conclusão da migração para o IMS.

### O que acontece com os usuários conectados durante a migração de usuário do IMS? {#ims-migration-log-off}

A Adobe recomenda que todos os usuários sejam desconectados durante a janela de migração.

### Os usuários em minha organização já estão usando o IMS. Ainda preciso executar a Migração do IMS?

Há dois aspectos nesta migração: migração de usuários finais e migração de usuários técnicos (usada em APIs do no código personalizado).

Se todos os usuários (operadores do Campaign) estiverem no IMS, não será necessário executar essa migração. No entanto, ainda é necessário migrar Usuários técnicos que podem ter sido usados no código personalizado. Saiba mais [nesta página](ims-migration.md).

Quando essa migração for concluída, você deverá entrar em contato com o Gerenciador de transição do Adobe para que o Adobe conclua a migração.