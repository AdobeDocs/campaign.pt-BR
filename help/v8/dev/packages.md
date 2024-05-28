---
title: Trabalho com pacotes de dados
description: Trabalho com pacotes de dados
feature: Data Management, Package Export/Import
role: Developer
level: Intermediate, Experienced
source-git-commit: 8b537c723335ea98eb39bfbc3a4f1df09861aaea
workflow-type: tm+mt
source-wordcount: '1963'
ht-degree: 51%

---

# Trabalhar com pacotes de dados{#data-packages}

## Introdução a pacotes {#gs-data-packages}

Você pode usar pacotes de dados para exportar e importar dados e configurações personalizadas da plataforma. Os pacotes podem conter diferentes tipos de configurações e componentes, filtrados ou não.

Em pacotes de dados do Campaign, as entidades do banco de dados do Adobe Campaign podem ser exibidas em arquivos XML. Em um pacote, cada entidade é representada com todos os seus dados.

O princípio da **pacotes de dados** é exportar uma configuração de dados e integrá-la a outro ambiente do Adobe Campaign. Saiba como manter um conjunto consistente de pacotes de dados nesta [seção](#data-package-best-practices).

### Tipos de pacotes {#types-of-packages}

Você pode trabalhar com três tipos de pacotes no Adobe Campaign: pacotes de usuário, pacotes de plataforma e pacotes de administrador.

* A **pacote do usuário** permite selecionar a lista de entidades a serem exportadas. Esse tipo de pacote gerencia dependências e verifica erros.
* A **pacote de plataforma** inclui todos os recursos técnicos adicionados (não padrão): schemas, código JavaScript, etc.
* Um **pacote de administração** inclui todos os templates e objetos comerciais adicionados (não padrão): templates, bibliotecas, etc.

>[!CAUTION]
>
>A variável **platform** e **administrador** os pacotes contêm uma lista predefinida de entidades a serem exportadas. Cada entidade está vinculada às condições de filtragem que permitem remover os recursos prontos para uso do pacote criado.

## Estrutura de dados {#data-structure}

A descrição de um pacote de dados é um documento XML estruturado que está de acordo com a gramática do **xrk:navtree** schema de dados, como no exemplo abaixo:

```xml
<package>
  <entities schema="nms:recipient">
    <recipient email="john.smith@adobe.com" lastName="Smith" firstName="John">      
      <folder _operation="none" name="nmsRootFolder"/>      
      <company _operation="none" name="Adobe"/>
    </recipient>
  </entities>
  <entities schema="sfa:company">
    <company name="Adobe">
      <location city="London" zipCode="W11 2BQ"/>
    </company>
  </entities>
</package>
```

O documento XML deve começar e terminar com o elemento `<package>`. Qualquer `<entities>` os elementos seguintes distribuem os dados por tipo de documento. Um `<entities>` contém os dados do pacote no formato do schema de dados inserido no **schema** atributo. Os dados em um pacote não devem conter chaves internas incompatíveis entre as bases, como chaves geradas automaticamente (opção **autopk**).

No nosso exemplo, as associações no `folder` e `company` Os links foram substituídos pelas teclas de &quot;alto nível&quot; nas tabelas de destino:

```xml
<recipient>
  <folder _operation="none" name="nmsRootFolder"/>
  <company _operation="none" name="Adobe"/>
</recipient>
```

A variável `operation` atributo com o valor `none` define um link de reconciliação.

Um pacote de dados pode ser criado manualmente a partir de qualquer editor de texto. Você deve garantir que a estrutura do documento XML esteja em conformidade com a `xtk:navtree` esquema de dados. O console do cliente tem um módulo de exportação e importação de pacote de dados.

## Exportar pacotes {#export-packages}

Os pacotes podem ser exportados de três formas diferentes:

* Use o **[!UICONTROL Package Export]** assistente para exportar um conjunto de objetos em um único pacote. [Saiba mais](#export-a-set-of-objects-in-a-package)
* Para exportar um **objeto único**, clique com o botão direito do mouse e selecione **[!UICONTROL Actions > Export in a package]**.
* Use o **Definições de pacote** para criar uma estrutura de pacote na qual você adiciona objetos a serem exportados posteriormente em um pacote. [Saiba mais](#manage-package-definitions)

Depois que um pacote é exportado, você pode importá-lo e todas as entidades adicionadas para outra instância do Campaign.

### Exportar um conjunto de dados em um pacote {#export-a-set-of-objects-in-a-package}

Para exportar um conjunto de objetos em um pacote de dados, siga estas etapas:

1. Navegue até o assistente de exportação de pacotes por meio da **[!UICONTROL Tools > Advanced > Export package...]** do explorador.
1. Selecione o [tipos de pacotes](#types-of-packages).

   ![](assets/package_type.png)

1. Clique em **Adicionar** para selecionar as entidades a serem exportadas como um pacote.

   >[!CAUTION]
   >
   >Se exportar um tipo de pasta **[!UICONTROL Offer category]**, **[!UICONTROL Offer environment]**, **[!UICONTROL Program]** ou **[!UICONTROL Plan]**, nunca selecione a **xtk:folder**, já que alguns dados podem ser perdidos. Selecione a entidade que corresponde à pasta: **nms:offerCategory** para categorias de ofertas, **nms:offerEnv** para ambientes de ofertas, **nms:program** para programas e **nms:plan** para planos.

   O mecanismo de dependência controla a sequência de exportação da entidade. Para obter mais informações, consulte [Gerenciamento de dependências](#managing-dependencies).

1. Clique em **[!UICONTROL Next]** e defina o query de filtro no tipo de documento a ser extraído. Você deve configurar a cláusula de filtragem para extração de dados.

   >[!NOTE]
   >
   >O editor de query é apresentado [nesta seção](../../platform/using/about-queries-in-campaign.md).

1. Clique em **[!UICONTROL Next]** e selecione a ordem de classificação dos dados exportados.

1. Visualize os dados a serem extraídos para verificar sua configuração.

1. A última página do assistente de exportação de pacotes permite iniciar a exportação. Os dados serão armazenados no arquivo indicado no campo **[!UICONTROL File]**.

### Gerenciar dependências {#manage-dependencies}

O processo de exportação rastreia os links entre os vários elementos exportados. Esse mecanismo é definido por duas regras:

* objetos vinculados a um link com um `own` ou `owncopy` são exportados no mesmo pacote que o objeto exportado.
* objetos vinculados a um link com um `neutral` ou `define` a integridade do tipo (link definido) deve ser exportada separadamente.

>[!NOTE]
>
>Os tipos de integridade vinculados a elementos do schema são definidos em [esta página](database-links.md).

#### Exportar uma campanha {#export-a-campaign}

Veja abaixo um exemplo de como exportar uma campanha. A campanha de marketing a ser exportada contém:
* a `MyTask`tarefa
* a `campaignWorkflow` fluxo de trabalho na seguinte pasta: **[!UICONTROL Administration > Production > Technical workflows > Campaign processes > MyWorkflow]**.

A tarefa e o workflow são exportados no mesmo pacote que a campanha desde que os schemas correspondentes sejam conectados por links com um `own` integridade do tipo.

O conteúdo do pacote é:

```xml
<?xml version='1.0'?>
<package author="Administrator (admin)" buildNumber="7974" buildVersion="7.1" img=""
label="" name="" namespace="" vendor="">
 <desc></desc>
 <version buildDate="2013-01-09 10:30:18.954Z"/>
 <entities schema="nms:operation">
  <operation duration="432000" end="2013-01-14" internalName="OP1" label="MyCampaign"
  modelName="opEmpty" start="2013-01-09">
   <controlGroup>
    <where filteringSchema=""/>
   </controlGroup>
   <seedList>
    <where filteringSchema="nms:seedMember"></where>
    <seedMember internalName="SDM1"></seedMember>
   </seedList>
   <parameter useAsset="1" useBudget="1" useControlGroup="1" useDeliveryOutline="1"
   useDocument="1" useFCPValidation="0" useSeedMember="1" useTask="1"
   useValidation="1" useWorkflow="1"></parameter>
   <fcpSeed>
    <where filteringSchema="nms:seedMember"></where>
   </fcpSeed>
   <owner _operation="none" name="admin" type="0"/>
   <program _operation="none" name="nmsOperations"/>
   <task end="2013-01-17 10:07:51.000Z" label="MyTask" name="TSK2" start="2013-01-16 10:07:51.000Z"
   status="1">
    <owner _operation="none" name="admin" type="0"/>
    <operation _operation="none" internalName="OP1"/>
    <folder _operation="none" name="nmsTask"/>
   </task>
   <workflow internalName="WKF12" label="CampaignWorkflow" modelName="newOpEmpty"
   order="8982" scenario-cs="Notification of the workflow supervisor (notifySupervisor)"
   schema="nms:recipient">
    <scenario internalName="notifySupervisor"/>
    <desc></desc>
    <folder _operation="none" name="Folder4"/>
    <operation _operation="none" internalName="OP1"/>
   </workflow>
  </operation>
 </entities>
</package>   
```

A afiliação a um tipo de pacote é definida em um schema com o `@pkgAdmin and @pkgPlatform` atributo. Esses atributos recebem uma expressão XTK que define as condições de afiliação ao pacote.

```xml
<element name="offerEnv" img="nms:offerEnv.png" 
template="xtk:folder" pkgAdmin="@id != 0">
```

Por último, a `@pkgStatus` atributo permite definir as regras de exportação para esses elementos ou atributos. Dependendo do valor do atributo, o elemento ou atributo será encontrado no pacote exportado. Os três valores possíveis para este atributo são:

* `never`: não exporta o campo/link
* `always`: força a exportação deste campo
* `preCreate`: autoriza a criação da entidade vinculada

>[!NOTE]
>
>A variável `preCreate` o valor só é admitido para eventos do tipo link. Ele permite criar ou apontar para uma entidade que ainda não foi carregada no pacote exportado.

## Gerenciar definições de pacote {#manage-package-definitions}

As definições de pacote permitem criar uma estrutura de pacote na qual você adiciona entidades que serão exportadas posteriormente em um único pacote. É possível importar esse pacote e todas as entidades adicionadas para outra instância do Campaign.

**Tópicos relacionados:**

* [Criar uma definição de pacote](#create-a-package-definition)
* [Adicionar entidades a uma definição de pacote](#add-entities-to-a-package-definition)
* [Configurar a geração de definições de pacote](#configure-package-definitions-generation)
* [Exportar pacotes de uma definição de pacote](#export-packages-from-a-package-definition)

### Criar uma definição de pacote {#create-a-package-definition}

As definições de pacote podem ser acessadas no menu **[!UICONTROL Administration > Configuration > Package management > Package definitions]**.

Para criar uma definição de pacote, clique em **[!UICONTROL New]** e preencha as informações gerais sobre a definição de pacote.

![](assets/packagedefinition_create.png)

Você pode então adicionar entidades à definição do pacote e exportá-lo para um pacote de arquivos XML.

**Tópicos relacionados:**

* [Adicionar entidades a uma definição de pacote](#add-entities-to-a-package-definition)
* [Configurar a geração de definições de pacote](#configure-package-definitions-generation)
* [Exportar pacotes de uma definição de pacote](#export-packages-from-a-package-definition)

### Adicionar entidades a uma definição de pacote {#add-entities-to-a-package-definition}

Na guia **[!UICONTROL Content]**, clique no botão **[!UICONTROL Add]** para selecionar as entidades que serão exportadas com o pacote. As práticas recomendadas ao selecionar entidades são apresentadas na [nesta seção](#export-a-set-of-objects-in-a-package).

![](assets/packagedefinition_addentities.png)

As entidades podem ser adicionadas a uma definição de pacote diretamente da sua localização na instância. Para fazer isso, siga as etapas abaixo:

1. Clique com o botão direito do mouse na entidade desejada e depois selecione **[!UICONTROL Actions > Export in a package]**.

1. Selecione **[!UICONTROL Add to a package definition]** e depois selecione a definição de pacote à qual deseja adicionar à entidade.

1. A entidade é adicionada à definição de pacote e será exportada com o pacote (consulte [esta seção](#export-packages-from-a-package-definition)).

### Configurar a geração de definições de pacote {#configure-package-definitions-generation}

A criação de pacote pode ser configurada na guia **[!UICONTROL Content]** de definição de pacote. Para fazer isso, clique em **[!UICONTROL Generation parameters]**.

![](assets/packagedefinition_generationparameters.png)

* Use o **[!UICONTROL Include the definition]** opção para incluir a definição usada atualmente na definição de pacote.
* Use o **[!UICONTROL Include an installation script]** opção para adicionar um script javascript a ser executado na importação de pacotes. Quando selecionada, uma guia **[!UICONTROL Script]** é adicionada na tela de definição de pacote.
* Use o **[!UICONTROL Include default values]** opção para adicionar os valores de todos os atributos da entidade ao pacote.

  Essa opção não está selecionada por padrão para evitar exportações longas. Isso significa que, por padrão, os atributos das entidades com valores padrão (&#39;string vazia&#39;, &#39;0&#39; e &#39;falso&#39; se não definido de outra forma no schema) não são adicionados ao pacote e, portanto, não são exportados.

  >[!CAUTION]
  >
  >Se a instância onde o pacote for importado contiver entidades idênticas ao próprio pacote (por exemplo, com a mesma ID externa), então seus atributos não serão atualizados. Isso pode ocorrer se os atributos da instância anterior tiverem valores padrão, pois não estão incluídos no pacote. Nesse caso, selecionar a opção **[!UICONTROL Include default values]** impediria mesclar as versões, pois todos os atributos da instância anterior seriam exportados com o pacote.

### Exportar pacotes de uma definição de pacote {#export-packages-from-a-package-definition}

Siga as etapas abaixo para exportar um pacote de uma definição de pacote:

1. Selecione a definição de pacote a ser exportada, clique em **[!UICONTROL Actions]** e selecione **[!UICONTROL Export the package]**.
1. Verifique o nome e o local do arquivo exportado.
1. Clique em **[!UICONTROL Start]** botão para iniciar a exportação.

## Importar pacotes {#import-packages}

O assistente de importação de pacotes pode ser acessado pelo menu principal **[!UICONTROL Tools > Advanced > Import package]** do console do cliente.

### Instalar um pacote de um arquivo {#install-a-package-from-a-file}

Para importar um pacote de dados existente, siga estas etapas:

1. Acesse o assistente de importação pelo menu principal **[!UICONTROL Tools > Advanced > Import package]** do console do cliente.
1. Selecione o arquivo XML e clique em **[!UICONTROL Open]**.

O conteúdo do pacote a ser importado é exibido na seção intermediária do editor.

Clique em **[!UICONTROL Next]** e em **[!UICONTROL Start]** para iniciar a importação.

### Instalar um pacote integrado {#install-a-standard-package}

Pacotes incorporados (também conhecido como pacotes padrão) são instalados quando o Adobe Campaign é configurado. Dependendo das suas permissões, do modelo de implantação e da oferta de produto, você pode importar novos pacotes padrão.

Consulte o contrato de licença para verificar quais pacotes você pode instalar.

## Práticas recomendadas para o pacote de dados {#data-package-best-practices}

Esta seção descreve como organizar pacotes de dados de forma consistente durante a vida útil do projeto.


### Versões

Você sempre deve importar dentro da mesma versão da plataforma. Você deve verificar se implantou seus pacotes entre duas instâncias que têm a mesma build. Nunca force a importação e sempre atualize a plataforma primeiro (se a build for diferente).

>[!IMPORTANT]
>
>A Adobe não oferece suporte à importação entre diferentes versões.

Preste atenção ao schema e à estrutura do banco de dados. A importação de um pacote com schema deve ser seguida pela geração do schema.

### Tipos de pacotes {#package-types}

Comece definindo diferentes tipos de pacotes. Somente quatro tipos são usados:

**Entidades**

* Todos os elementos específicos &quot;xtk&quot; e &quot;nms&quot; no Adobe Campaign como schemas, formulários, pastas, templates do delivery etc.
* Você pode considerar uma entidade como um elemento &quot;admin&quot; e &quot;platform&quot;.
* Não se deve incluir mais de uma entidade ao fazer upload de um pacote em uma instância do Campaign.

Se precisar implantar sua configuração em uma nova instância, você poderá importar todos os pacotes de entidade.

**Recursos**

Este tipo de pacote:
* Responde a um requisito/especificação do cliente.
* Contém uma ou várias funcionalidades.
* Deve conter todas as dependências para poder executar a funcionalidade sem qualquer outro pacote.

**Campanhas**

Este pacote não é obrigatório. Às vezes, é útil criar um tipo específico para todas as campanhas, mesmo se uma campanha puder ser vista como um recurso.

**Atualizações**

Depois de configurado, um recurso pode ser exportado para outro ambiente. Por exemplo, o pacote pode ser exportado de um ambiente dev para um ambiente de teste. Neste teste, um defeito é revelado. Primeiro, ele precisa ser corrigido no ambiente dev. Em seguida, o patch deve ser aplicado na plataforma de teste.

A primeira solução seria exportar todo o recurso novamente. Mas, para evitar qualquer risco (atualizar elementos indesejados), é mais seguro dispor de um pacote que contenha apenas a correção.

É por isso que recomendamos criar um pacote de &quot;atualização&quot;, contendo apenas um tipo de entidade do recurso.

Uma atualização não pode ser apenas uma correção, mas também um novo elemento do seu pacote de entidade/recurso/campanha. Para evitar a implantação de todo o pacote, é possível exportar um pacote de atualização.

### Nomeação de convenções {#data-package-naming}

Agora que os tipos estão definidos, devemos especificar uma convenção de nomenclatura. O Adobe Campaign não permite criar subpastas para especificações de pacotes, o que significa que os números são a melhor solução para se manter organizado. Os números prefixam os nomes dos pacotes.

Por exemplo, você pode usar a seguinte convenção:

* Entidade: de 1 a 99
* Recurso: de 100 a 199
* Campanha: de 200 a 299
* Atualização: de 5000 a 5999

#### Ordem dos pacotes de entidade {#entity-packages-order}

Para ajudar na importação, os pacotes de entidade devem ser ordenados, pois devem ser importados.

Por exemplo:

* 001 - Schema
* 002 - Formulário
* 003 - Imagens
* etc.

>[!NOTE]
>
>O Forms deve ser importado somente **após** atualizações de esquema.


#### Documentação do pacote {#package-documentation}

Ao atualizar um pacote, você deve sempre colocar um comentário no campo de descrição para detalhar quaisquer modificações e motivos (por exemplo, &quot;adicionar um novo schema&quot; ou &quot;corrigir um defeito&quot;).

A prática recomendada também é inserir a data da atualização.

>[!IMPORTANT]
>
>O campo de descrição só pode conter até 2.000 caracteres.

