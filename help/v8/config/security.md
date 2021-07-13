---
product: Adobe Campaign
title: Práticas recomendadas de segurança do Campaign
description: Introdução às práticas recomendadas de segurança do Campaign
source-git-commit: c61d8aa8e0a68ccc81a6141782f860daf061bc61
workflow-type: tm+mt
source-wordcount: '503'
ht-degree: 22%

---

# Práticas recomendadas de segurança do Campaign {#ac-security}

No Adobe, levamos a segurança de sua experiência digital muito a sério. As práticas de segurança estão profundamente enraizadas em nossos processos e ferramentas internos de desenvolvimento e operações de software e são rigorosamente seguidas por nossas equipes multifuncionais para prevenir, detectar e responder a incidentes de maneira conveniente.

Além disso, nosso trabalho colaborativo com parceiros, pesquisadores líderes, instituições de pesquisa de segurança e outras organizações do setor nos ajuda a nos manter atualizados com as mais recentes ameaças e vulnerabilidades e incorporamos regularmente técnicas avançadas de segurança nos produtos e serviços que oferecemos.

## Privacidade

A configuração e proteção da privacidade é um elemento essencial da otimização da segurança. Estas são algumas das práticas recomendadas relacionadas à privacidade:

* Protect suas informações pessoais (PI) do cliente usando HTTPS em vez de HTTP
* Use [Restrição de exibição PI](../dev/restrict-pi-view.md) para proteger a privacidade e impedir que os dados sejam utilizados incorretamente
* Certifique-se de que as senhas criptografadas sejam restritas
* Proteja as páginas que podem conter informações pessoais, como mirror pages, aplicativos web, etc.

?? Como usuário do Managed Cloud Services, o Adobe trabalhará com você para implementar essas configurações no ambiente.

## Personalização

Ao adicionar links personalizados ao seu conteúdo, sempre evite qualquer personalização na parte do nome do host do URL para evitar possíveis brechas de segurança. Os exemplos a seguir nunca devem ser usados em todos os atributos de URL &lt;`a href="">` ou `<img src="">`:

* `<%= url >`
* `https://<%= url >`
* `https://<%= domain >/path`
* `https://<%= sub-domain >.domain.tld/path`
* `https://sub.domain<%= main domain %>/path`

## Restrição de dados

Você precisa ter certeza que as senhas criptografadas não estarão acessíveis a um usuário autenticado de baixo privilégio. Para fazer isso, há duas maneiras principais: restringir o acesso apenas aos campos de senha ou à entidade inteira.

Essa restrição permite remover campos de senhas, mas deixa a conta externa acessível a partir da interface para todos os usuários. Saiba mais [nesta página](../dev/restrict-pi-view.md).

1. Vá em **[!UICONTROL Administration]** > **[!UICONTROL Configuration]** > **[!UICONTROL Data schemas]**.

1. Crie um novo **[!UICONTROL Extension of a schema]**.

1. Escolha **[!UICONTROL External Account]** (extAccount).

1. Na última tela, você pode editar seu novo srcSchema para restringir o acesso a todos os campos de senha:

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
   >Você pode substituir `$(loginId) = 0 or $(login) = 'admin'` por `hasNamedRight('admin')` para permitir que todos os usuários administradores vejam essas senhas.


## Gerenciamento de acesso

O gerenciamento de acesso é uma parte importante do fortalecimento da segurança. Estas são algumas das principais práticas recomendadas:

* Criar grupos de segurança suficientes
* Verifique se cada operador tem os direitos de acesso apropriados
* Evite usar o operador administrador e evite ter muitos operadores no grupo de administradores

↗️ Saiba mais em [documentação do Adobe Campaign Classic v7](https://experienceleague.adobe.com/docs/campaign-classic/using/installing-campaign-classic/security-privacy/access-management.html?lang=en#webapp-operator){target=&quot;_blank&quot;}

## Diretrizes de codificação

Ao desenvolver no Adobe Campaign (fluxos de trabalho, Javascript, JSSP etc.), sempre siga estas diretrizes:

* **Scripting**: tente evitar instruções SQL. Use funções parametrizadas em vez de concatenação de strings e evite a injeção de SQL colocando as funções SQL a serem utilizadas na lista de permissões.

* **Proteger o modelo** de dados: use direitos nomeados para limitar as ações do operador, adicione filtros do sistema (sysFilter)

* **Adicionar captchas em aplicações** web: adicione captchas em suas páginas de aterrissagem e páginas de assinatura públicas.

↗️ Saiba mais em [documentação do Adobe Campaign Classic v7](https://experienceleague.adobe.com/docs/campaign-classic/using/installing-campaign-classic/security-privacy/scripting-coding-guidelines.html?lang=en#installing-campaign-classic){target=&quot;_blank&quot;}
