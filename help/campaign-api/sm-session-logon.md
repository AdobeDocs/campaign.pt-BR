---
source-git-commit: ffa29306eb4402ed20c7d04bdbbaffd4dde5bfe4
workflow-type: tm+mt
source-wordcount: '173'
ht-degree: 3%
---
# Logon

Abre uma sessão

```text
[ String sessionToken, sessionInfo sessionInfo, String securityToken ] = Logon ( String login, String password, XML parameters )
```

## Parâmetros

Conta de usuário do **logon**

**senha** Senha associada ao logon do usuário

**parâmetros** configurações de conexão

## Retornar valor(es)

**sessionToken** Token de sessão

Parâmetros da sessão **sessionInfo**

**securityToken** Token de segurança

## Configuração do mecanismo de bloqueio de conta

Um mecanismo de bloqueio de conta está disponível na API logon(). Impede novas tentativas de logon após um determinado número de tentativas com falha consecutivas em um intervalo de tempo especificado.

Quatro opções estão disponíveis para configurar o mecanismo de bloqueio:

* **XtkSecurity\_max\_Unsuccessul\_Attempts\_Allowed**: máximo de tentativas malsucedidas de bloquear uma chave dentro da duração especificada. O valor padrão é 3.
* **XtkSecurity\_Initial\_Ban\_Duration**: duração para a chave ser banida pela primeira vez. A duração padrão é de 5 minutos.
* **XtkSecurity\_Max\_Ban\_Duration**: duração máxima para a qual uma chave pode ser banida.
* **XtkSecurity\_Examine\_Window**: janela de tempo para rastrear o número de tentativas de logon malsucedidas para proibir uma chave inválida. A duração padrão é de 10 minutos.

Por exemplo, se alguém tentar 3 tentativas malsucedidas em 10 minutos, sua chave será bloqueada por 5 minutos.

## Recursos

**Esquema:** [xtk:session](s-xtk-session.md)

**Estático:**

Sim
