---
product: campaign
title: Carregamento (SOAP)
description: Carregamento (SOAP)
feature: Workflows
role: User
version: Campaign v8, Campaign Classic v7
exl-id: 21c42a36-9a50-49b8-8a07-b041ba8b2026
TQID: 'https://experienceleague.adobe.com/CBO5ddwOwsFclqdXq-ahz6ZMg0fXVc4L8vIruKz17j4'
product_v2:
  - id: dfc56824-e8b9-499e-85d4-21aedb507314
    internal-label: Campaign
  - id: d0e9f0b2-1f2b-4134-9844-49cd4e950f27
    internal-label: Campaign v8
feature_v2:
  - id: a658c786-869b-4194-a780-2594d663adda
    internal-label: Data management
subfeature_v2:
  - id: fcb46c0f-76e1-48bc-9dd0-fcf9d97526cf
    internal-label: Workflows
role_v2:
  - id: b69b2659-1057-424e-8fc5-ed9e016dc554
    internal-label: User
source-git-commit: e13b3537d149f2bdad7e9dd66768837e5c4b595b
workflow-type: tm+mt
source-wordcount: '281'
ht-degree: 81%
---
# Carregamento (SOAP){#loading-soap}



>[!CAUTION]
>
>A atividade de **Carregamento (SOAP)** só estará disponível se você tiver o módulo **FDA (Federated Data Access)** instalado. Verifique o contrato de licença.

A atividade de **Carregamento (SOAP)** é usada além da atividade de **carregamento de dados (RDBMS)** quando não é possível coletar dados diretamente pelo FDA em um banco de dados externo.

A operação é como descrita a seguir:

1. Escolha usar um exemplo XML ou WSDL.

   O exemplo a seguir é de um fluxo de trabalho técnico do módulo do Centro de Mensagens.

   ![Atividade de carregamento (SOAP) com Use um exemplo XML selecionado, um exemplo de resultado e o script de Inicialização.](assets/load_soap_002.png)

1. Para um exemplo XML, selecione um arquivo de exemplo. O arquivo é analisado para estabelecer um exemplo de resultado.

   Para um WSDL, insira a URL de acesso correspondente, e então gere o código estrutural. O serviço e a chamada selecionados são atualizados e exibidos automaticamente.

   ![Formato do resultado com Usar um WSDL selecionado, um campo URL de Acesso e o link Gerar o código estrutural.](assets/soap_load_003.png)

1. Selecione **[!UICONTROL Click here to view and edit analysis results]** para especificar cada coluna identificada.

   ![Janela de formato de arquivo listando colunas identificadas, com o rótulo, o tipo de dados e o nome interno da coluna selecionada.](assets/soap_load_001.png)

   Se desejar atualizar o exemplo, selecione **[!UICONTROL Re-analyze the example]**.

1. Você pode usar o número de linha como um identificador e/ou especificar que a chamada SOAP retorna vários elementos.
1. Insira os seguintes scripts de guia de acordo com sua função:

   * **[!UICONTROL Initialization]**: estabelece uma conexão SOAP.
   * **[!UICONTROL Iteration]**: executa a chamada para o serviço SOAP. O retorno dessa função deve ser um objeto XML compatível com a descrição do exemplo ou do WSDL.

     O código dessa guia será chamado em um loop pelo Adobe Campaign até que um objeto XML nulo seja retornado.

   * **[!UICONTROL Finalization]**: fecha a conexão e/ou libera outros recursos criados durante o processamento.
