---
title: Notas de versão anteriores do Campaign v8
description: Lançamento antecipado do Campaign v8
feature: Release Notes
role: Admin, Developer, User
level: Beginner, Intermediate, Experienced
hide: true
hidefromtoc: true
exl-id: a45f7b22-44c7-4dad-af0a-ae8f683ae3d9
source-git-commit: e0ec2940db3120dc8fbfd17dd2f5083bbf31232c
workflow-type: tm+mt
source-wordcount: '586'
ht-degree: 33%

---

# Notas de versão anteriores {#e-new-release}

Esta página descreve as melhorias e correções incluídas no próximo lançamento do Campaign v8. Esse conteúdo está sujeito a alterações sem aviso prévio até a data de lançamento. As notas de versão oficiais estão disponíveis nesta [página](../start/release-notes.md).

## Versão 8.5.1 {#release-8-5}

_30 de junho de 2023_

**Novidades**

<table> 
<thead>
<tr> 
<th> <strong>Serviço aprimorado de notificação por push</strong><br /> </th> 
</tr> 
</thead> 
<tbody> 
<tr> 
<td><p>O Campaign 8.5.1 está apresentando nosso mais recente serviço de notificação por push no v8, viabilizado por uma estrutura robusta criada em uma tecnologia de ponta moderna. Este serviço foi projetado para desbloquear novos níveis de escalabilidade, garantindo que suas notificações possam alcançar um público maior com eficiência contínua. Com nossa infraestrutura aprimorada e nossos processos otimizados, você pode esperar maior escala e confiabilidade, permitindo que você interaja e se conecte com seus usuários de aplicativos móveis como nunca. Esse recurso só está disponível para um grupo selecionado de clientes (disponibilidade limitada).</p>
</td> 
</tr> 
</tbody> 
</table>

**Atualizações de compatibilidade**

* A versão de 32 bits do console do cliente agora está obsoleta. A partir da versão 8.6, o Console do cliente só estará disponível em 64 bits. A atualização para a versão de 64 bits do console do cliente é perfeita. Para obter mais informações sobre como atualizar seu sistema operacional, consulte esta [nota técnica](https://experienceleague.adobe.com/docs/campaign/technotes-ac/tn-new/console.html?lang=pt-BR).
* Agora você pode conectar a instância do Campaign v8 ao banco de dados externo do Azure synapse. Essa conexão é gerenciada por meio de uma nova conta externa.

**Aprimoramentos**

* A taxa de transferência do SMS foi significativamente aprimorada com a implementação de uma variedade de otimizações, resultando em maior velocidade e eficiência para a comunicação por SMS.
* A partir do Campaign v8.5.1, o processo de autenticação para o Campaign v8 foi aprimorado. Os operadores técnicos devem usar o Adobe Identity Management System (IMS) para se conectarem ao Campaign.
* Agora você pode aproveitar as conexões de Destino e Origem para sincronizar atributos de perfil, como dados de recusa entre o Adobe Experience Platform e o banco de dados do Campaign v8
* A preparação da entrega foi otimizada.
* Uma nova opção de autenticação baseada em chave foi adicionada para a conta externa SFTP, juntamente com o método de autenticação de usuário/senha existente. Agora os usuários podem se autenticar com segurança usando uma chave privada, melhorando a segurança e fornecendo um mecanismo de autenticação alternativo para o acesso SFTP.

**Melhorias de segurança**

* Não é mais possível criar operadores no Console do cliente. Agora você precisa usar o Admin Console. [Saiba mais](../start/gs-permissions.md).
* Várias ferramentas de terceiros foram atualizadas para otimizar a segurança.

**Correções**

* Correção de um problema que poderia resultar na codificação incorreta de caracteres especiais no conteúdo HTML de uma entrega em vários navegadores. (NEO-60081)
* Correção de um problema que impedia salvar um relatório em uma implantação corporativa (FFDA) do Campaign v8. (NEO-56836)
* Correção de um problema ao inserir ou atualizar dados em um esquema FFDA personalizado por meio de uma atividade de fluxo de trabalho Atualizar dados. (NEO-54708)
* Correção de um problema que impedia que o workflow de limpeza do banco de dados removesse endereços na tabela nms:address no FFDA. (NEO-54460)
* Correção de um problema com o fluxo de trabalho de faturamento que poderia falhar com um erro &quot;Compilação de memória esgotada&quot;. (NEO-51137)
* Correção de um problema que impedia que a descriptografia GPG funcionasse corretamente na atividade de workflow Carregamento de dados (arquivo). (NEO-50257)
* Corrigido um problema que impedia o funcionamento da função `JSPContext.sqlExecWithOneParam`. (NEO-50066)
* Correção de um problema que resultava em falhas de delivery ao usar caracteres não imprimíveis em campos de personalização. (NEO-48588)
* Correção de um problema que poderia causar erros de entrega ao inserir imagens dinâmicas do Adobe Target. (NEO-62689)
* Correção de um problema para impedir que os navegadores adicionem espaços extras ao usar conteúdo condicional em uma entrega. (NEO-62132)
* Correção de um problema que fazia com que uma janela pop-up fosse aberta ao clicar em uma imagem no editor de conteúdo de email. (NEO-60752)
* Correção de um problema que poderia resultar em um erro e impedir a rolagem da tela ao editar o conteúdo de uma entrega. (NEO-61364)
