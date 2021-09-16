---
title: Gerenciamento de chaves no Campaign
description: Introdução ao gerenciamento de chaves
exl-id: ef06cb6b-1b25-4dbe-8fd0-f880ec9d645b
source-git-commit: f071fc227dac6d72873744ba56eb0b4b676de5dd
workflow-type: tm+mt
source-wordcount: '676'
ht-degree: 2%

---

# Gerenciamento de chaves e unicidade {#key-management}

No Campaign v8, a chave primária é um UUID (Universally Unique IDentifier), que é uma sequência de caracteres. Para criar esse UUID, o elemento principal do schema deve conter os atributos **autouuid** e **autopk** definidos como **true**.

O Adobe campaign v8 vem com o Snowflake como o banco de dados principal. A arquitetura distribuída do banco de dados do Snowflake não fornece mecanismos para gerenciar a unicidade de uma chave em uma tabela: os usuários finais são responsáveis por garantir a consistência das chaves no banco de dados do Adobe Campaign.

Evitar duplicatas em chaves e, especialmente, em chaves primárias, é obrigatório para preservar a consistência do banco de dados relacional. As duplicatas em chaves primárias levam a problemas com atividades de workflow do gerenciamento de dados, como **Query**, **Reconciliation**, **Update data** e muito mais.

Como prática recomendada, o Adobe recomenda a adoção de uma estratégia [Detect](#detect-duplicates) e [Correct](#correct-duplicates) como parte do processo geral de Gerenciamento de dados, caso chaves duplicadas tenham sido carregadas no banco de dados.

## Detectar duplicatas{#detect-duplicates}

O Campaign vem com uma nova garantia que remove automaticamente qualquer UUID duplicada de um público-alvo durante a preparação do delivery. Esse novo mecanismo impede que qualquer erro ocorra ao preparar um delivery.

>[!CAUTION]
>
>Chaves duplicadas não são restritas a UUIDs. Isso pode ocorrer no com IDs, incluindo chaves personalizadas criadas em tabelas personalizadas.

Como usuário final, você pode verificar essas informações nos logs do delivery: alguns recipients podem ser excluídos do target principal devido à chave duplicada. Nesse caso, o seguinte aviso é exibido: `Exclusion of duplicates (based on the primary key or targeted records)`.

![](assets/delivery-log-duplicates.png)

Quando isso ocorre, é possível criar um workflow para identificar as chaves duplicadas. Você poderá corrigir essas chaves. Para fazer isso, siga as etapas abaixo:

1. Crie um novo workflow.

   ![](assets/new-wf.png)

1. Adicionar uma atividade **Query**
1. Selecione a tabela **Recipient**

   ![](assets/add-query-on-rcp.png)

1. Adicione uma atividade **Deduplication** e desduplique na chave primária (UUID). Mantenha apenas uma duplicata e marque a opção **Generate Complement** para criar uma transição de saída para a(s) duplicata(s).

   ![](assets/deduplicate.png)

1. Salve as duplicatas em uma lista usando uma atividade List update .

   ![](assets/list-update.png)

Agora, você pode acessar os recipients duplicados diretamente da lista. Mesmo que a transição contenha apenas uma das linhas duplicadas, todas as duplicatas serão registradas na lista.


## Correção de duplicatas{#correct-duplicates}

A correção das duplicatas requer que os clientes atualizem os dados do Campaign. O tipo de ação está estreitamente vinculado à natureza das duplicatas e da implementação. Podemos enfrentar vários casos que devem exigir uma estratégia de mitigação diferente (remover, mesclar ou atualizar).

>[!IMPORTANT]
>
>As chaves primárias duplicadas impedem que você use atividades de workflow integradas para selecionar ou atualizar uma linha específica. Devido à duplicação de UUID, a desduplicação de dados falhará e poderá afetar a integridade do banco de dados. Como consequência, é altamente recomendável corrigir duplicatas.

Por exemplo:

* **Caso 1**  - Recipientes duplicados com a mesma UUID e as mesmas informações de perfil (mesmo email, nome etc.) : os recipients parecem duplicatas &quot;reais&quot; e a atenuação pode ser apenas remover uma das duplicatas.
Outra abordagem poderia ser mesclar informações de um recipient no outro.

* **Caso 2**  - Recipientes duplicados com o mesmo UUID, mas informações de perfil diferentes (email diferente, nome etc.):
desta vez, parece que há perfis diferentes e você pode manter ambos no banco de dados do Campaign, o que significa que podemos preferir apenas atualizar uma das duplicatas que geram um novo UUID. [Saiba mais neste exemplo](#deduplicate-sample).

Dependendo de sua estratégia de mitigação, sempre é possível consultar a lista de outro workflow e aplicar a atualização de acordo com sua necessidade. Para obter mais orientações, entre em contato com o Adobe.

### Amostra de desduplicação{#deduplicate-sample}

No caso de recipients duplicados, você pode manter ambos os registros no banco de dados do Campaign. Nesse caso, você precisa atualizar um deles com um novo UUID.

Para executar uma consulta de atualização SQL no banco de dados da nuvem, você pode usar a atividade de workflow **SQL Data Management** e executar a seguinte atualização SQL:

```sql
update nmsrecipient set urecipientid = uuid_string()
where semail = 'bretta37@adobe.com'
and urecipientid = 'c04d93f2-6012-4668-b523-88db1262cd46';
```

![](assets/sql-data-management.png)

Depois que a linha selecionada é atualizada com um novo UUID, você pode verificar a linha atualizada da interface e observar que o UUID foi atualizado conforme esperado. Você também pode detectar duplicatas no Banco de Dados executando o workflow **Detectar duplicatas** [conforme explicado aqui](#detect-duplicates).
