---
title: Validação de uma conexão SMPP
description: Saiba como validar uma conexão SMPP
feature: SMS
role: User
level: Intermediate
exl-id: eda6934a-e48a-4932-8c88-588f661005d6
source-git-commit: 6f29a7f157c167cae6d304f5d972e2e958a56ec8
workflow-type: tm+mt
source-wordcount: '4437'
ht-degree: 16%

---

# Validação de uma conexão SMPP {#validate-smpp-connection}

Estas são algumas verificações para verificar se a conexão SMPP está OK.

## Itens a serem verificados antes de entrar em funcionamento {#check-go-live}

Antes de entrar em funcionamento, verifique se a configuração do SMPP está correta com a lista de verificações abaixo.

>[!IMPORTANT]
>
>Esta lista de verificação não é exaustiva. Quanto mais cheques você fizer, melhor.

>[!NOTE]
>
>Ative rastreamentos SMPP detalhados durante verificações. Isso ajudará você e a equipe de suporte a entender os problemas.

### Verifique se há conflitos de conta externa {#sms-external-accounts-check}

Verifique se você não tem mais contas externas SMS. Exclua as contas de teste para eliminar possíveis conflitos.

Verifique se nenhuma outra instância se conecta à conta externa. Em particular, verifique se o ambiente de pré-produção não se conecta à conta externa de produção.

Se você precisar ter várias contas na mesma instância do Campaign que se conectam ao mesmo provedor, entre em contato com o provedor para garantir que realmente diferenciam as conexões entre essas contas. Ter várias contas com o mesmo login requer configuração extra.

Verifique se todas as contas externas de SMS habilitadas têm a configuração de processo dedicado habilitada. Não é possível mesclar os dois tipos de contas (com e sem processo dedicado) na mesma instância.

### Fazer um teste real {#real-test}

Tente enviar alguns SMS em diferentes celulares.

**Enviar SMS com todos os tipos de caracteres**

Se você precisar enviar SMS com caracteres não GSM ou não ASCII, tente enviar algumas mensagens com os caracteres mais diversos possível. Se você configurar uma tabela de mapeamento de caracteres personalizada, envie pelo menos um SMS para todos os valores data_coding possíveis.

**Verifique se o SR está corretamente processado**

O SMS deve ser marcado como recebido no log de delivery. O log de entrega deve ser bem-sucedido e ter esta aparência: &quot;*SR seuProvedor stat=DELIVRD err=000|#MESSAGE#*&quot;.

Verifique se você definiu corretamente o campo &quot;*Nome da implementação SMSC*&quot;: o log de entrega nunca deve conter &quot;*SR Genérico*&quot; em ambientes de produção.

**Verifique se o MO foi processado**

Envie alguns SMS para todas as palavras-chave de resposta automática e verifique se a resposta é rápida (não mais do que alguns segundos).

Verifique se os MOs estão inseridos no banco de dados *nms:inSms*. Se você tiver TLVs personalizados, verifique se eles também estão inseridos corretamente e formatados adequadamente.

Verifique no log se o Campaign responde com um *DELIVER_SM_RESP (command_status=0)* bem-sucedido.

**Fazer um teste de carga**

Isso é especialmente importante se você enviar muitas mensagens ou se usar mensagens em tempo real.

Faça um teste que carregue a conexão a 100% por pelo menos 5 segundos. Você terá que enviar mensagens reais se o provedor não tiver uma maneira de se conectar a uma conta falsa para testes. Uma maneira de fazer isso é monitorar de perto o primeiro delivery grande o suficiente com mensagens SMPP detalhadas ativadas.

O número mínimo de mensagens a enviar pode ser calculado assim:

*Taxa de transferência máxima de MT * Número total de conexões de transmissor/transceptor * 5*

Após a conclusão do delivery, verifique o seguinte:

* Verificar se todas as mensagens foram enviadas (não necessariamente recebidas)
* Deve haver absolutamente zero PDU com command_status não 0x00000000, a menos que isso seja explicitamente declarado pelo provedor como operação normal
* As conexões devem permanecer absolutamente estáveis (sem PDU BIND) durante todo o processo de entrega.
* Verifique se todas as mensagens têm um SR e se ele foi processado corretamente (consulte [Verificar se o SR foi processado corretamente](#real-test)). Se uma pequena porcentagem tiver erros, verifique se eram erros reais de retorno do SR, não erros durante o envio ou o processamento no lado da campanha.
* Se não tiver certeza sobre o desempenho, verifique se a latência é razoável, especialmente entre uma PDU e seu RESP correspondente. Ter mais de 500 ms de latência pode ser um problema para alta taxa de transferência. Use essa latência para verificar a fórmula da janela de envio (consulte a configuração da janela de envio para obter mais detalhes)

### Verificar as PDUs {#pdu}

Verifique se as PDUs estão formatadas corretamente.

>[!IMPORTANT]
>
>Essa etapa é altamente recomendada ao conectar-se a um provedor que antes não estava conectado ao Campaign.

**ASSOCIAR**

Verifique se as PDUs BIND_* foram enviadas corretamente. O item mais importante a ser verificado é se o provedor sempre retorna PDUs BIND_RESP bem-sucedidas (command_status = 0).

Verifique se não há muitas PDUs BIND_*. Se houver muitos deles, isso poderá indicar que a conexão é instável. Consulte a seção de solução de problemas de conexões instáveis abaixo para obter mais informações sobre isso.

**LINK_DE_CONSULTA**

Verifique se as PDUs INQUIRE_LINK são trocadas regularmente quando a conexão está ociosa.

**SUBMIT_SM / DELIVER_SM**

Envie uma mensagem e, em seguida, pesquise nos registros os respectivos PDUs SUBMIT_SM, SUBMIT_SM_RESP, DELIVER_SM e DELIVER_SM_RESP.

Com a *PDU SUBMIT_SM*:

* Verifique se data_coding está correto (0 por padrão).
* Verifique se short_message está corretamente codificado: tente decodificá-lo usando um conversor hexadecimal que suporte várias codificações (há algumas disponíveis online).
* Se você usar message_payload para mensagens longas, verifique se o conteúdo está presente no campo opcional e não no campo short_message.

Com a *PDU SUBMIT_SM_RESP*:

* Verifique se ele foi bem-sucedido (command_status = 0).
* Verifique se o corpo contém uma ID formatada corretamente seguida de um byte &quot;0&quot;.

Com a *PDU DELIVER_SM*:

* Decodifique o campo hexadecimal short_message (há ferramentas online para isso).
* Verifique com uma ferramenta de verificação de regex se o regex definido no regex de Extração da ID no SR retorna exatamente um grupo de captura e se ele captura a ID inteira na mensagem.
* Verifique se a ID extraída corresponde à ID em SUBMIT_SM_RESP.
* Verifique se o regex definido no regex de Extração do status no SR retorna o conteúdo do campo stat.
* Verifique se o regex definido no regex de Extração do erro no SR retorna o conteúdo do campo err.

Com a *PDU DELIVER_SM_RESP*:

* Verifique se ele foi enviado rapidamente depois de receber o PDU DELIVER_SM (normalmente menos de um segundo).
* Verifique se ele foi bem-sucedido (command_status = 0).

### Teste em tempo real com o provedor {#sms-live-test}

Uma prática recomendada antes de entrar em funcionamento é fazer um teste ao vivo com o provedor, com ambos os lados observando os logs durante a execução.

>[!IMPORTANT]
>
>Essa etapa é altamente recomendada ao conectar-se a um provedor que nunca foi conectado ao Campaign antes.

### Desabilitar rastreamentos de SMPP detalhados {#sms-disable-smpp}

Quando todas as verificações forem concluídas, a última ação a ser executada será desativar os rastreamentos SMPP detalhados para que eles não gerem muitos logs.

## Solução de problemas de SMS {#sms-troubleshooting}

### Procedimento geral de solução de problemas {#sms-general-troubleshooting}

O conector SMS envolve 3 entidades: o provedor SMPP, o Adobe e você.
O principal especialista em SMS é o provedor SMPP, portanto, ele deve ser envolvido em todos os problemas relacionados ao tráfego de SMS (problemas de conexão, mensagens perdidas, problemas de codificação, regras específicas de país etc.).

#### Habilitar processo dedicado {#sms-dedicated-process}

>[!IMPORTANT]
>
>Verifique se **[!UICONTROL Send messages through a dedicated process]** está habilitado em todas as contas SMS ativas.

Se tiver problemas com o conector mais antigo (baseado em MTA) (processo dedicado desativado), considere migrar para o conector do processo dedicado. Ele tem um desempenho muito melhor, é mais estável e fornece um feedback muito melhor em seus logs.

#### Conflito entre contas externas diferentes {#sms-conflict-external-accounts}

Se a instância tiver várias contas externas de SMS, verifique se os problemas não são causados por um conflito entre contas.

Para isolar a conta externa que está causando problemas:

1. Desativar todas as contas externas
1. Ativar uma conta externa
1. Tente reproduzir o problema
1. Se o problema não ocorrer com essa única conta, desative-a e reinicie na etapa 2 na próxima conta. Depois de verificar cada conta individualmente, há dois cenários possíveis:

**O problema ocorreu em uma ou em várias contas**

Nesse caso, você pode aplicar outros procedimentos de solução de problemas a cada conta individualmente. É melhor desativar outras contas ao diagnosticar uma conta, para reduzir o tráfego de rede e a quantidade de logs.

**O problema não ocorreu quando apenas uma conta estava ativa a qualquer momento**

Você tem um conflito entre contas. O Adobe Campaign trata as contas individualmente, mas o provedor pode tratá-las como uma única conta.

*Você está usando diferentes combinações de logon/senha entre todas as suas contas*
Você terá que entrar em contato com o provedor para diagnosticar possíveis conflitos referentes a ele.

*Algumas contas externas compartilham a mesma combinação de logon/senha*
O provedor não tem como saber de qual conta externa a PDU BIND está vindo. Portanto, ele trata todas as conexões de várias contas como uma única, de modo que provavelmente roteia MO e SR aleatoriamente pelas duas contas, causando problemas aparentemente aleatórios.

Se o provedor der suporte a vários códigos curtos para a mesma combinação de logon/senha, você terá que perguntar a ele onde colocar esse código curto na PDU BIND. Observe que essa parte das informações deve ser colocada na PDU BIND e não em SUBMIT_SM, pois a PDU BIND é o único local que permitirá o roteamento correto de MOs.

Consulte a seção [Informações em cada tipo de PDU](#pdu) acima para saber quais campos estão disponíveis na PDU BIND. Geralmente, você colocaria o código curto em *address_range*, mas isso requer suporte especial do provedor. Entre em contato com ele para saber como espera rotear vários códigos curtos independentemente.

O Adobe Campaign oferece suporte ao manuseio de vários códigos curtos na mesma conta externa, portanto, muitas vezes, o uso de uma única conta para todo o tráfego funcionará bem.

#### Uma conta externa parou de funcionar {#sms-external-account-not-working}

Em geral, as conexões SMPP tendem a ser muito estáveis ao longo do tempo e, uma vez configuradas corretamente, elas devem continuar funcionando.

* Verifique se o conector foi alterado recentemente - e por quem (verifique as Contas externas como um grupo).
* Verifique se o sistema foi atualizado e quando.
* Verifique se algum pacote que afeta o SMS pode ter sido atualizado recentemente.

Se nenhuma dessas verificações causar uma causa raiz, entre em contato com o provedor. Às vezes, quando provedores atualizam suas plataformas, seu conector se comporta de forma um pouco diferente. Isso pode quebrar as configurações ajustadas e introduzir regressões.

É recomendável manter contato com o provedor. Muitas vezes, eles comunicam as principais alterações antecipadamente.

#### Problema de mid-sourcing (hospedado)  {#sms-issue-hosted}

* Se o problema ocorrer em um ambiente mid-sourcing, verifique se o delivery e os broadlogs foram criados e atualizados corretamente no servidor mid-sourcing. Se não for o caso, o problema não será um problema de SMS.
* Certifique-se de que o nome do operador mid esteja estritamente em letras minúsculas, caso contrário o delivery permanecerá no status pending.
* Se tudo funcionar no servidor intermediário e o SMS for enviado corretamente, mas a instância de marketing não for atualizada corretamente, ocorrerá um problema de sincronização intermediária.

#### Problema ao conectar-se ao provedor {#sms-issue-connection}

* Se a PDU BIND retornar um código *command_status* diferente de zero (o que significa que há um erro), ou se não houver uma PDU BIND_RESP, pergunte ao provedor por que isso acontece.
* Verifique se a rede está configurada corretamente para que a conexão TCP possa ser estabelecida com o provedor.
* Peça ao provedor que verifique se ele permitiu corretamente os endereços IP da instância do Adobe Campaign (a maioria dos provedores exige isso).
* Verifique as configurações da conta externa. Pergunte ao provedor em caso de dúvida sobre o valor de alguns campos.
* Se a conexão for bem-sucedida, mas instável, verifique os [Problemas com conexões instáveis](#unstable-connections). abaixo.
* Se problemas de conexão forem difíceis de diagnosticar, uma captura de rede fornecerá muitas informações. Certifique-se de que a captura de rede seja executada simultaneamente enquanto o problema aparece para que ele possa ser analisado com eficiência. Você também deve observar a hora exata em que o problema ocorre, para que seja mais fácil encontrá-lo nas capturas de rede.

#### Problemas com conexões instáveis {#unstable-connections}

**Como diagnosticar conexões instáveis:**

Uma conexão é considerada instável se qualquer uma dessas coisas acontecer:

* A conexão dura menos de uma hora.
* Reiniciar o processo SMS &quot;corrigirá&quot; os problemas temporariamente. Provavelmente, significa que uma conexão instável aciona a limitação. Reiniciar o processo de SMS limpa a limitação e, em seguida, ocorre novamente até que a causa raiz seja encontrada.
* O provedor envia PDUs UNBIND. O provedor nunca deve enviar PDUs UNBIND em operação normal.
* *enquire_link* expira, no lado do Campaign ou no lado do provedor. Nesse caso, você pode ou não ver INQUIRE_LINK_RESP com um código de erro diferente de zero.
* Há muitas PDUs BIND. Não deve haver mais do que alguns durante um dia (depende do número de conexões). Mais de 1 BIND PDU por hora e por conexão deve gerar um alerta.

**Como corrigir problemas de estabilidade de conexão:**

* Conexões instáveis raramente são a causa principal. Muitas vezes, é o resultado de outro problema que aciona uma desconexão de uma maneira ou outra. Encontrar a causa raiz é a prioridade.
* Ative rastreamentos SMPP detalhados. Você precisará deles para ver o que está acontecendo quando a conexão for reiniciada.
* Se o provedor enviar PDUs UNBIND, provavelmente fará algo errado. Pergunte a eles por que enviam UNBIND e isso provavelmente levará à causa raiz.
* Fazer uma captura de rede às vezes é a única maneira de ver como a conexão é fechada.
* Se o provedor fechar as conexões (enviando um pacote TCP FIN ou TCP RST), pergunte a ele por que fazer isso. Isso deve indicar a causa raiz do problema.
* Se o provedor fechar a conexão depois de enviar um erro limpo (como DELIVER_SM_RESP com um código de erro), ele deverá corrigir o conector, pois isso impedirá que outros tipos de mensagens sejam transmitidas e acionará a limitação do MTA. Isso é especialmente importante no modo transceptor, em que o fechamento da conexão afeta tanto o MT quanto o SR.
* Se houver tempos limite (tempos limite de BIND, tempos limite SUBMIT_SM), o Campaign pode estar enviando mensagens muito rapidamente para esse provedor. Tente reduzir a configuração de *taxa de transferência máxima do MT* e veja se isso resolve o problema.

#### Problema ao enviar um MT (SMS normal enviado para um usuário final)

* Verifique se a conexão está estável: uma conexão SMPP deve permanecer ativa por pelo menos 1 hora continuamente. Consulte a seção &quot;Problema com conexões instáveis&quot; acima.
* Se o reinício do processo SMS fizer com que o envio do MT funcione novamente por um pequeno período, provavelmente você terá uma limitação devido a uma conexão instável. Consulte a seção &quot;Problema com conexões instáveis&quot; acima.
* Verifique se o log amplo está presente e com o status e as datas corretas. Caso contrário, não é um problema de SMS, mas um problema de delivery ou de preparação de delivery (que está fora do escopo deste documento).
* Verifique se o conector de SMS está associado ao equipamento do provedor. Solicite feedback ao provedor para garantir que todos os sistemas estejam se comunicando corretamente. Consulte PDUs BIND_TRANSMITTER e BIND_TRANSCEIVER para obter informações sobre o processo de associação. Talvez seja necessário ativar os rastreamentos SMPP para solucionar problemas corretamente.
* Com os rastreamentos SMPP ativados, verifique se a PDU SUBMIT_SM está contendo as informações certas (consulte a documentação acima).
* Verifique se o provedor responde com uma PDU SUBMIT_SM_RESP com um valor &quot;OK&quot; (código 0). Verifique se a PDU chega com um atraso razoável: qualquer tempo superior a 1 segundo é suspeito e deve ser discutido com o provedor. Geralmente, chega em menos de 100 ms.
* Se todas essas etapas funcionarem, você poderá ter certeza de que o problema se refere ao provedor. Ele terá que solucionar problemas em sua plataforma.
* Se isso funcionar, mas o tráfego for inconsistente, tente ajustar a janela de envio e diminuir o rendimento do MT. Você precisará trabalhar com o provedor para ajustar isso. O Campaign pode enviar mensagens muito rapidamente. Portanto, problemas de desempenho podem surgir no equipamento do provedor.

#### Os MTs são duplicados (o mesmo SMS é enviado várias vezes seguidas)

Duplicatas frequentemente são causadas por tentativas. É normal haver duplicatas ao tentar enviar mensagens novamente. Portanto, concentre seus esforços na eliminação da causa raiz das tentativas.

* Se duplicatas forem enviadas com um intervalo de exatamente 60 segundos (ou qualquer outro período &quot;regular&quot; suspeito), provavelmente será um problema referente ao provedor, que não envia um SUBMIT_SM_RESP rápido o suficiente.
* Se você vir muitos BIND/UNBIND, você tem uma conexão instável: consulte a seção [Problemas com conexões instáveis](#unstable-connections) para obter soluções antes de tentar resolver problemas de mensagens duplicadas.
* Verifique se todos os PDUs SUBMIT_SM têm SUBMIT_SM_RESP correspondente logo após. Se eles não funcionarem ou SUBMIT_SM_RESP for muito lento, o problema se refere ao provedor.

Redução da quantidade de duplicatas quando há uma nova tentativa:

* Diminua a *janela de envio*. A janela de envio deve ser grande o suficiente para abranger a latência SUBMIT_SM_RESP, mas não muito grande. Seu valor representa o número máximo de mensagens que poderão ser duplicadas se ocorrer um erro enquanto a janela estiver cheia.

#### Problema ao processar SR (recibos de entrega)

* Você precisará de rastreamentos SMPP ativados para realizar qualquer tipo de solução de problemas de SR.
* Verifique se o PDU DELIVER_SM vem do provedor e se está corretamente formado.
* Verifique se o Campaign responde com uma PDU DELIVER_SM_RESP bem-sucedida em tempo hábil. Isso garante que o SR foi inserido na tabela providerMsgStatus para processamento diferido pelo processo de SMS.

Se o PDU DELIVER_SM não for confirmado com êxito, será necessário verificar algumas coisas:

* Verifique o regex relacionado à extração de id e ao processamento de erros na conta externa. Talvez seja necessário validá-los em relação ao conteúdo da PDU DELIVER_SM.
* Verifique se os erros foram devidamente provisionados na tabela broadLogMsg (a documentação do Campaign explica isso em detalhes).

Se o PDU DELIVER_SM tiver sido reconhecido pelo conector SMPP estendido do ACC, mas o broadLog não for atualizado corretamente, verifique o processo de reconciliação da ID descrito na seção MT, SR e entradas de banda larga correspondentes acima.

Se você corrigiu tudo, mas alguns SR inválidos ainda estão nos buffers do provedor, é possível ignorá-los usando a opção &quot;Contagem de confirmação de ID inválida&quot;. Isso deverá ser usado com cuidado e redefinido como 0 o mais rápido possível depois que os buffers estiverem limpos.

Se o processamento SR for lento, tente qualificar as mensagens de status mais comuns na tabela BroadLogMsg.

Se apenas alguns SRs forem recebidos, mas não todos, verifique se nenhum outro sistema se conecta à conta do provedor, como um sistema de teste. O SR pode ser roteado em qualquer conexão, portanto, alguns deles podem ser roteados para esse outro sistema. O provedor pode ajudar você a descobrir onde está esse outro sistema se conectando à conta.

#### Problema ao processar o MO (e quarentena/resposta automática)

* Ativar rastreamentos SMPP durante testes. Se você não ativar o TLS, é sempre melhor fazer uma captura de rede ao solucionar problemas do MO para verificar se as PDUs contêm as informações corretas e estão formatadas corretamente.
* Ao capturar tráfego de rede ou analisar rastreamentos SMPP, capture toda a conversa com o MO e seu MT de resposta (se uma resposta estiver configurada).
* Se o MO (DELIVER_SM PDU) não aparecer nos rastreamentos, você pode ter certeza de que o problema se refere ao provedor. Ele terá que solucionar problemas em sua plataforma.
* Se a PDU DELIVER_SM for exibida, verifique se ela é confirmada pelo Campaign com uma PDU DELIVER_SM_RESP bem-sucedida (código 0). Esse RESP garante que toda a lógica de processamento foi aplicada pelo Campaign (resposta automática e quarentena). Se esse não for o caso, procure uma mensagem de erro nos logs de processo do SMS.
* Se as respostas automáticas estiverem ativadas, verifique se SUBMIT_SM foi enviado ao provedor. Caso contrário, você encontrará uma mensagem de erro nos logs de processo de SMS.
* Se o SUBMIT_SM MT PDU que contém a resposta for encontrado nos rastreamentos, mas o SMS não chegar ao telefone celular, você terá que entrar em contato com o provedor para obter assistência na solução de problemas, pois o problema provavelmente está do lado dele.

#### Problema durante a preparação de entrega sem a exclusão de destinatário em quarentena (em quarentena pelo recurso de resposta automática)

* Verifique se o formato do número de telefone é exatamente o mesmo na tabela de quarentena e no log de entrega. Caso contrário, consulte a configuração &quot;Enviar número de telefone completo&quot; acima se tiver problemas com o prefixo &quot;+&quot; do formato de número de telefone internacional.
* Check short codes: Haverá exclusões se o código curto do recipient for igual ao definido na conta externa ou se estiver vazio (vazio = qualquer código curto). Se apenas um código curto for usado para toda a instância do Campaign, será mais fácil deixar todos os campos de &quot;código curto&quot; vazios.

#### Problemas de codificação  {#sms-encoding-issues}

Problemas de codificação são frequentes no SMS. Estas são algumas etapas básicas.

**Etapa 1: entrar em contato com o provedor**

O provedor é o especialista que sabe como o SMS funciona. Entre em contato com ele e veja o que há de errado. Ele deve ser capaz de dizer se o problema se refere a ele ou ao Campaign. Se o problema estiver no Campaign, ele deverá saber exatamente qual campo está incorreto, o que ajuda muito.

**Etapa 2: saiba o que está em sua mensagem**

Você terá que saber o que está em sua mensagem. Essa frase pode parecer fácil, mas não é. O Unicode permite tantas variantes para caracteres semelhantes que o Campaign não pode lidar com todas elas.

A origem de problemas mais comum é a cópia e colagem por meio de um processador de texto, que altera os caracteres comuns para versões tipograficamente corretas: espaços alterados para espaços não separáveis, aspas duplas alteradas para aspas de abertura e fechamento, sinais de menos alterados para vários tipos de hifens ...

Não copie e cole a mensagem ao testar. Sempre digite-a diretamente na interface.

**Não se intimide com o hexadecimal**. Hexadecimal parece estranho e não natural, mas tem uma qualidade muito distinta: você pode dizer a diferença entre caracteres semelhantes. Um L minúsculo, um I maiúsculo, O, 0, todos os diferentes tipos de aspas, codificações não latinas ou até mesmo tipos diferentes de espaços podem parecer iguais (ou não são exibidos). O hexadecimal mostra tudo e ajuda a comparar as coisas.

Para converter o unicode em hexadecimal, você pode usar ferramentas online.

**Ao abrir tíquetes** sobre problemas de codificação, para o provedor ou o suporte do Campaign, **inclua uma versão hexadecimal** do que você digita e do que vê.

**Etapa 3: saiba o que você deve enviar**

Determine a codificação que você espera que seja usada e pesquise online a tabela de caracteres dela. Verifique se os caracteres que você deseja enviar estão disponíveis na página de código de destino. Verifique se o campo data_coding está correto e corresponde ao que você e o provedor esperam.

**Etapa 4: saiba o que você realmente enviou**

Você precisará da saída de depuração do conector para ver exatamente quais bytes enviou ao provedor. Problemas de codificação aparecem em SUBMIT_SM PDUs, portanto, capture-os. Envie mensagens muito distintas, que sejam fáceis de encontrar no log.

Não hesite em enviar diferentes tipos de caracteres especiais ao testar. Por exemplo, a codificação GSM7 tem caracteres estendidos que são muito distintos em sua forma hexadecimal, de modo que são fáceis de identificar porque não aparecem em nenhuma outra codificação.

#### Problemas de desempenho {#sms-performance-issues}

>[!NOTE]
>
>Desempenho é um tópico muito amplo. Esta seção fornece algumas verificações básicas a serem feitas antes de tentar dimensionar ou executar outros projetos grandes.

**Problemas de desempenho ao enviar o MT**

* Verifique se todas as configurações na seção Throughput and delays da conta externa estão corretas e se elas correspondem às configurações permitidas pelo provedor.
* Verifique se não há tentativas.
* Verifique se a infraestrutura do provedor não está saturada. Verifique se há erros RMSGQFUL ou RTHROTTLED em PDUs RESP.
* Verifique as configurações de serverConf. Comece com valores padrão e aumente os parâmetros lentamente e um por um.
* Verifique se o processo SMS não é reiniciado o tempo todo quando está sendo carregado. Se isso acontecer, talvez seja necessário aumentar *maxSMSMemoryMb*, *maxProcessMemoryAlertMb* e *maxProcessMemoryWarningMb* no arquivo serverConf.

**Problemas de desempenho ao receber SR**

Se o provedor reclamar da sobrecarga de buffer, talvez o Campaign não receba o SR rápido o suficiente.

* Verifique se o banco de dados da instância não está sobrecarregado. O processamento SR é muito dependente do desempenho do banco de dados.
* Peça ao provedor que aumente a janela de envio para DELIVER_SM de seu lado. Idealmente, ele deve ser tão grande quanto a configuração *batchUpdateSize* em serverConf.

### Elementos a serem incluídos ao se comunicar sobre um problema de SMS

Sempre que buscar assistência para um problema de SMS (seja para abrir um tíquete de suporte para o Adobe Campaign, para o provedor de SMS ou qualquer tipo de comunicação sobre o problema), você precisará incluir pelo menos as seguintes informações para ter certeza de que ele será qualificado corretamente. Questões adequadamente qualificadas são fundamentais para resolver problemas mais rapidamente, portanto, dar um pouco mais de tempo para tentar entender a situação e fornecer informações significativas levará a um enorme salto na eficiência.

* Ative as mensagens SMPP detalhadas durante o horário em que o problema ocorre. A maioria dos problemas de SMS é praticamente impossível de resolver sem isso.
* Se o problema estiver relacionado ao tráfego de SMS, entre em contato primeiro com o provedor. Eles são os mais experientes e sua plataforma geralmente é adequada para o diagnóstico eficiente de problemas de tráfego de SMS em tempo real.
* Inclua uma descrição breve e concreta do problema.
* Inclua uma descrição do resultado esperado.
* Inclua todos os comentários do provedor.
* Inclua logs e/ou capturas de rede relevantes. Ao fazer capturas, reproduza o problema durante a captura ou ele será inútil.
* Se você incluir logs, rastreamentos ou capturas, aponte o local exato no arquivo quando o problema ocorrer, bem como o local exato de um exemplo em funcionamento, se houver. Capturas ou rastreamentos podem ser grandes e tediosos de olhar, então qualquer coisa que ajude a encontrar informações neles é útil.
* Se você mencionar mensagens, PDUs ou logs, indique claramente a data e a hora para que sejam fáceis de encontrar por outras pessoas.
* Tente reproduzir o problema em um ambiente de teste. Se não tiver certeza sobre uma configuração, experimente-a no ambiente de teste e verifique o resultado com os rastreamentos SMPP. Geralmente, é melhor relatar problemas replicados em ambientes de teste do que problemas em ambientes de produção.
* Inclua qualquer alteração ou ajuste feito na plataforma: mesmo uma pequena alteração pode ter enormes impactos. Além disso, inclua qualquer alteração que o provedor possa ter feito.

#### Quando uma captura de rede é útil?

Nem sempre é necessária uma captura de rede. Muitas vezes, as mensagens SMPP detalhadas são suficientes. Estas são algumas diretrizes que ajudarão você a determinar se uma captura de rede compensa o esforço:

* Problemas de conexão, mas as mensagens detalhadas não mostram nenhuma PDU BIND_RESP.
* Desconexões inexplicáveis sem mensagem de erro (esse é o comportamento do conector quando detecta um erro de protocolo de baixo nível).
* O provedor reclama sobre o processo de desconexão/desassociação.
* Há problemas de codificação em campos TLV opcionais.
* Há suspeita de que o tráfego esteja misturado entre conexões diferentes.

Em todas as outras situações, tente analisar as mensagens SMPP detalhadas primeiro e solicitar uma captura de rede somente se estiver claro que há informações ausentes nos logs detalhados.

#### Quando uma captura de rede é inútil?

Em alguns casos, capturar o tráfego da rede é inútil ou apenas uma perda de tempo. As situações mais comuns são:

* TLS ativado: por definição, o tráfego TLS é criptografado para que não possa ser capturado.
* Problemas de desempenho: os logs contêm todas as informações necessárias para rastrear problemas de desempenho.
* Problemas de tempo (tempo de repetição, período inquire_link, limite de rendimento ...)
* Análise e processamento SR: os registros detalhados dão muito mais contexto e uma apresentação melhor.
* Processamento de MO (respostas automáticas, quarentena).
* Erros que não envolvem o tráfego SMPP real: preparação de delivery, problemas da API do centro de mensagens, problemas de fluxo de trabalho, ...
