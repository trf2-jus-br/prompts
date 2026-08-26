---
uuid: 9c83c855-1c47-4f16-bd1f-a010240209e4
name: Juízo de Voto
description: Prepare o juízo de votação do recurso, com análise sequencial de verificações preliminares, conformidade com teses vinculantes e mérito, atribuindo o desfecho aplicável a cada pedido.
sort: 3
share: oculto
piece_strategy: mais-relevantes-segunda-instancia
---

# PROMPT

Leia atentamente o conteúdo das peças processuais fornecidas abaixo.

{{textos}}

Você leu diversos documentos de um processo judicial em segunda instância.

Você leu, também, um documento marcado como <pedidos-do-recurso-e-argumentos> que contém os pedidos formulados no recurso judicial e os argumentos apresentados para embasar cada pedido. A extração dos pedidos e argumentos já foi realizada previamente e deve ser reaproveitada.

Você leu um documento marcado como <pesquisa-de-temas> que contém a análise jurídica do recurso com base em teses e súmulas vinculantes. Se você optar por utilizar essa análise, deverá transcrever os dados dessa análise nos campos apropriados da resposta. No entanto, é importante destacar que a análise realizada no documento marcado como <pesquisa-de-temas> não é definitiva e pode ser complementada ou corrigida com base em outras informações disponíveis sobre o processo. Portanto, você deve considerar todas as informações disponíveis para realizar uma análise completa e precisa.

Você pode ter lido, também, um levantamento analítico do processo (sistematização da lide, do juízo de admissibilidade, do confronto de teses e dos desfechos possíveis), produzido em etapa anterior. Se presente, utilize-o como insumo preparatório — ele não é vinculante e não dispensa as verificações próprias deste juízo.

## Considerações Iniciais

1. Juízo de Votação

O juízo de votação leva em consideração uma série de análises efetuadas.
- Essas análises seguem, em regra, uma ordem sequencial: cada etapa só é examinada depois de vencida a anterior;
- O juízo de conhecimento tem primazia sobre o juízo de mérito — regra;
- Há, contudo, determinados vícios que autorizam afastar o exame do mérito com o não conhecimento do recurso (hipóteses de não conhecimento);
- A ordem sequencial comporta uma exceção relevante: nem toda hipótese de conformidade encerra a análise. O sobrestamento é terminal — incidindo, o julgamento limita-se ao tema e as demais questões não são analisadas. Já a improcedência (desprovimento) por contrariedade a tese vinculante convive, na mesma decisão, com o juízo de mérito das questões que não sejam objeto de tema (decisão mista).

2. Óbices iniciais

Há hipóteses que podem levar ao não conhecimento do recurso e que devem ser analisadas antes mesmo da conformidade. São seis verificações iniciais principais:
2.1. Verificar se houve preparo;
2.2. Verificar se o recurso é tempestivo (art. 1.003, §5º, do CPC).
2.3. Verificar se a via recursal eleita é cabível;
2.4. Verificar se a representação processual está regular;
2.5. Verificar se existe interesse recursal;
2.6. Verificar se o recorrente possui legitimidade recursal.
Caso não superada qualquer dessas hipóteses acima, o recurso deve ser não conhecido.

3. Juízo de Conformidade

Verificado o preparo, a tempestividade, o cabimento da via eleita, a regularidade da representação processual, o interesse recursal e a legitimidade recursal, passa-se ao juízo de conformidade: é necessário verificar se há (ou não) um Tema Repetitivo (STJ) ou de Repercussão Geral (STF) que se amolde perfeitamente ao caso concreto. A mera existência de um Tema sobre matéria correlata não basta. O Tema só será aplicado quando houver (i) identidade da questão jurídica entre o recurso e o Tema e (ii) similitude fática suficiente para que a ratio decidendi do precedente seja transponível ao caso. Havendo elementos distintivos relevantes entre a controvérsia recorrida e o paradigma (distinguishing), o Tema não se aplica e a análise prossegue como se inexistisse. NUNCA sugira a aplicação de tese de repercussão geral na qual o STF tenha reconhecido a ausência de repercussão geral ou o caráter infraconstitucional da controvérsia. Confirmada a aplicação do Tema, deve ser analisada a conformidade, na seguinte sequência:
3.1. Verificar se é hipótese de sobrestamento (art. 313, VI, e art. 1.040 do CPC);
3.2. Verificar se é hipótese de dar ou negar provimento.

4. Juízo de Mérito

Passa-se ao juízo de mérito quando: (i) não houver tema de repercussão geral ou de recurso repetitivo sobre as questões recorridas; ou (ii) quando as demais questões não são abrangidas por tema.
Não se chega a esta etapa nas hipóteses de sobrestamento, que encerram o julgamento.
Para que o mérito seja apreciado, não deve haver tema que imponha sobrestamento, provimento ou negativa de provimento, nem qualquer hipótese de não conhecimento.


## Roteiro de Verificação

Utilize a seguinte sequência de verificações para analisar:

### Verificações Preliminares de Não Conhecimento
- Se houver algum motivo de não conhecimento geral, independente da análise do pedido ou argumento específico, o recurso não deve ser conhecido.
- Neste caso, informe o motivo no campo "motivoGeral" do JSON.
- Este campo é um array, pois pode haver mais de um motivo geral.
- As opções de motivos gerais estão listadas abaixo.

#### Verificar se houve preparo
- Óbice que impede o conhecimento do recurso quando o preparo não foi regularizado, faltando requisito essencial de admissibilidade (art. 1.007 do CPC). Abrange: (i) ausência total de preparo — a parte não comprovou o recolhimento no ato de interposição e, intimada a recolher em dobro (art. 1.007, §4º, do CPC), deixou o prazo decorrer in albis; (ii) preparo insuficiente — recolheu valor a menor e, intimada a complementar (art. 1.007, §2º), não o fez no prazo de 5 dias; (iii) gratuidade requerida após a interposição — o pedido de justiça gratuita foi formulado fora do ato recursal e sua concessão não afasta o recolhimento em dobro; (iv) gratuidade indeferida — o pedido foi negado por falta de demonstração de hipossuficiência (art. 99, §2º, do CPC) e o prazo concedido para regularizar o preparo decorreu in albis; e (v) defeito formal na comprovação do preparo, em que a guia de recolhimento não evidencia o pagamento efetivo (não bastando o comprovante de mero agendamento bancário) ou não identifica corretamente o processo de origem.
- caso não haja preparo regular: não conhecimento pelo motivo *DESERCAO*.

#### Verificar Irregularidade da representação processual
- Óbice que impede o conhecimento do recurso quando a representação processual da parte recorrente apresenta vício não sanado, faltando pressuposto processual que deve subsistir durante todo o trâmite, inclusive na fase recursal. Configura-se quando, identificado o vício — por exemplo, renúncia do advogado subscritor após a interposição, ausência de procuração válida nos autos em nome do signatário, ou procuração cujos poderes não abrangem a prática de atos em sede recursal —, a parte, regularmente intimada a saná-lo no prazo de 5 dias (art. 932, parágrafo único, do CPC), deixa de fazê-lo. Art. 76, §2º, I, do CPC.
- caso seja identificada: não conhecimento pelo motivo *IRREGULARIDADE_REPRESENTACAO*.

#### Verificar Ilegitimidade
- Óbice que impede o conhecimento do recurso por ausência de legitimidade recursal, pressuposto subjetivo de admissibilidade (art. 996 do CPC), que só autoriza a recorrer as partes, o Ministério Público e o terceiro prejudicado. Configura-se quando, por exemplo, o recurso é interposto por quem não figurou como parte no processo, por quem não integrou a relação processual (sem ter sido admitido como assistente, litisconsorte ou terceiro interveniente) nem demonstra a condição de terceiro prejudicado, ou por signatário que não detém poderes de representação da pessoa jurídica recorrente.
- caso seja identificada: não conhecimento pelo motivo *ILEGITIMIDADE*.

#### Verificar se o recurso é tempestivo
- Óbice que impede o conhecimento do recurso interposto fora do prazo de 15 dias úteis (art. 1.003, §5º, do CPC), por inexistir fato apto a interromper ou suspender o prazo. Abrange quatro realidades: (i) interposição pura e simples após o término do prazo; (ii) embargos de declaração não conhecidos, que não interrompem o prazo recursal (ex.: por intempestivos ou por não indicarem vício do art. 1.022 do CPC); (iii) agravo interno não conhecido, que não reabre o prazo recursal; e (iv) alegação de feriado local ou de suspensão do expediente forense sem a comprovação no ato de interposição exigida pelo art. 1.003, §6º, sendo inadmissível a juntada posterior do documento.
- caso não seja tempestivo: não conhecimento pelo motivo *INTEMPESTIVIDADE*.

#### Verificar Falta de interesse
- Óbice que impede o conhecimento do recurso por ausência de interesse recursal, pressuposto objetivo de admissibilidade que exige que a decisão recorrida tenha deixado de atender, total ou parcialmente, à pretensão da parte — pois somente o desatendimento do pedido confere ao recurso a utilidade necessária. Abrange duas realidades: (i) a decisão recorrida atendeu integralmente ao que a parte pediu, inexistindo desatendimento a reparar; e (ii) a decisão recorrida acolheu o pedido, mas a parte almeja resultado mais amplo ou imediato do que efetivamente requereu — e a mera expectativa de um resultado além do pedido não configura o desatendimento que legitima o recurso.
- caso seja identificada: não conhecimento pelo motivo *FALTA_DE_INTERESSE_RECURSAL*.

#### Verificar o cabimento da via recursal
- Óbice que impede o conhecimento do recurso quando, havendo meio de impugnação próprio e adequado contra o provimento atacado, a parte deixou de utilizá-lo ou utilizou via inadequada. Abrange duas realidades: (i) a parte deixou de interpor o recurso cabível contra a decisão impugnada (ex.: apelação contra sentença, agravo de instrumento contra decisão interlocutória), preferindo via imprópria; e (ii) o recurso interposto não é o adequado ao provimento impugnado (descabimento), sem que se possa invocar o princípio da fungibilidade recursal.
- caso seja identificada: não conhecimento pelo motivo *DESCABIMENTO*.
- Caso não superadas as hipóteses acima, o recurso não deve ser conhecido; caso superadas, passa-se à etapa seguinte.

### Juízo de Conformidade
- Somente se superadas as verificações preliminares de não conhecimento e se houver tema de repercussão geral ou recurso repetitivo que se amolde perfeitamente ao caso concreto, nos termos do item 3 das Considerações Iniciais.
- O juízo de conformidade está relacionado à aplicação dos temas de recurso repetitivo (STJ) e de repercussão geral (STF) à controvérsia devolvida ao colegiado, observados os critérios de identidade da questão jurídica e similitude fática que autorizam a transposição da ratio decidendi do precedente ao caso (afastando-se a aplicação do tema quando houver distinguishing). NUNCA sugira a aplicação de tese de repercussão geral na qual o STF tenha reconhecido ausência de repercussão geral ou o caráter infraconstitucional da controvérsia.
- A análise do juízo de conformidade pode resultar em 2 (duas) situações distintas:
  - Sobrestamento/suspensão do processo, até o julgamento definitivo do tema;
  - Resolução da controvérsia pela própria tese firmada no tema, julgando o recurso com fundamento na tese vinculante (provimento ou desprovimento, conforme o caso).
- Princípio da subsunção ordinária (aplicar tese ≠ revolver matéria de fato): a aplicação de uma tese ao caso concreto sempre exige subsumir os fatos do caso à hipótese normativa do precedente. Isso é jurisdição ordinária, não reexame de prova. Não confunda "aplicar a tese exige verificar como os fatos do caso se enquadram na hipótese do precedente" (situação normal e inevitável em qualquer aplicação do direito) com "a tese trata de hipótese fática genericamente diferente da do caso" (distinguishing legítimo). Esses dois planos têm consequências opostas:
   - Quando a tese se ocupa da MESMA questão jurídica e da MESMA situação fática genérica do caso, ela SE APLICA e deve fundamentar o julgamento do recurso (dar ou negar provimento, conforme o desfecho que a tese impõe), AINDA QUE a aplicação demande examinar como, naquele caso concreto, os elementos previstos na tese se realizam.
   - Apenas quando a tese se ocupa de hipótese fática genericamente DIFERENTE da do caso (o precedente discute uma situação normativa distinta) há distinguishing, e a tese não se aplica, prosseguindo a análise de mérito pelas demais questões.
- No julgamento de segundo grau, é admissível o reexame da matéria fático-probatória devolvida (art. 1.013, §1º, do CPC): a circunstância de a aplicação de uma tese exigir verificar a presença dos elementos do precedente no caso concreto NÃO equivale a "reexame de prova" e NÃO afasta a aplicação da tese. Você NÃO deve afastar a aplicação de uma tese sob fundamento de que sua aplicação demandaria avaliar circunstâncias do caso — avaliar circunstâncias do caso para subsumir à norma é o que todo julgador faz. A tese apenas não resolve a controvérsia quando a questão devolvida for exclusivamente fático-probatória, sem questão jurídica alguma que a tese possa decidir — hipótese em que o julgamento se fará pela análise probatória, no juízo de mérito.
- Caso identificada hipótese de sobrestamento/suspensão, você não deve indicar provimento, desprovimento, não conhecimento ou prejudicialidade, pois o sobrestamento é hipótese de exclusão absoluta de todas as demais hipóteses.
  
#### Verificar se é hipótese de sobrestamento/suspensão (art. 313, VI, e art. 1.040, ambos do CPC)
- Se o tema de repercussão geral e/ou de recurso repetitivo identificado não tiver sido definitivamente julgado (trânsito em julgado), no âmbito do STJ e/ou do STF, deve ser adotada uma das seguintes alternativas:
  - Se não houve julgamento do Tema, o processo deve ser sobrestado até o julgamento do Tema pelo tribunal competente;
  - Se houve o julgamento do Tema, mas não ocorreu o trânsito em julgado, deve ser mantido o sobrestamento;
  - Se forem identificados 02 (dois) ou mais temas pendentes, de repercussão geral e/ou de recurso repetitivo, a decisão deverá determinar o sobrestamento até o julgamento de todos eles;
  - Se forem identificados, simultaneamente, 1 (um) tema pendente e outras questões sobre as quais não exista tema (hipótese de juízo de mérito), o processo deve ser sobrestado pelo Tema, conforme uma das decisões acima;
  - Na hipótese de sobrestamento por Tema não (definitivamente) julgado, as demais questões tratadas no recurso não serão analisadas no julgamento. Todo o processo deve ser sobrestado. Ficarão pendentes o juízo de conformidade (relativo aos temas já julgados) e o juízo de mérito (referente às demais questões recorridas sobre as quais não haja tema) até que ocorra o julgamento do(s) tema(s) pendente(s). O sobrestamento será a única questão abordada no julgamento. Caso identificada hipótese de sobrestamento/suspensão, você não deve indicar provimento, desprovimento, não conhecimento ou prejudicialidade, pois o sobrestamento é hipótese de exclusão absoluta de todas as demais hipóteses;
  - Se houver tema de repercussão geral não definitivamente julgado (hipóteses acima), o processo deve ser suspenso ainda que o recurso em julgamento não seja recurso extraordinário;
- caso seja identificada: utilizar o dispositivo *SUSPENDER* (suspensão do processo até o julgamento do tema pelo tribunal competente).

#### Verificar se é hipótese de dar provimento com fundamento na tese
- Se todos os temas de repercussão geral ou de recursos repetitivos relevantes para a controvérsia já estiverem definitivamente julgados (trânsito em julgado) e não houver outro tema pendente de julgamento, e se verificado que a decisão recorrida **NÃO está** em conformidade com a tese firmada no Tema, o recurso deve ser provido, para que o provimento de origem seja reformado e a tese vinculante seja aplicada ao caso concreto;
- Na hipótese de provimento com fundamento na tese, as demais questões tratadas no recurso também deverão ser analisadas no mesmo julgamento: aplica-se a tese à matéria a ela sujeita (com fundamento no art. 927, caput, do CPC) e efetua-se o juízo de mérito referente às demais questões recorridas.
- caso seja identificada: utilizar o dispositivo *DAR_PROVIMENTO* (provimento do recurso com aplicação da tese vinculante).

#### Verificar se é hipótese de negar provimento com fundamento na tese
- Se todos os temas de repercussão geral ou de recursos repetitivos relevantes para a controvérsia já estiverem definitivamente julgados (trânsito em julgado) e não houver outro tema pendente de julgamento, e se verificado que a decisão recorrida **está** em conformidade com a tese firmada no Tema, deve ser negado provimento ao recurso;
- Na hipótese de negativa de provimento com fundamento na tese, as demais questões tratadas no recurso também deverão ser analisadas no mesmo julgamento: aplica-se a tese à matéria a ela sujeita (com fundamento no art. 927, caput, do CPC) e efetua-se o juízo de mérito referente às demais questões recorridas.
- caso seja identificada: utilizar o dispositivo *NEGAR_PROVIMENTO* (desprovimento do recurso com aplicação da tese vinculante).

##### Hipóteses que NÃO configuram julgamento com fundamento em tese (a questão não é devolvida ao colegiado)
- Alegação de violação aos arts. 1.022 e/ou 489 do CPC (omissão, contradição ou obscuridade) ou qualquer alegação de negativa de prestação jurisdicional contra decisão que enfrentou, de forma clara e fundamentada, os pontos essenciais da controvérsia: NÃO se trata de hipótese de provimento nem de aplicação de tese. Inexistente o vício de integração alegado — segundo a jurisprudência consolidada, o julgador não é obrigado a rebater individualmente todos os argumentos das partes, bastando expor as razões de seu convencimento —, a hipótese é de desconsideração do pedido ou argumento correspondente, por ausência de matéria a julgar, pelo motivo *AUSENCIA_DE_MATERIA*;
- Nesses casos, NÃO utilize os dispositivos DAR_PROVIMENTO ou NEGAR_PROVIMENTO, nem indique tema de repercussão geral: utilize, conforme o caso, o dispositivo NAO_CONHECER ou DESCONSIDERAR, com o motivo correspondente.
 
### Juízo de Mérito
- O juízo de mérito é realizado depois de superadas as verificações preliminares e desde que NÃO seja caso de sobrestamento — hipótese em que, conforme acima, as demais questões não são analisadas e o julgamento se limita àquele tema.
- Ele se aplica em duas situações:
  (i) quando não houver tema de repercussão geral ou de recurso repetitivo sobre nenhuma das questões recorridas; ou
  (ii) quando houver questões recorridas que não sejam abrangidas por tema definitivamente julgado — situação em que essas questões devem ser julgadas, NA MESMA DECISÃO, pelo colegiado, ainda que parte da controvérsia seja resolvida pela tese vinculante.
- Antes de julgar o mérito de cada questão, verifique se há óbice ao conhecimento da própria questão (deficiência de fundamentação recursal). Se houver, a questão não deve ser conhecida, utilizando o dispositivo *NAO_CONHECER*.

#### Pressupostos de conhecimento da questão recorrida (dialeticidade recursal)

##### Deficiência de Fundamentação (art. 1.010, II e III, do CPC)
- Óbice que impede o conhecimento da questão recorrida quando as razões recursais não permitem a exata compreensão da controvérsia, por falta de argumentação clara, individualizada e vinculada à decisão recorrida ou por falta de impugnação específica analítica dos fundamentos da decisão recorrida. O recurso deve impugnar específica e analiticamente cada fundamento da decisão recorrida, bem como desenvolver argumentação clara, individualizada e específica para cada ponto impugnado, sob pena de deficiência na fundamentação. Abrange três realidades: (i) fundamentação genérica ou abstrata, dissociada dos fundamentos do julgado; (ii) indicação ou mera enumeração dos pontos tidos por violados sem desenvolver a argumentação específica que demonstre, de forma analítica, como a decisão os teria contrariado; e (iii) razões que atacam fundamentos inexistentes na decisão recorrida ou discutem matéria não examinada na origem. Súmula 284 do STF (por analogia).
- caso seja identificada: não conhecimento da questão pelo motivo *DEFICIENCIA_FUNDAMENTACAO*.

##### Fundamento autônomo suficiente não impugnado (Súmula 283/STF, por analogia)
- Óbice que impede o conhecimento da questão recorrida quando a decisão recorrida se apoia em mais de um fundamento, cada qual suficiente por si só para mantê-la, e o recurso não impugna todos eles, deixando subsistir fundamento autônomo capaz de preservar a conclusão. Abrange duas realidades: (i) a recorrente impugnou parte dos fundamentos, mas não o fundamento autônomo que basta para manter o julgado; e (ii) a recorrente não impugnou esse fundamento autônomo. Em ambas, o provimento do recurso seria inútil. Súmula 283 do STF (por analogia).
- caso seja identificada: não conhecimento da questão pelo motivo *FUNDAMENTO_AUTONOMO*.

#### Julgamento da questão no mérito (desfechos)
- Superadas as verificações preliminares, afastada a hipótese de sobrestamento e não sendo caso de não conhecimento, cada pedido deve ser julgado no mérito, com exame da matéria de fato e de direito devolvida.
- A tese firmada em tema definitivamente julgado deve ser aplicada de ofício (art. 927, caput, do CPC), vinculando o julgamento da matéria abrangida.
- Para cada pedido, verifique se ele é procedente, improcedente ou parcialmente procedente, à luz dos argumentos invocados, da legislação aplicável e do material probatório dos autos. Julgue cada questão conforme o desfecho adequado:
  - se o pedido deve ser acolhido integralmente: utilizar o dispositivo *DAR_PROVIMENTO*;
  - se o pedido deve ser acolhido apenas em parte: utilizar o dispositivo *DAR_PROVIMENTO_PARCIAL*;
  - se o pedido deve ser rejeitado: utilizar o dispositivo *NEGAR_PROVIMENTO*.

### Recurso Prejudicado
O recurso recebe dispositivo *RECURSO_PREJUDICADO* quando, supervenientemente à sua interposição, fato ou ato processual esvazia o seu objeto, retirando a utilidade do exame de mérito. A perda de objeto deve ser verificada com cautela: só configura essa hipótese quando NENHUMA matéria do recurso remanescer.

#### Sentença de mérito superveniente em recurso sobre tutela provisória
Quando o recurso tem por objeto decisão proferida em agravo de instrumento que discutiu tutela provisória — de urgência (antecipada ou cautelar) ou de evidência — e, no curso do processo principal, sobreveio sentença de mérito que decide definitivamente a matéria objeto da tutela, o recurso fica prejudicado. A sentença substitui a tutela provisória, esvaziando o objeto do recurso, cuja discussão se limitava ao cabimento, alcance ou manutenção daquela medida provisória. Atribua *RECURSO_PREJUDICADO*.
- Cuidado: a prejudicialidade pressupõe que a sentença de mérito tenha efetivamente decidido a matéria objeto da tutela provisória. Se a sentença tratou de questão distinta, ou se a tutela protege aspecto não decidido na sentença (ex.: cautelar conservativa que protege bem diverso do objeto principal da ação), não há prejudicialidade.

*RECURSO_PREJUDICADO* aplica-se ao recurso como um todo. Se a perda de objeto for parcial, não atribua esse dispositivo — analise cada pedido segundo as regras gerais.

### Desconsiderar o pedido ou o argumento
- Caso o pedido ou argumento não seja relevante para o juízo de votação, ou caso o pedido ou argumento seja repetitivo em relação a outros pedidos ou argumentos já analisados, ou já tenha sido tomada uma decisão de suspensão, ele deve ser desconsiderado, utilizando o dispositivo *DESCONSIDERAR*.
- Pedido de gratuidade de justiça formulado para o processamento do próprio recurso NÃO é pedido de mérito recursal. Trata-se de requerimento procedimental, dirigido ao relator, paralelo ao recurso, sem matéria a ser examinada em juízo de conformidade ou de mérito. Atribua dispositivo *DESCONSIDERAR*.
  - Distinção essencial: o pedido de REFORMA da decisão que tenha negado a gratuidade NÃO se confunde com o pedido procedimental acima. Quando o recurso impugna a parcela da decisão que indeferiu a justiça gratuita na origem, o pedido é de mérito recursal e deve passar pela análise normal (juízo de conformidade e juízo de mérito, conforme o caso).
  - Critério prático: pergunte-se "este item busca a reforma de algo que o primeiro grau decidiu sobre gratuidade, ou busca apenas obter a gratuidade para os atos do próprio recurso?". Se a resposta for "reforma" → mérito recursal (análise normal). Se for "apenas obter para os atos do recurso" → procedimental (*DESCONSIDERAR*).


## FIELDS

Os campos abaixo compõem o JSON de diretrizes que orientará a redação do voto na etapa seguinte. O usuário poderá revisar e editar esse JSON antes da redação do voto — preencha-o, portanto, com a sua melhor sugestão, de modo completo e fundamentado.

### motivoGeral[] (opcional, opções: DESERCAO, IRREGULARIDADE_REPRESENTACAO, ILEGITIMIDADE, INTEMPESTIVIDADE, FALTA_DE_INTERESSE_RECURSAL, DESCABIMENTO) - Motivo do Não Conhecimento
- Quando for o caso de não conhecer por um motivo geral, independente da análise do pedido ou argumento específico, deve ser informado neste campo o identificador do motivo do não conhecimento do recurso.
- As opções de motivos estão listadas e explicadas no título Verificações Preliminares de Não Conhecimento, acima.
- Caso haja mais de um motivo geral, informe todos os motivos aplicáveis neste campo, utilizando um array. Preencha este campo com [].

### pedidos[] - Pedidos

##### texto - Texto do Pedido
- Informe o texto conciso que descreve o pedido de mérito recursal
- Esse texto deve ser copiado do documento ipsis litteris, do documento marcado como <pedidos-do-recurso-e-argumentos>.

##### dispositivo (opções: SUSPENDER, DAR_PROVIMENTO, DAR_PROVIMENTO_PARCIAL, NEGAR_PROVIMENTO, NAO_CONHECER, DESCONSIDERAR, RECURSO_PREJUDICADO) - Dispositivo do Pedido
- Se foi identificado um tema pendente de julgamento definitivo, utilize a opção SUSPENDER.
- Se foi identificado um ou mais motivos de não conhecimento, a opção NAO_CONHECER deve ser utilizada.
- Se um pedido anterior já foi marcado com SUSPENDER, e não houver tema ou motivo de não conhecimento específico para o pedido atual, preencha este campo com DESCONSIDERAR.
- Quando um pedido vier marcado como SUBSIDIARIO ou ALTERNATIVO em relação a outro, e o pedido vinculado já tiver sido provido ou decidido em termos que o tornem prejudicial, o dispositivo do pedido subsidiário/alternativo deve ser DESCONSIDERAR. Caso o pedido vinculado tenha sido não conhecido sem afetar o subsidiário (ex.: não conhecimento da preliminar de nulidade não prejudica o pedido subsidiário de reforma de mérito), o subsidiário deve receber análise própria.
- Quando o pedido tiver Tp_Relacao=ACESSORIO com Id_PedidoVinculado preenchido: o pedido recebe DESCONSIDERAR. O acessório não tem existência autônoma para fins de julgamento — está contido na decisão sobre o principal (se este for provido) ou é por ele prejudicado (se este for negado, suspenso ou não conhecido). A análise incide exclusivamente sobre o pedido principal vinculado.
- Quando o pedido tiver Tp_Relacao=SUBSIDIARIO com Id_PedidoVinculado preenchido: aplique a propagação apenas se o pedido vinculado tiver recebido dispositivo DAR_PROVIMENTO — nesse caso, o subsidiário recebe DESCONSIDERAR (a pretensão principal foi acolhida, tornando inútil a alternativa). Em todos os demais casos (principal recebeu NEGAR_PROVIMENTO, DAR_PROVIMENTO_PARCIAL, SUSPENDER, NAO_CONHECER ou DESCONSIDERAR), o pedido subsidiário deve ser analisado autonomamente, recebendo dispositivo conforme as regras gerais deste campo.

##### tema[] (opcional) - Tema do Pedido
- Quando o dispositivo for SUSPENDER, DAR_PROVIMENTO ou NEGAR_PROVIMENTO com fundamento em tese vinculante, devem ser informados neste campo um ou mais identificadores dos temas que poderão ser obtidos no documento marcado como <pesquisa-de-temas>. Caso a análise de temas não tenha informado o tema para suspensão ou julgamento com fundamento na tese, deixe esse campo em branco.
- O identificador do tema tem o formato "stj-rr-123" ou "stf-rg-456", conforme o tribunal e o tipo de tema. Ele pode ser encontrado no documento marcado como <pesquisa-de-temas> em passagens como por exemplo: (ID: stf-rg-123) ou (ID: stj-rr-456).

##### motivo[] (opcional, opções: DEFICIENCIA_FUNDAMENTACAO, FUNDAMENTO_AUTONOMO, AUSENCIA_DE_MATERIA) - Motivo do Não Conhecimento
- Quando o dispositivo for NAO_CONHECER, deve ser informado neste campo o identificador do motivo do não conhecimento da questão.
- As opções de motivos estão listadas e explicadas nos títulos Juízo de Mérito e Hipóteses que NÃO configuram julgamento com fundamento em tese, acima. 
- Caso haja mais de um motivo, informe todos os motivos aplicáveis neste campo, utilizando um array. Caso contrário, preencha este campo com [].

##### fundamentacoes[] - Fundamentações Sugeridas do Pedido
- Liste sugestões de fundamentação a favor e contra o pedido, para orientar a redação do voto na etapa seguinte.
- Apresente entre 2 e 4 sugestões de cada tipo (A_FAVOR e CONTRA). Extraia ou sintetize as sugestões a partir das peças (razões recursais, contrarrazões, sentença), do documento marcado como <pesquisa-de-temas> (teses e súmulas aplicáveis) e, se presente, do levantamento analítico do processo — não as invente.
- O usuário poderá revisar este JSON e alterar as marcações (inclusive o próprio teor das fundamentações) antes da redação do voto; a redação utilizará as fundamentações marcadas como roteiro.
- Quando o dispositivo do pedido for SUSPENDER, RECURSO_PREJUDICADO ou DESCONSIDERAR, o preenchimento deste campo é opcional (pode permanecer vazio).
- Para cada sugestão, preencha os campos texto, tipo e checked:

###### Tg_Texto - Texto da Fundamentação
- A fundamentação, formulada de modo conciso e aplicável ao caso concreto (não uma máxima abstrata).

###### Tipo (opções: A_FAVOR, CONTRA) - Tipo da Fundamentação
- Tipo: A_FAVOR (fundamentação que sustenta o acolhimento do pedido) ou CONTRA (fundamentação que sustenta o seu desacolhimento).

###### Lg_Selecionada - Selecionada
- Indicação de que a sugestão deve ser aproveitada na redação do voto.
- Dentre as sugestões apresentadas, marque com true nas que entender pertinentes e mais importantes: tipicamente, as alinhadas com o dispositivo atribuído ao pedido e as contrárias relevantes que deverão ser enfrentadas na fundamentação. Marque checked=false nas demais. Isso é uma decisão da IA, que poderá ser revista pelo usuário antes da redação do voto.

#### argumentos[] - Argumentos do Pedido
- Liste os fundamentos jurídicos apresentados para embasar o pedido

##### texto - Texto do Argumento
- Esse texto deve ser copiado do documento marcado como <pedidos-do-recurso-e-argumentos>.

##### dispositivo (opções: SUSPENDER, DAR_PROVIMENTO, DAR_PROVIMENTO_PARCIAL, NEGAR_PROVIMENTO, NAO_CONHECER, DESCONSIDERAR, RECURSO_PREJUDICADO) - Dispositivo do Argumento
- Se desejar informar um dispositivo especificamente para o argumento, preencha este campo. Caso contrário, preencha este campo com DESCONSIDERAR.
- Se o pedido ao qual o argumento pertence tiver o campo dispositivo preenchido com SUSPENDER, DAR_PROVIMENTO ou NEGAR_PROVIMENTO, preencha este campo com DESCONSIDERAR.

##### tema[] (opcional) - Tema do Argumento
- Caso o campo dispositivo do argumento tenha sido preenchido com SUSPENDER, DAR_PROVIMENTO ou NEGAR_PROVIMENTO com fundamento em tese vinculante, faça conforme acima, mas para o argumento específico, ou deixe em branco.

##### motivo[] (opcional, opções: DEFICIENCIA_FUNDAMENTACAO, FUNDAMENTO_AUTONOMO, AUSENCIA_DE_MATERIA) - Motivo do Não Conhecimento
- Caso o campo dispositivo do argumento tenha sido preenchido com NAO_CONHECER, faça conforme acima, mas para o argumento específico, ou preencha este campo com [].
- As opções de motivos estão listadas e explicadas nos títulos Juízo de Mérito e Hipóteses que NÃO configuram julgamento com fundamento em tese, acima.
- Caso haja mais de um motivo para o argumento, informe todos os motivos aplicáveis neste campo, utilizando um array. Caso contrário, preencha este campo com [].

##### fundamentacoes[] - Fundamentações Sugeridas do Argumento
- Apresente, para o argumento, entre 2 e 4 sugestões A_FAVOR e entre 2 e 4 CONTRA, nos mesmos termos do campo fundamentacoes do pedido: cada sugestão com texto, tipo (A_FAVOR ou CONTRA) e checked, extraída ou sintetizada das peças, do documento marcado como <pesquisa-de-temas> e, se presente, do levantamento analítico do processo.
- Marque checked=true nas sugestões pertinentes, alinhadas com o dispositivo atribuído ao argumento ou contrárias relevantes a serem enfrentadas.
- Quando o dispositivo do argumento for DESCONSIDERAR (incluindo a hipótese de o pedido ter recebido SUSPENDER, DAR_PROVIMENTO ou NEGAR_PROVIMENTO), o preenchimento deste campo é opcional.

###### Tg_Texto - Texto da Fundamentação
- A fundamentação, formulada de modo conciso e aplicável ao caso concreto (não uma máxima abstrata).

###### Tipo (opções: A_FAVOR, CONTRA) - Tipo da Fundamentação
- Tipo: A_FAVOR (fundamentação que sustenta o acolhimento do pedido) ou CONTRA (fundamentação que sustenta o seu desacolhimento).

###### Lg_Selecionada - Selecionada
- Indicação de que a sugestão deve ser aproveitada na redação do voto.
- Dentre as sugestões apresentadas, marque com true nas que entender pertinentes e mais importantes: tipicamente, as alinhadas com o dispositivo atribuído ao pedido e as contrárias relevantes que deverão ser enfrentadas na fundamentação. Marque checked=false nas demais. Isso é uma decisão da IA, que poderá ser revista pelo usuário antes da redação do voto.


### Tg_ComandosAdicionais (opcional) - Comandos Adicionais
- Utilize este campo para informar quaisquer comandos adicionais que sejam necessários para redação do voto, que será feita em seguida, mas que não se encaixem nos campos anteriores. Por exemplo, caso seja necessário desmembrar um pedido ou argumento específico, ou caso haja alguma particularidade relevante para a análise, informe aqui. Se não houver comandos adicionais, deixe este campo em branco.

# FORMAT
{% if motivoGeral %}**Motivo(s) de Não Conhecimento Geral:** {{ motivoGeral | join(", ") }}
{% else %}
{% for d in pedidos %}{% set outerIndex = loop.index %}**Pedido {{loop.index}}:** {{ d.texto }}

Argumentos:{% for a in d.argumentos %}
{{loop.index}}. {{ a.texto }}{% endfor %}

Fundamentações:{% for f in d.fundamentacoes %}
{{loop.index}}. {{ "[x]" if f.checked else "[ ]" }} ({{ f.tipo }}) {{ f.texto }}{% endfor %}
    
{% endfor %}
{% endif %}

{% if Tg_ComandosAdicionais %}
**Comandos Adicionais:** {{ Tg_ComandosAdicionais }}
{% endif %}
