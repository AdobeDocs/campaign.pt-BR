---
title: Práticas recomendadas de segurança do Campaign
description: Introdução às práticas recomendadas de segurança do Campaign
feature: Privacy, PI
role: Developer
level: Beginner
exl-id: 1d593c8e-4b32-4902-93a7-7b18cef27cac
source-git-commit: 5ab598d904bf900bcb4c01680e1b4730881ff8a5
workflow-type: tm+mt
source-wordcount: '583'
ht-degree: 25%

---

# Práticas recomendadas de segurança do Campaign {#ac-security}

No Adobe, levamos a segurança da sua experiência digital muito a sério. As práticas de segurança estão profundamente enraizadas em nossos processos e ferramentas internos de desenvolvimento e operações de software e são rigorosamente seguidas por nossas equipes multifuncionais para evitar, detectar e responder a incidentes de maneira adequada.

Além disso, nosso trabalho colaborativo com parceiros, pesquisadores líderes, instituições de pesquisa de segurança e outras organizações do setor nos ajuda a nos manter atualizados com as mais recentes ameaças e vulnerabilidades e regularmente incorporamos técnicas avançadas de segurança aos produtos e serviços que oferecemos.

## Privacidade

A configuração e a proteção da privacidade são um elemento essencial da otimização da segurança. Estas são algumas das práticas recomendadas a serem seguidas em relação à privacidade:

* Protect as informações pessoais (PI) do cliente usando HTTPS em vez de HTTP
* Uso [Restrição de visualização de PI](../dev/restrict-pi-view.md) proteger a privacidade e impedir que os dados sejam utilizados indevidamente
* Verifique se as senhas criptografadas são restritas
* Proteja as páginas que podem conter informações pessoais, como mirror pages, aplicativos web, etc.


>[!NOTE]
>
>Como usuário do Managed Cloud Service, o Adobe trabalhará com você para implementar essas configurações no seu ambiente.


## Gerenciamento de acesso

O gerenciamento de acesso é uma parte importante do fortalecimento da segurança. Estas são algumas das principais práticas recomendadas do:

* Criar grupos de segurança suficientes
* Verifique se cada operador tem os direitos de acesso apropriados

Saiba mais sobre permissões no [nesta seção](../start/gs-permissions.md)

## Diretrizes de codificação

Ao desenvolver no Adobe Campaign (workflows, Javascript, JSSP etc.), sempre siga estas diretrizes:

* **Scripting**: tente evitar instruções SQL. Use funções parametrizadas em vez de concatenação de strings e evite a injeção de SQL colocando as funções SQL a serem utilizadas na lista de permissões.

* **Proteger o modelo de dados**: usar direitos nomeados para limitar as ações do operador, adicionar filtros do sistema (sysFilter)

* **Adicionar captchas em aplicações web**: adicione captchas em suas páginas de aterrissagem e páginas de assinatura públicas.

Saiba mais em [Documentação do Adobe Campaign Classic v7](https://experienceleague.adobe.com/docs/campaign-classic/using/installing-campaign-classic/security-privacy/scripting-coding-guidelines.html#installing-campaign-classic){target="_blank"}.


## Personalização

Ao adicionar links personalizados ao seu conteúdo, sempre evite qualquer personalização na parte do nome do host do URL para evitar possíveis brechas de segurança. Os exemplos a seguir nunca devem ser usados em todos os atributos de URL &lt;`a href="">` ou `<img src="">`:

* `<%= url >`
* `https://<%= url >`
* `https://<%= domain >/path`
* `https://<%= sub-domain >.domain.tld/path`
* `https://sub.domain<%= main domain %>/path`

## Restrição de dados

Você precisa ter certeza que as senhas criptografadas não estarão acessíveis a um usuário autenticado de baixo privilégio. Para fazer isso, há duas formas principais: restringir o acesso aos campos de senha somente ou à entidade inteira.

Essa restrição permite remover campos de senhas, mas deixa a conta externa acessível a partir da interface para todos os usuários. Saiba mais [nesta página](../dev/restrict-pi-view.md).

1. Entrar **[!UICONTROL Administration]** > **[!UICONTROL Configuration]** > **[!UICONTROL Data schemas]**.

1. Criar um novo **[!UICONTROL Extension of a schema]**.

1. Escolher **[!UICONTROL External Account]** (extAccount).

1. Na última tela, você pode editar o novo srcSchema para restringir o acesso a todos os campos de senha:

   Você pode substituir o elemento principal (`<element name="extAccount" ... >`) por:

   ```
   <element name="extAccount">
       <attribute accessibleIf="$(loginId) = 0 or $(login) = 'admin'" name="password"/>
       <attribute accessibleIf="$(loginId) = 0 or $(login) = 'admin'" name="clientSecret"/>
   
       <element name="s3Account">
           <attribute accessibleIf="$(loginId) = 0 or $(login) = 'admin'" name="awsSecret"/>
       </element>
       <element name="wapPush">
           <attribute accessibleIf="$(loginId) = 0 or $(login) = 'admin'" name="password"/>
           <attribute accessibleIf="$(loginId) = 0 or $(login) = 'admin'" name="clientSecret"/>
       </element>
       <element name="mms">
           <attribute accessibleIf="$(loginId) = 0 or $(login) = 'admin'" name="password"/>
           <attribute accessibleIf="$(loginId) = 0 or $(login) = 'admin'" name="clientSecret"/>
       </element>
   </element>
   ```

   Então, seu srcSchema estendido pode se parecer com:

   ```
   <...>
       <element name="extAccount">
           <attribute accessibleIf="$(loginId) = 0 or $(login) = 'admin'" name="password"/>
           <attribute accessibleIf="$(loginId) = 0 or $(login) = 'admin'" name="clientSecret"/>
   
           <element name="s3Account">
               <attribute accessibleIf="$(loginId) = 0 or $(login) = 'admin'" name="awsSecret"/>
           </element>
           <element name="wapPush">
               <attribute accessibleIf="$(loginId) = 0 or $(login) = 'admin'" name="password"/>
               <attribute accessibleIf="$(loginId) = 0 or $(login) = 'admin'" name="clientSecret"/>
           </element>
           <element name="mms">
               <attribute accessibleIf="$(loginId) = 0 or $(login) = 'admin'" name="password"/>
               <attribute accessibleIf="$(loginId) = 0 or $(login) = 'admin'" name="clientSecret"/>
           </element>
       </element>
   <...> 
   ```

   >[!NOTE]
   >
   >Você pode substituir `$(loginId) = 0 or $(login) = 'admin'` por `hasNamedRight('admin')` para permitir que todos os usuários com direito de administrador vejam essas senhas.


## Gerenciamento de acesso

O gerenciamento de acesso é uma parte importante do fortalecimento da segurança. Estas são algumas das principais práticas recomendadas do:

* Criar grupos de segurança suficientes
* Verifique se cada operador tem os direitos de acesso apropriados

Saiba mais sobre permissões no [nesta seção](../start/gs-permissions.md).

## Diretrizes de codificação

Ao desenvolver no Adobe Campaign (workflows, Javascript, JSSP etc.), sempre siga estas diretrizes:

* **Scripting**: tente evitar instruções SQL. Use funções parametrizadas em vez de concatenação de strings e evite a injeção de SQL colocando as funções SQL a serem utilizadas na lista de permissões.

* **Proteger o modelo de dados**: usar direitos nomeados para limitar as ações do operador, adicionar filtros do sistema (sysFilter)

* **Adicionar captchas em aplicações web**: adicione captchas em suas páginas de aterrissagem e páginas de assinatura públicas.

Saiba mais em [Documentação do Adobe Campaign Classic v7](https://experienceleague.adobe.com/docs/campaign-classic/using/installing-campaign-classic/security-privacy/scripting-coding-guidelines.html#installing-campaign-classic){target="_blank"}.
