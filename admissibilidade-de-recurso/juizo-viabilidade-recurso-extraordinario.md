---
uuid: 64182d4d-da22-4135-8150-3379386db58a
name: Juízo de Viabilidade de Recurso Extraordinário
description: Realize o juízo completo de viabilidade do recurso extraordinário com análise sequencial de verificação preliminar, conformidade e admissibilidade.
sort: 3
share: oculto
piece_strategy: viabilidade-recurso-extraordinario
---

# PROMPT

Leia atentamente o conteúdo das peças processuais fornecidas abaixo.

{{textos}}

Você leu diversos documentos relacionados a Recurso Extraordinário em processo judicial.

Você leu, também, um documento marcado como <pedidos-do-recurso-e-argumentos> que contém os pedidos formulados no recurso judicial e os argumentos apresentados para embasar cada pedido. A extração dos pedidos e argumentos já foi realizada previamente e deve ser reaproveitada.

Você leu um documento marcado como <pesquisa-de-temas> que contém a análise de viabilidade jurídica do recurso com base em teses e súmulas vinculantes. Se você optar por utilizar essa análise, deverá transcrever os dados dessa análise nos campos apropriados da resposta. No entanto, é importante destacar que a análise de viabilidade jurídica realizada no documento marcado como <pesquisa-de-temas> não é definitiva e pode ser complementada ou corrigida com base em outras informações disponíveis sobre o processo, como o acórdão, o recurso e as contrarrazões. Portanto, você deve considerar todas as informações disponíveis para realizar uma análise completa e precisa da admissibilidade do recurso.

## Considerações Iniciais

1. Juízo de Viabilidade do RE (Recurso Extraordinário)

O juízo de viabilidade do Recurso Extraordinário leva em consideração uma série de análises efetuadas pela Vice-Presidência do Tribunal (juízo de conformidade e juízo de admissibilidade).
- Essas análises seguem, em regra, uma ordem sequencial: cada etapa só é examinada depois de vencida a anterior;
- O juízo de conformidade tem primazia sobre o juízo de admissibilidade — regra;
- Há, contudo, determinados vícios que autorizam afastar o juízo de conformidade para o exercício do juízo de admissibilidade (hipóteses de inadmissão);
- A ordem sequencial comporta uma exceção relevante: nem toda hipótese de conformidade encerra a análise. O sobrestamento e a retratação são terminais — incidindo, a decisão limita-se ao tema e as demais questões não são analisadas. Já a negativa de seguimento convive, na mesma decisão, com o juízo de admissibilidade das questões que não sejam objeto de tema (decisão mista).

2. Óbices iniciais à admissibilidade

Há hipóteses que podem levar à inadmissibilidade do recurso (juízo de admissibilidade) e que devem ser analisadas antes mesmo da conformidade. São seis verificações iniciais principais:
2.1. Verificar se houve preparo;
2.2. Verificar se a representação processual está regular;
2.3. Verificar se o recorrente possui legitimidade recursal;
2.4. Verificar se o recurso é tempestivo (art. 1.003, §5º, do CPC);
2.5. Verificar se existe interesse recursal;
2.6. Verificar se houve o esgotamento da jurisdição no órgão de origem.
Caso não superada qualquer dessas hipóteses acima, o recurso deve ser inadmitido


3. Juízo de Conformidade

Verificado o preparo, a regularidade da representação processual, a legitimidade recursal, a tempestividade, o interesse recursal e o esgotamento da instância, passa-se ao juízo de conformidade: é necessário verificar se há (ou não) um Tema de Repercussão Geral (STF) que se amolde perfeitamente ao caso concreto. A mera existência de um Tema sobre matéria correlata não basta. O Tema só será aplicado quando houver (i) identidade da questão jurídica entre o recurso e o Tema e (ii) similitude fática suficiente para que a ratio decidendi do precedente seja transponível ao caso. Havendo elementos distintivos relevantes entre a controvérsia recorrida e o paradigma (distinguishing), o Tema não se aplica e a análise prossegue como se inexistisse. Confirmada a aplicação do Tema, deve ser analisada a conformidade, na seguinte sequência:
3.1. Verificar se é hipótese de sobrestamento (art. 1.030, III, do CPC);
3.2. Verificar se é hipótese de retratação (art. 1.030, II, do CPC);
3.3. Verificar se é hipótese de negativa de seguimento (art. 1.030, I, "a", do CPC).
Observação própria do recurso extraordinário: a negativa de seguimento alcança também a hipótese de o STF haver **negado a existência de repercussão geral** sobre a questão (art. 1.030, I, "a", primeira parte, c/c art. 1.035, §8º, do CPC). Nesse caso, a conformidade do acórdão recorrido com tese é irrelevante: o recurso não segue porque a própria questão constitucional foi declarada sem repercussão geral.

4. Juízo de Admissibilidade

Passa-se ao juízo de admissibilidade quando: (i) não houver tema de repercussão geral sobre as questões recorridas; ou (ii) for caso de negativa de seguimento — seja porque o acórdão recorrido está em conformidade com a tese firmada, seja porque a repercussão geral da questão foi negada pelo STF —, hipótese em que a admissibilidade é examinada, na mesma decisão, quanto às demais questões não abrangidas por tema.
Não se chega a esta etapa nas hipóteses de sobrestamento e de retratação, que encerram a decisão.
Para que uma questão seja admitida, é necessário que não haja nenhum óbice à sua admissão.

5. Admissão

Uma questão recorrida será admitida quando não houver, sobre ela, tema que imponha sobrestamento, retratação ou negativa de seguimento (inclusive por repercussão geral negada), nem qualquer hipótese de inadmissão.
O recurso pode ser admitido integralmente — quando todas as questões superam os óbices — ou apenas em parte, quando algumas questões são admitidas e outras recebem negativa de seguimento ou inadmissão (decisão mista).

## Roteiro de Verificação

Utilize a seguinte sequência de verificações para analisar a admissibilidade do recurso extraordinário:

### Verificações Preliminares de Inadmissão
- Se houver algum motivo de inadmissão geral, independente da análise do pedido ou argumento específico, o recurso deve ser inadmitido.
- Neste caso, informe o motivo da inadmissão no campo "motivoGeral" do JSON.
- Este campo é um array, pois pode haver mais de um motivo de inadmissão geral.
- As opções de motivos de inadmissão geral estão listadas abaixo.

#### Verificar se houve preparo
- Óbice que impede a admissibilidade do recurso extraordinário quando o preparo não foi regularizado, faltando requisito essencial de admissibilidade. Abrange quatro realidades: (i) ausência total de preparo — a parte não comprovou o recolhimento no ato de interposição e, intimada para recolher em dobro (art. 1.007, §4º, do CPC), deixou o prazo decorrer in albis; (ii) preparo insuficiente — recolheu valor a menor e, intimada para complementar (art. 1.007, §2º), não o fez no prazo de 5 dias; (iii) gratuidade requerida após a interposição — o pedido de justiça gratuita foi formulado fora do ato recursal, e sua concessão não retroage para afastar o recolhimento em dobro; e (iv) gratuidade indeferida — o pedido foi negado por falta de demonstração de hipossuficiência (art. 99, §2º, do CPC) e o prazo concedido para regularizar o preparo decorreu in albis. Art. 1.007, caput e §§ 2º e 4º, do CPC.
- caso não haja: inadmissão pelo motivo *DESERCAO*.

####  Verificar Irregularidade da representação processual
- Óbice que impede a admissibilidade do recurso extraordinário quando a representação processual da parte recorrente apresenta vício não sanado, faltando pressuposto processual que deve subsistir durante todo o trâmite, inclusive na fase recursal. Configura-se quando, identificado o vício — por exemplo, renúncia do advogado subscritor após a interposição, ausência de procuração válida nos autos em nome do signatário, ou procuração cujos poderes não abrangem a prática de atos em sede recursal extraordinária —, a parte, regularmente intimada para saná-lo no prazo de 5 dias (art. 932, parágrafo único, do CPC), deixa de fazê-lo. Art. 76, §2º, I, do CPC.
- caso seja identificada: inadmissão pelo motivo *IRREGULARIDADE_REPRESENTACAO*.

####  Verificar Ilegitimidade
- Óbice que impede a admissibilidade do recurso extraordinário por ausência de legitimidade recursal, pressuposto subjetivo de admissibilidade (art. 996 do CPC), que só autoriza a recorrer as partes, o Ministério Público e o terceiro prejudicado. Configura-se quando, por exemplo, o recurso é interposto por quem não figurou como parte no processo de origem, por quem não integrou a relação processual nas instâncias ordinárias (sem ter sido admitido como assistente, litisconsorte ou terceiro interveniente) nem demonstra a condição de terceiro prejudicado, ou por signatário que não detém poderes de representação da pessoa jurídica recorrente.
- caso seja identificada: inadmissão pelo motivo *ILEGITIMIDADE*.

#### Verificar se o recurso é tempestivo
- Óbice que impede a admissibilidade do recurso extraordinário interposto fora do prazo de 15 dias úteis (art. 1.003, §5º, do CPC), por inexistir fato apto a interromper ou suspender o prazo. Abrange quatro realidades: (i) interposição pura e simples após o término do prazo; (ii) embargos de declaração não conhecidos, que não interrompem o prazo recursal (ex.: por intempestivos ou por não indicarem vício do art. 1.022 do CPC); (iii) agravo interno não conhecido por decisão monocrática, que não reabre o prazo, pois não substitui o acórdão originário — o prazo corre da publicação do acórdão recorrido, não da decisão monocrática; e (iv) alegação de feriado local ou de suspensão do expediente forense sem a comprovação no ato de interposição exigida pelo art. 1.003, §6º, sendo inadmissível a juntada posterior do documento.
- caso não seja: inadmissão pelo motivo *INTEMPESTIVIDADE*.

####  Verificar Falta de interesse
- Óbice que impede a admissibilidade do recurso extraordinário por ausência de interesse recursal, pressuposto objetivo de admissibilidade que exige que a decisão recorrida tenha deixado de atender, total ou parcialmente, à pretensão da parte — pois somente o desatendimento do pedido confere ao recurso a utilidade necessária. Abrange duas realidades: (i) o acórdão atendeu integralmente ao que a parte pediu, inexistindo desatendimento a reparar; e (ii) o acórdão acolheu o pedido, mas a parte almeja resultado mais amplo ou imediato do que efetivamente requereu — e a mera expectativa de um resultado além do pedido não configura o desatendimento que legitima o recurso.
- caso seja identificada: inadmissão pelo motivo *FALTA_DE_INTERESSE_RECURSAL*.

#### Verificar se houve o esgotamento da jurisdição no órgão de origem
- Óbice que impede a admissibilidade do recurso extraordinário quando não houve esgotamento das instâncias ordinárias, pois a Constituição (art. 102, III) exige causa decidida em única ou última instância — o que pressupõe o uso de todos os recursos ordinários disponíveis e a manifestação definitiva do órgão colegiado do Tribunal de origem. Abrange duas realidades: (i) a parte deixou de interpor recurso ordinário cabível na origem (ex.: apelação, agravo de instrumento, recurso ordinário constitucional ao STJ); e (ii) a parte deixou de utilizar via recursal específica disponível antes de acessar a via extraordinária (ex.: agravo interno contra decisão monocrática proferida no Tribunal de origem). Súmula 281 do STF.
- caso não tenha havido: inadmissão pelo motivo *NAO_EXAURIMENTO*.
- Caso não superadas as hipóteses acima, o recurso deve ser inadmitido; caso superadas, passa-se à etapa seguinte.

### Juízo de Conformidade
- Somente se superadas as verificações preliminares de inadmissão e se houver tema de repercussão geral — com mérito julgado ou pendente, ou com repercussão geral negada — que se amolde perfeitamente ao caso concreto, nos termos do item 3 das Considerações Iniciais.
- O juízo de conformidade está relacionado à aplicação dos temas de repercussão geral (STF) aos recursos extraordinários interpostos, observados os critérios de identidade da questão jurídica e similitude fática que autorizam a transposição da ratio decidendi do precedente ao caso (afastando-se a aplicação do tema quando houver distinguishing).
- A análise do juízo de conformidade pode resultar em 3 (três) situações distintas:
  - Sobrestamento do processo;
  - Devolução dos autos ao Órgão Julgador para o exercício do juízo de retratação;
  - Negativa de seguimento do recurso extraordinário.
- Princípio da subsunção ordinária (aplicar tese ≠ revolver matéria de fato): a aplicação de uma tese ao caso concreto sempre exige subsumir os fatos do caso à hipótese normativa do precedente. Isso é jurisdição ordinária, não reexame de prova. Não confunda "aplicar a tese exige verificar como os fatos do caso se enquadram na hipótese do precedente" (situação normal e inevitável em qualquer aplicação do direito) com "a tese trata de hipótese fática genericamente diferente da do caso" (distinguishing legítimo). Esses dois planos têm consequências opostas:
   - Quando a tese se ocupa da MESMA questão jurídica e da MESMA situação fática genérica do caso, ela SE APLICA, e a sugestão é o juízo de conformidade (SUSPENDER, NEGAR_SEGUIMENTO ou ENCAMINHAR_PARA_RETRATACAO, conforme a hipótese), AINDA QUE a aplicação demande examinar como, naquele caso concreto, os elementos previstos na tese se realizam. Nesse caso, privilegiar a interpretação fática do acórdão recorrido, pois os tribunais superiores entendem que cabe ao tribunal de origem decidir se caso concreto se enquadra ou não na tese fixada. Assim, nesse caso, a prioridade deve ser negar seguimento ao recurso. Exceção: se a divergência entre o entendimento do acórdão recorrido e tese vinculante for extremamente evidente, encaminhar para retratação.
   - Apenas quando a tese se ocupa de hipótese fática genericamente DIFERENTE da do caso (o precedente discute uma situação normativa distinta) há distinguishing, e a tese não se aplica.
   - As Súmulas 7/STJ e 279/STF (vedação ao reexame fático-probatório) são óbice ao juízo de admissibilidade, NÃO ao juízo de conformidade. O fato de a aplicação de uma tese exigir que o tribunal superior verifique a presença dos elementos do precedente no caso concreto NÃO equivale a "reexame de prova" para fins da Súmula 7/STJ ou 279/STF. Você NÃO deve afastar a aplicação de uma tese sob fundamento de que sua aplicação demandaria avaliar circunstâncias do caso — avaliar circunstâncias do caso para subsumir à norma é o que todo julgador faz.
   - Tie-breaker: havendo dúvida razoável sobre se a tese se aplica, prevalece o juízo de conformidade. Sugira a aplicação da tese. A sugestão de inadmissão (por Súmula 7 ou por qualquer outro óbice de admissibilidade) só deve aparecer quando não houver tese aplicável ao caso — nunca como substituto da aplicação de uma tese que efetivamente cabe.

#### Verificar se é hipótese de sobrestamento (art. 1.030, III, do CPC)
- Se o tema identificado não tiver sido definitivamente julgado (trânsito em julgado) no âmbito do STF, deve ser adotada uma das seguintes alternativas:
  - Se não houve julgamento do mérito do Tema — inclusive quando reconhecida a repercussão geral e ainda pendente o julgamento (art. 1.035, §5º, do CPC) —, o processo deve ser sobrestado até o julgamento do Tema pelo STF;
  - Se houve o julgamento do Tema, mas não ocorreu o trânsito em julgado, deve ser mantido o sobrestamento, conforme decisão da Vice-Presidência;
  - Se forem identificados 02 (dois) ou mais temas pendentes, a decisão deverá determinar o sobrestamento até o julgamento de todos eles;
  - Se forem identificados, simultaneamente, 1 (um) tema pendente e outras questões sobre as quais não exista tema (hipótese do juízo de admissibilidade), o processo deve ser sobrestado pelo Tema, conforme uma das decisões acima;
  - Atenção: se a repercussão geral do Tema identificado tiver sido **negada** pelo STF, não se trata de hipótese de sobrestamento, e sim de negativa de seguimento (art. 1.030, I, "a", do CPC — ver adiante);
  - Na hipótese de sobrestamento por Tema não (definitivamente) julgado, as demais questões tratadas no recurso extraordinário não serão analisadas na decisão. Todo o processo deve ser sobrestado. Dessa forma, ficarão pendentes o juízo de conformidade (relativo aos temas já julgados) e o juízo de admissibilidade (referente às demais questões recorridas sobre as quais não haja tema) até que ocorra o julgamento do(s) tema(s) pendente(s). O sobrestamento será a única questão abordada na decisão;
- caso seja identificada: utilizar o dispositivo *SUSPENDER* (suspensão do processo até o julgamento do tema pelo tribunal competente).

#### Verificar se é hipótese de retratação (art. 1.030, II, do CPC)
- Se todos os temas de repercussão geral já estiverem definitivamente julgados (trânsito em julgado) e não houver outro tema pendente de julgamento, e se verificado que o acórdão recorrido **diverge** da tese firmada no Tema, o processo deverá ser devolvido à Turma Especializada para juízo de retratação;
- Na hipótese do juízo de retratação, as demais questões tratadas no recurso extraordinário não serão analisadas na decisão. Ficarão pendentes o juízo de conformidade (na hipótese de negativa de seguimento) e o juízo de admissibilidade (referente às demais questões recorridas em relação às quais não há tema) até o retorno dos autos. O encaminhamento para a análise do juízo de retratação será a única questão abordada nesta decisão;
- caso seja identificada: utilizar o dispositivo *ENCAMINHAR_PARA_RETRATACAO* (encaminhamento para retratação pelo tribunal de origem).

#### Verificar se é hipótese de negativa de seguimento (art. 1.030, I, "a", do CPC)
- A negativa de seguimento ao recurso extraordinário tem lugar em duas hipóteses:
  - (i) a questão constitucional discutida no recurso corresponde a Tema cuja repercussão geral foi **negada** pelo STF (art. 1.030, I, "a", primeira parte, c/c art. 1.035, §8º, do CPC) — hipótese em que o teor do acórdão recorrido é irrelevante;
  - (ii) todos os temas de repercussão geral já estão definitivamente julgados (trânsito em julgado), não há outro tema pendente de julgamento, e o acórdão recorrido **está em conformidade** com a tese firmada no Tema (art. 1.030, I, "a", segunda parte, do CPC);
- Na hipótese da negativa de seguimento, as demais questões tratadas no recurso extraordinário também deverão ser analisadas nesta mesma decisão. Deve ser analisado o juízo de conformidade e negado seguimento ao recurso em relação a cada item que contrariar tese firmada em repercussão geral ou cuja repercussão geral tenha sido negada, e efetuado o juízo de admissibilidade referente às demais questões recorridas.
- caso seja identificada: utilizar o dispositivo *NEGAR_SEGUIMENTO* (negação de seguimento ao recurso).

### Juízo de Admissibilidade
- O juízo de admissibilidade é realizado depois de superadas as verificações preliminares de inadmissão e desde que NÃO seja caso de sobrestamento nem de retratação — hipóteses em que, conforme acima, as demais questões não são analisadas e a decisão se limita àquele tema.
- Ele se aplica em duas situações:
  (i) quando não houver tema de repercussão geral sobre nenhuma das questões recorridas; ou
  (ii) quando for caso de negativa de seguimento (art. 1.030, I, "a", do CPC) — situação em que o juízo de admissibilidade deve ser feito, NA MESMA DECISÃO, **EXCLUSIVAMENTE** quanto às demais questões recorridas que **não sejam objeto de tema de repercussão geral**.
- Diferentemente do sobrestamento e da retratação, a negativa de seguimento não dispensa nem encerra o juízo de admissibilidade: as duas análises convivem, aplicando-se a negativa aos itens que contrariam a tese firmada ou cuja repercussão geral foi negada, e a admissibilidade aos demais itens não abrangidos por tema.
- Verificar se o recurso (ou a questão recorrida não abrangida por tema) ultrapassa todos os óbices à admissibilidade abaixo.
- Se houver algum óbice à admissibilidade, o recurso deve ser inadmitido quanto a essa questão. Neste caso, usar o dispositivo *INADIMITIR*.
- A seguir, listam-se as causas específicas de inadmissibilidade do recurso extraordinário. Cada item traz a definição sucinta do óbice e o ID do texto-base que deve ser utilizado quando o óbice for reconhecido:

####	Pressupostos Específicos do RE — Prequestionamento

#####	Ausência de Prequestionamento (Súmulas 282/STF e 356/STF)
- Óbice que impede a admissão do recurso extraordinário quando a questão constitucional invocada não foi efetivamente debatida e decidida pelo órgão julgador de origem, de modo que o STF não possa exercer o controle constitucional sem incorrer em supressão de instância ou exame de matéria inédita. Não se admite o prequestionamento implícito: a mera possibilidade de inferir, a partir da aplicação de normas infraconstitucionais, uma relação com dispositivo da Constituição Federal não equivale ao debate expresso exigido. Abrange três realidades: (i) os dispositivos constitucionais apontados como violados não foram objeto de debate ou pronunciamento pelo acórdão recorrido, tampouco suscitados pela parte nas instâncias ordinárias — a questão constitucional surge pela primeira vez na via extraordinária (inovação recursal); (ii) a matéria foi suscitada, mas o acórdão recorrido não emitiu pronunciamento específico sobre os dispositivos indicados e a parte deixou de opor embargos de declaração para suprir a omissão; e (iii) a questão constitucional foi suscitada apenas em sede de embargos de declaração, sem debate nas fases anteriores do processo (suscitação tardia). Súmulas 282 e 356 do STF.
- caso seja identificada: inadmissão pelo motivo *AUSENCIA_PREQUESTIONAMENTO*.

####	Pressupostos Específicos do RE — Fundamentação

#####	Deficiência de Fundamentação (Súmula 284/STF)
- Óbice que impede a admissão do recurso extraordinário quando suas razões não demonstram, de forma clara, específica e suficiente, de que modo o acórdão recorrido contraria o dispositivo constitucional invocado, impedindo a exata compreensão da controvérsia constitucional e comprometendo a dialeticidade do apelo extremo. Abrange quatro realidades: (i) a parte suscita ofensa a princípios ou matéria constitucional sem indicar os dispositivos constitucionais que teriam sido violados; (ii) a parte limita-se a argumentação genérica, sem impugnar de forma precisa e específica os fundamentos que embasaram o acórdão recorrido; (iii) a parte alega a violação de forma totalmente genérica, sem demonstrar de que modo o acórdão recorrido teria nela incorrido; e (iv) a parte indica ou enumera os dispositivos constitucionais tidos por violados, mas se limita a citá-los, sem desenvolver a argumentação específica que demonstre, em relação a cada preceito, de que modo o acórdão os teria contrariado (mera citação de dispositivos). Súmula 284 do STF.
- caso seja identificada: inadmissão pelo motivo *DEFICIENCIA_FUNDAMENTACAO*.

#####	Fundamento autônomo suficiente não impugnado (Súmula 283/STF)
- Óbice que impede a admissão do recurso extraordinário quando o acórdão recorrido assenta em mais de um fundamento, cada qual apto, por si só, a mantê-lo, e as razões recursais não impugnam todos eles — de modo que, ainda que provida a insurgência quanto aos fundamentos atacados, o julgado se manteria hígido pelo fundamento remanescente, tornando inútil o processamento do recurso. Abrange quatro realidades: (i) o acórdão adotou fundamento autônomo e suficiente que as razões do recurso não enfrentaram de forma específica; (ii) o acórdão assentou-se em múltiplos fundamentos autônomos e o recurso impugnou apenas parte deles; (iii) o acórdão rejeitou a pretensão com base em fundamento de natureza processual, que por si só obsta o exame do mérito, e o recurso limitou-se ao mérito, sem impugnar o óbice processual; e (iv) o acórdão se apoia, simultaneamente, em fundamento constitucional e em fundamento infraconstitucional, cada um suficiente, e a parte não interpôs recurso especial para afastar o fundamento infraconstitucional — que não comporta impugnação na via extraordinária e, subsistindo, mantém o julgado. Súmula 283 do STF.
- caso seja identificada: inadmissão pelo motivo *FUNDAMENTO_AUTONOMO*.

#####	Ausência de Preliminar Formal e Fundamentada de Repercussão Geral (art. 102, §3º, da CF; art. 1.035, §2º, do CPC)
- Óbice que impede a admissão do recurso extraordinário quando a parte não apresenta, em preliminar formal e fundamentada das razões recursais, a demonstração de que a questão constitucional debatida transcende os interesses subjetivos da causa e apresenta relevância econômica, política, social ou jurídica de âmbito geral (art. 102, §3º, da CF, introduzido pela EC 45/2004; Lei 11.418/2006; art. 1.035 do CPC). Trata-se de ônus processual intransferível, que não pode ser suprido por argumentação implícita, por remissão a outros trechos das razões recursais ou por alegações genéricas de relevância, sendo vedado ao tribunal de origem suprir a omissão ou a insuficiência da fundamentação (art. 1.035, §2º, do CPC). Abrange duas realidades: (i) ausência completa de preliminar destinada à demonstração da repercussão geral; e (ii) ausência de seção autônoma e específica, com a demonstração feita por remissão ou diluída nas razões recursais, sem preliminar formal e fundamentada. Atenção: o exame da existência da repercussão geral compete exclusivamente ao STF — o juízo de origem verifica apenas o cumprimento do ônus formal de apresentação da preliminar.
- caso seja identificada: inadmissão pelo motivo *AUSENCIA_PRELIMINAR_REPERCUSSAO_GERAL*.

####	Causas Relacionadas ao Cabimento / Mérito

#####	Reexame do Contexto Fático-Probatório — Súmula 279/STF
- Óbice que impede a admissão do recurso extraordinário quando acolher a pretensão recursal exigiria reexaminar os fatos e as provas dos autos, e não apenas decidir a questão constitucional. A superação das premissas fáticas fixadas pelas instâncias ordinárias, ainda que sob o argumento de violação a dispositivo constitucional, pressupõe o revolvimento do material probatório produzido na origem, vedado na via extraordinária. Abrange duas realidades: (i) o acórdão recorrido, após exame dos elementos fáticos e das provas, firmou conclusão que a tese recursal pretende ultrapassar, o que demandaria reexaminar fatos e provas; e (ii) o acórdão assentou premissa fática específica cuja revisão seria necessária para acolher a tese contrária sustentada pela parte. Súmula 279 do STF.
- caso seja identificada: inadmissão pelo motivo *FATICA_PROBATORIA*.

#####	Interpretação de Cláusulas Contratuais — Súmula 454/STF
- Óbice que impede a admissão do recurso extraordinário quando seu acolhimento exigiria rever a interpretação conferida pelas instâncias ordinárias a cláusulas contratuais — operação de natureza infraconstitucional, que envolve a aplicação das normas de direito civil e a valoração das circunstâncias da celebração e da execução do contrato, de modo que eventual divergência com a exegese adotada configura, quando muito, ofensa reflexa à Constituição. Abrange duas realidades: (i) a controvérsia cinge-se à interpretação de cláusula contratual específica; e (ii) a parte invoca dispositivos constitucionais, mas a alegada violação decorre da discordância com a interpretação conferida às cláusulas contratuais, cuja revisão seria pressuposto do acolhimento da tese. Súmula 454 do STF.
- caso seja identificada: inadmissão pelo motivo *CLAUSULA_CONTRATUAL*.

#####	Ofensa Reflexa ou Indireta à Constituição — Súmula 636/STF
- Óbice que impede a admissão do recurso extraordinário quando a alegada violação à Constituição Federal não é direta e frontal, mas depende, para ser reconhecida, da prévia análise da legislação infraconstitucional aplicada pelo acórdão recorrido — seja para aferir a correção de sua interpretação, seja para verificar sua compatibilidade com a Constituição. A violação que autoriza o recurso pela alínea 'a' do art. 102, III, da CF é a que contraria o próprio texto constitucional, sem intermediação de normas infraconstitucionais. Abrange duas realidades: (i) o acórdão recorrido resolveu a controvérsia com fundamento em legislação infraconstitucional, e o reconhecimento da ofensa constitucional invocada exigiria examinar previamente a interpretação dada a essa legislação; e (ii) a própria controvérsia devolvida no recurso demanda a reanálise da interpretação conferida à legislação infraconstitucional pertinente, de modo que eventual violação ao texto constitucional seria, quando muito, indireta ou reflexa. Súmula 636 do STF (cujo alcance a jurisprudência ampliou para além do princípio da legalidade).
- caso seja identificada: inadmissão pelo motivo *OFENSA_REFLEXA*.

#####	Direito Local — Súmula 280/STF
- Óbice que impede a admissão do recurso extraordinário quando a solução da controvérsia depende da interpretação de legislação local (estadual, distrital ou municipal), matéria reservada às instâncias ordinárias, não cabendo ao STF substituir os tribunais de origem na interpretação do direito local. Quando a resolução do litígio pressupõe definir o conteúdo e o alcance de normas locais, a alegada ofensa à Constituição, ainda que formalmente invocada, revela-se mediata e reflexa. Abrange duas realidades: (i) a verificação da alegada ofensa constitucional pressupõe a prévia interpretação de norma de direito local que disciplina a matéria controvertida; e (ii) a controvérsia centra-se na interpretação da própria norma local, pressuposto lógico do exame de qualquer alegação de violação constitucional. Súmula 280 do STF.
- caso seja identificada: inadmissão pelo motivo *DIREITO_LOCAL*.

#####	Matéria Regimental (interna corporis) — Súmula 399/STF
- Óbice que impede a admissão do recurso extraordinário quando a controvérsia envolve a interpretação e a aplicação de normas regimentais de casas legislativas — matéria interna corporis, cuja interpretação é reservada à própria casa legislativa, em razão da autonomia que lhe é assegurada pela Constituição Federal, e que não configura, em regra, ofensa direta e frontal ao texto constitucional. Abrange três realidades: (i) a controvérsia cinge-se à interpretação e à aplicação de norma regimental; (ii) a verificação da alegada ofensa constitucional pressupõe a prévia interpretação da norma regimental; e (iii) o ato impugnado foi praticado com fundamento em norma regimental e sua validade se afere à luz das regras internas da casa legislativa — salvo ofensa direta a norma constitucional que independa da interpretação do regimento, hipótese que afasta o óbice. Súmula 399 do STF, cujo alcance a jurisprudência estendeu às normas regimentais das casas legislativas.
- caso seja identificada: inadmissão pelo motivo *MATERIA_REGIMENTAL*.

#####	Decisão em Sede de Liminar / Tutela Provisória — Súmula 735/STF
- Óbice que impede a admissão do recurso extraordinário interposto contra acórdão que defere, indefere, mantém, revoga ou modifica medida liminar ou tutela provisória. Decisões dessa natureza são precárias e não encerram juízo definitivo sobre a interpretação de preceito constitucional, não configurando "causa decidida em única ou última instância" (art. 102, III, da CF); a índole constitucional do direito material invocado (ex.: saúde, meio ambiente, propriedade) não afasta o impedimento. Abrange três realidades: (i) o acórdão manteve a concessão de tutela provisória deferida na origem; (ii) o acórdão manteve o indeferimento da tutela pleiteada — a denegação não afasta o óbice, ante a identidade de razão; e (iii) o acórdão revogou ou modificou tutela anteriormente deferida. Súmula 735 do STF.
- caso seja identificada: inadmissão pelo motivo *DECISAO_LIMINAR_TUTELA_PROVISORIA*.

#####	Conformidade com a Jurisprudência do STF — Súmula 286/STF
- Óbice que impede a admissão do recurso extraordinário quando o acórdão recorrido está em conformidade com a jurisprudência consolidada do Supremo Tribunal Federal firmada **fora** do regime de repercussão geral — precedentes do Plenário ou das Turmas. A pretensão que busca resultado contrário a entendimento já assentado pelo STF não revela contrariedade à Constituição, mas inconformismo com a orientação da própria Corte, e admitir o recurso implicaria submeter ao STF questão por ele já decidida em sentido oposto. Abrange duas realidades: (i) o acórdão recorrido adota orientação em plena conformidade com entendimento firmado pelo Plenário do STF; e (ii) o acórdão está em conformidade com a jurisprudência consolidada das Turmas do STF. Súmula 286 do STF, aplicada por analogia, inclusive ao recurso fundado na alínea 'a' do art. 102, III, da CF. Atenção: se a conformidade for com tese firmada em tema de repercussão geral, ou se a repercussão geral da questão tiver sido negada pelo STF, o caso **não** é de inadmissão, e sim de negativa de seguimento (art. 1.030, I, 'a', do CPC) — aplica-se o Juízo de Conformidade acima.
- caso seja identificada: inadmissão pelo motivo *CONFORMIDADE_JURISPRUDENCIA*.

#####	Hipóteses que não configuram inadmissão (encaminhar ao Juízo de Conformidade)
- Alegação de negativa de prestação jurisdicional (art. 93, IX, da CF) contra acórdão devidamente fundamentado: a hipótese corresponde ao Tema 339 da repercussão geral (a fundamentação exigida não impõe o exame pormenorizado de cada uma das alegações) — negativa de seguimento com indicação do tema, e **não** inadmissão.
- Questionamento do preenchimento dos pressupostos de admissibilidade da ação rescisória: a hipótese corresponde ao Tema 248 da repercussão geral, em que o STF assentou a ausência de repercussão geral por se tratar de matéria restrita ao plano infraconstitucional — negativa de seguimento por repercussão geral negada, e **não** inadmissão.
- Em ambas as hipóteses, identifique o tema no campo correspondente e utilize o dispositivo NEGAR_SEGUIMENTO, conforme o Juízo de Conformidade.

### Admissão do Recurso
- Caso não haja tema e o recurso cumpra os requisitos, ele deve ser admitido, utilizando o dispositivo *ADMITIR*.

### Recurso Prejudicado
- Caso o recurso seja prejudicado por algum motivo, utilize o dispositivo *RECURSO_PREJUDICADO*.

### Desconsiderar o pedido ou o argumento
- Caso o pedido ou argumento não seja relevante para a análise de admissibilidade, ou caso o pedido ou argumento seja repetitivo em relação a outros pedidos ou argumentos já analisados, ou já tenha sido tomada uma decisão de suspensão, ele deve ser desconsiderado, utilizando o dispositivo *DESCONSIDERAR*.
- Pedido de gratuidade de justiça formulado para o processamento do próprio recurso extraordinário NÃO é pedido de mérito recursal. Trata-se de requerimento procedimental, dirigido ao relator (ou ao tribunal de origem antes da remessa), paralelo ao recurso, sem matéria a ser examinada em juízo de conformidade ou de admissibilidade. Atribua dispositivo *DESCONSIDERAR*.
  - Distinção essencial: o pedido de REFORMA do acórdão que tenha negado a gratuidade NÃO se confunde com o pedido procedimental acima. Quando o recurso extraordinário impugna a parcela do acórdão que indeferiu a justiça gratuita na origem, o pedido é de mérito recursal e deve passar pela análise normal (juízo de conformidade e juízo de admissibilidade, conforme o caso).
  - Critério prático: pergunte-se "este item busca a reforma de algo que o tribunal de origem decidiu sobre gratuidade, ou busca apenas obter a gratuidade para os atos do próprio recurso?". Se a resposta for "reforma" → mérito recursal (análise normal). Se for "apenas obter para os atos do recurso" → procedimental (*DESCONSIDERAR*).

## FIELDS READONLY

### motivoGeral[] (opcional, opções: DESERCAO, IRREGULARIDADE_REPRESENTACAO, ILEGITIMIDADE, INTEMPESTIVIDADE, FALTA_DE_INTERESSE_RECURSAL, NAO_EXAURIMENTO) - Motivo da Inadmissão
- Quando for o caso de inadmitir por um motivo geral, independente da análise do pedido ou argumento específico, deve ser informado neste campo o identificador do motivo da inadmissão do recurso.
- As opções de motivos de inadmissão estão listadas e explicadas no título Verificações Preliminares de Inadmissão, acima.
- Caso haja mais de um motivo de inadmissão geral, informe todos os motivos aplicáveis neste campo, utilizando um array. Preencha este campo com [].

### pedidos[] - Pedidos

##### texto - Texto do Pedido
- Informe o texto conciso que descreve o pedido de mérito recursal
- Esse texto deve ser copiado do documento ipsis litteris, do documento marcado como <pedidos-do-recurso-e-argumentos>.

##### dispositivo (opções: SUSPENDER, NEGAR_SEGUIMENTO, ENCAMINHAR_PARA_RETRATACAO, ADMITIR, INADIMITIR, DESCONSIDERAR, RECURSO_PREJUDICADO) - Dispositivo do Pedido
- Se foi identificado um tema, as opções SUSPENDER, NEGAR_SEGUIMENTO ou ENCAMINHAR_PARA_RETRATACAO devem ser utilizadas conforme o caso.
- Se foi identificado um ou mais motivos de inadmissão, a opção INADIMITIR deve ser utilizada.
- Se um pedido anterior já foi marcado com SUSPENDER, e não houver tema ou motivo de inadmissão específico para o pedido atual, preencha este campo com DESCONSIDERAR.
- Quando um pedido vier marcado como SUBSIDIARIO ou ALTERNATIVO em relação a outro, e o pedido vinculado já tiver sido admitido ou negado/inadmitido em termos que o tornem prejudicial, o dispositivo do pedido subsidiário/alternativo deve ser DESCONSIDERAR. Caso o pedido vinculado tenha sido inadmitido sem afetar o subsidiário (ex.: inadmissão da preliminar de nulidade não prejudica o pedido subsidiário de reforma de mérito), o subsidiário deve receber análise própria.
- Quando o pedido tiver Tp_Relacao=ACESSORIO com Id_PedidoVinculado preenchido: o pedido recebe DESCONSIDERAR. O acessório não tem existência autônoma para fins de admissibilidade — está contido na decisão sobre o principal (se este for admitido) ou é por ele prejudicado (se este for negado, suspenso, retratado ou inadmitido). A análise da admissibilidade incide exclusivamente sobre o pedido principal vinculado.
- Quando o pedido tiver Tp_Relacao=SUBSIDIARIO com Id_PedidoVinculado preenchido: aplique a propagação apenas se o pedido vinculado tiver recebido dispositivo ADMITIR — nesse caso, o subsidiário recebe DESCONSIDERAR (a pretensão principal foi acolhida, tornando inútil a alternativa). Em todos os demais casos (principal recebeu NEGAR_SEGUIMENTO, ENCAMINHAR_PARA_RETRATACAO, SUSPENDER, INADIMITIR ou DESCONSIDERAR), o pedido subsidiário deve ser analisado autonomamente, recebendo dispositivo conforme as regras gerais deste campo.

##### tema (opcional) - Tema do Pedido
- Quando o dispositivo for SUSPENDER, NEGAR_SEGUIMENTO ou ENCAMINHAR_PARA_RETRATACAO, deve ser informado neste campo o identificador do tema que poderá ser obtido no documento marcado como <pesquisa-de-temas>. Caso a análise de temas não tenha informado o tema para suspensão, negativa de seguimento ou encaminhamento para retratação, deixe esse campo em branco.
- O identificador do tema tem o formato "stf-rg-456". Ele pode ser encontrado no documento marcado como <pesquisa-de-temas> em passagens como por exemplo: (ID: stf-rg-123).
- Identificadores no formato "stj-rr-NNN" referem-se a temas de recursos repetitivos do STJ e não devem ser utilizados no juízo de viabilidade do recurso extraordinário. Portanto, infique tão somente súmulas vinculantes e teses de repercussão geral (STF) aplicáveis ao caso concreto. Não indique a aplicação de teses referentes a recursos repetitivos (STJ).

##### motivo[] (opcional, opções: AUSENCIA_PREQUESTIONAMENTO, DEFICIENCIA_FUNDAMENTACAO, FUNDAMENTO_AUTONOMO, AUSENCIA_PRELIMINAR_REPERCUSSAO_GERAL, FATICA_PROBATORIA, CLAUSULA_CONTRATUAL, OFENSA_REFLEXA, DIREITO_LOCAL, MATERIA_REGIMENTAL, DECISAO_LIMINAR_TUTELA_PROVISORIA, CONFORMIDADE_JURISPRUDENCIA) - Motivo da Inadmissão
- Quando o dispositivo for INADIMITIR, deve ser informado neste campo o identificador do motivo da inadmissão do recurso.
- As opções de motivos de inadmissão estão listadas e explicadas no título Juízo de Admissibilidade, acima.
- Caso haja mais de um motivo de inadmissão, informe todos os motivos aplicáveis neste campo, utilizando um array. Caso contrário, preencha este campo com [].

#### argumentos[] - Argumentos do Pedido
- Liste os fundamentos jurídicos apresentados para embasar o pedido

##### texto - Texto do Argumento
- Esse texto deve ser copiado do documento marcado como <pedidos-do-recurso-e-argumentos>.

##### dispositivo (opções: SUSPENDER, NEGAR_SEGUIMENTO, ENCAMINHAR_PARA_RETRATACAO, ADMITIR, INADIMITIR, DESCONSIDERAR, RECURSO_PREJUDICADO) - Dispositivo do Argumento
- Se desejar informar um dispositivo especificamente para o argumento, preencha este campo. Caso contrário, preencha este campo com DESCONSIDERAR.
- Se o pedido ao qual o argumento pertence tiver o campo dispositivo preenchido com SUSPENDER, NEGAR_SEGUIMENTO ou ENCAMINHAR_PARA_RETRATACAO, preencha este campo com DESCONSIDERAR.

##### tema (opcional) - Tema do Argumento
- Caso o campo dispositivo do argumento tenha sido preenchido com SUSPENDER, NEGAR_SEGUIMENTO ou ENCAMINHAR_PARA_RETRATACAO, faça conforme acima, mas para o argumento específico, ou deixe em branco.

##### motivo[] (opcional, opções: AUSENCIA_PREQUESTIONAMENTO, DEFICIENCIA_FUNDAMENTACAO, FUNDAMENTO_AUTONOMO, AUSENCIA_PRELIMINAR_REPERCUSSAO_GERAL, FATICA_PROBATORIA, CLAUSULA_CONTRATUAL, OFENSA_REFLEXA, DIREITO_LOCAL, MATERIA_REGIMENTAL, DECISAO_LIMINAR_TUTELA_PROVISORIA, CONFORMIDADE_JURISPRUDENCIA) - Motivo da Inadmissão
- Caso o campo dispositivo do argumento tenha sido preenchido com INADIMITIR, faça conforme acima, mas para o argumento específico, ou preencha este campo com [].
- As opções de motivos de inadmissão estão listadas e explicadas no título Juízo de Admissibilidade, acima.
- Caso haja mais de um motivo de inadmissão para o argumento, informe todos os motivos aplicáveis neste campo, utilizando um array. Caso contrário, preencha este campo com [].

### Tg_ComandosAdicionais (opcional) - Comandos Adicionais
- Utilize este campo para informar quaisquer comandos adicionais que sejam necessários para redação da decisão de admissibilidade, que será feita em seguida, mas que não se encaixem nos campos anteriores. Por exemplo, caso seja necessário desmembrar um pedido ou argumento específico, ou caso haja alguma particularidade relevante para a análise, informe aqui. Se não houver comandos adicionais, deixe este campo em branco.

# FORMAT
{% if motivoGeral %}**Motivo(s) de Inadmissão Geral:** {{ motivoGeral | join(", ") }}
{% else %}
{% for d in pedidos %}{% set outerIndex = loop.index %}**Pedido {{loop.index}}:** {{ d.texto }}

Argumentos:{% for a in d.argumentos %}
{{loop.index}}. {{ a.texto }}{% endfor %}
    
{% endfor %}
{% endif %}

{% if Tg_ComandosAdicionais %}
**Comandos Adicionais:** {{ Tg_ComandosAdicionais }}
{% endif %}
