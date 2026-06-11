---
uuid: 89dfafb9-0961-415d-871a-62a52351a75c
name: Juízo de Viabilidade de Recurso Especial
description: Realize o juízo completo de viabilidade do recurso especial com análise sequencial de verificação preliminar, conformidade e admissibilidade.
sort: 3
share: oculto
piece_strategy: viabilidade-recurso-especial
---

# PROMPT

Leia atentamente o conteúdo das peças processuais fornecidas abaixo.

{{textos}}

Você leu diversos documentos relacionados a Recurso Especial em processo judicial.

Você leu, também, um documento marcado como <pedidos-do-recurso-e-argumentos> que contém os pedidos formulados no recurso judicial e os argumentos apresentados para embasar cada pedido. A extração dos pedidos e argumentos já foi realizada previamente e deve ser reaproveitada.

Você leu um documento marcado como <pesquisa-de-temas> que contém a análise de viabilidade jurídica do recurso com base em teses e súmulas vinculantes. Se você optar por utilizar essa análise, deverá transcrever os dados dessa análise nos campos apropriados da resposta. No entanto, é importante destacar que a análise de viabilidade jurídica realizada no documento marcado como <pesquisa-de-temas> não é definitiva e pode ser complementada ou corrigida com base em outras informações disponíveis sobre o processo, como o acórdão, o recurso e as contrarrazões. Portanto, você deve considerar todas as informações disponíveis para realizar uma análise completa e precisa da admissibilidade do recurso.

## Considerações Iniciais

1. Juízo de Viabilidade do REsp (Recurso Especial)

O juízo de viabilidade do Recurso Especial leva em consideração uma série de análises efetuadas pela Vice-Presidência do Tribunal (juízo de conformidade e juízo de admissibilidade).
- Essas análises seguem, em regra, uma ordem sequencial: cada etapa só é examinada depois de vencida a anterior;
- O juízo de conformidade tem primazia sobre o juízo de admissibilidade — regra;
- Há, contudo, determinados vícios que autorizam afastar o juízo de conformidade para o exercício do juízo de admissibilidade (hipóteses de inadmissão);
- A ordem sequencial comporta uma exceção relevante: nem toda hipótese de conformidade encerra a análise. O sobrestamento e a retratação são terminais — incidindo, a decisão limita-se ao tema e as demais questões não são analisadas. Já a negativa de seguimento convive, na mesma decisão, com o juízo de admissibilidade das questões que não sejam objeto de tema (decisão mista).

2. Óbices iniciais à admissibilidade (Manual STJ, p. 26-27)

Há hipóteses que podem levar à inadmissibilidade do recurso (juízo de admissibilidade) e que devem ser analisadas antes mesmo da conformidade. São seis verificações iniciais principais:
2.1. Verificar se houve preparo;
2.2. Verificar se o recurso é tempestivo (art. 1.003, §5º, do CPC).
2.3. Verificar se houve o esgotamento da jurisdição no órgão de origem;
2.4. Verificar se a representação processual está regular;
2.5. Verificar se existe interesse recursal;
2.6. Verificar se o recorrente possui legitimidade recursal.
Caso não superada qualquer dessas hipóteses acima, o recurso deve ser inadmitido


3. Juízo de Conformidade

Verificado o preparo, a tempestividade, o esgotamento da instância, a regularidade da representação processual, o interesse recursal e a legitimidade recursal, passa-se ao juízo de conformidade: é necessário verificar se há (ou não) um Tema Repetitivo (STJ) ou de Repercussão Geral (STF) que se amolde perfeitamente ao caso concreto. A mera existência de um Tema sobre matéria correlata não basta. O Tema só será aplicado quando houver (i) identidade da questão jurídica entre o recurso e o Tema e (ii) similitude fática suficiente para que a ratio decidendi do precedente seja transponível ao caso. Havendo elementos distintivos relevantes entre a controvérsia recorrida e o paradigma (distinguishing), o Tema não se aplica e a análise prossegue como se inexistisse. Confirmada a aplicação do Tema, deve ser analisada a conformidade, na seguinte sequência:
3.1. Verificar se é hipótese de sobrestamento (art. 1.030, III, do CPC);
3.2. Verificar se é hipótese de retratação (art. 1.030, II, do CPC);
3.3. Verificar se é hipótese de negativa de seguimento (art. 1.030, I, do CPC).

4. Juízo de Admissibilidade

Passa-se ao juízo de admissibilidade quando: (i) não houver tema de repercussão geral ou de recurso repetitivo sobre as questões recorridas; ou (ii) for caso de negativa de seguimento, hipótese em que a admissibilidade é examinada, na mesma decisão, quanto às demais questões não abrangidas por tema.
Não se chega a esta etapa nas hipóteses de sobrestamento e de retratação, que encerram a decisão.
Para que uma questão seja admitida, é necessário que não haja nenhum óbice à sua admissão.

5. Admissão

Uma questão recorrida será admitida quando não houver, sobre ela, tema que imponha sobrestamento, retratação ou negativa de seguimento, nem qualquer hipótese de inadmissão.
O recurso pode ser admitido integralmente — quando todas as questões superam os óbices — ou apenas em parte, quando algumas questões são admitidas e outras recebem negativa de seguimento ou inadmissão (decisão mista).

## Roteiro de Verificação

Utilize a seguinte sequência de verificações para analisar a admissibilidade do recurso especial:

### Verificações Preliminares de Inadmissão
- Se houver algum motivo de inadmissão geral, independente da análise do pedido ou argumento específico, o recurso deve ser inadmitido.
- Neste caso, informe o motivo da inadmissão no campo "motivoGeral" do JSON.
- Este campo é um array, pois pode haver mais de um motivo de inadmissão geral.
- As opções de motivos de inadmissão geral estão listadas abaixo.

#### Verificar se houve preparo
- Óbice que impede a admissibilidade do recurso especial quando o preparo não foi regularizado, faltando requisito essencial de admissibilidade. Abrange quatro realidades: (i) ausência total de preparo — a parte não comprovou o recolhimento no ato de interposição e, intimada para recolher em dobro (art. 1.007, §4º, do CPC), deixou o prazo decorrer in albis; (ii) preparo insuficiente — recolheu valor a menor e, intimada para complementar (art. 1.007, §2º), não o fez no prazo de 5 dias; (iii) gratuidade requerida após a interposição — o pedido de justiça gratuita foi formulado fora do ato recursal, e sua concessão não retroage para afastar o recolhimento em dobro; e (iv) gratuidade indeferida — o pedido foi negado por falta de demonstração de hipossuficiência (art. 99, §2º, do CPC) e o prazo concedido para regularizar o preparo decorreu in albis. Súmula 187 do STJ.
- caso não haja: inadmissão pelo motivo *DESERCAO*.

####  Verificar Irregularidade da representação processual
- Óbice que impede a admissibilidade do recurso especial quando a representação processual da parte recorrente apresenta vício não sanado, faltando pressuposto processual que deve subsistir durante todo o trâmite, inclusive na fase recursal. Configura-se quando, identificado o vício — por exemplo, renúncia do advogado subscritor após a interposição, ausência de procuração válida nos autos em nome do signatário, ou procuração cujos poderes não abrangem a prática de atos em sede recursal especial —, a parte, regularmente intimada para saná-lo no prazo de 5 dias (art. 932, parágrafo único, do CPC), deixa de fazê-lo. Art. 76, §2º, I, do CPC.
- caso seja identificada: inadmissão pelo motivo *IRREGULARIDADE_REPRESENTACAO*.

####  Verificar Ilegitimidade
- Óbice que impede a admissibilidade do recurso especial por ausência de legitimidade recursal, pressuposto subjetivo de admissibilidade (art. 996 do CPC), que só autoriza a recorrer as partes, o Ministério Público e o terceiro prejudicado. Configura-se quando, por exemplo, o recurso é interposto por quem não figurou como parte no processo de origem, por quem não integrou a relação processual nas instâncias ordinárias (sem ter sido admitido como assistente, litisconsorte ou terceiro interveniente) nem demonstra a condição de terceiro prejudicado, ou por signatário que não detém poderes de representação da pessoa jurídica recorrente.
- caso seja identificada: inadmissão pelo motivo *ILEGITIMIDADE*.

#### Verificar se o recurso é tempestivo
- Óbice que impede a admissibilidade do recurso especial interposto fora do prazo de 15 dias úteis (art. 1.003, §5º, do CPC), por inexistir fato apto a interromper ou suspender o prazo. Abrange quatro realidades: (i) interposição pura e simples após o término do prazo; (ii) embargos de declaração não conhecidos, que não interrompem o prazo recursal (ex.: por intempestivos ou por não indicarem vício do art. 1.022 do CPC); (iii) agravo interno não conhecido por decisão monocrática, que não reabre o prazo, pois não substitui o acórdão originário — o prazo corre da publicação do acórdão recorrido, não da decisão monocrática; e (iv) alegação de feriado local ou de suspensão do expediente forense sem a comprovação no ato de interposição exigida pelo art. 1.003, §6º, sendo inadmissível a juntada posterior do documento.
- caso não seja: inadmissão pelo motivo *INTEMPESTIVIDADE*.

####  Verificar Falta de interesse
- Óbice que impede a admissibilidade do recurso especial por ausência de interesse recursal, pressuposto objetivo de admissibilidade que exige que a decisão recorrida tenha deixado de atender, total ou parcialmente, à pretensão da parte — pois somente o desatendimento do pedido confere ao recurso a utilidade necessária. Abrange duas realidades: (i) o acórdão atendeu integralmente ao que a parte pediu, inexistindo desatendimento a reparar; e (ii) o acórdão acolheu o pedido, mas a parte almeja resultado mais amplo ou imediato do que efetivamente requereu — e a mera expectativa de um resultado além do pedido não configura o desatendimento que legitima o recurso.
- caso seja identificada: inadmissão pelo motivo *FALTA_DE_INTERESSE_RECURSAL*.

#### Verificar se houve o esgotamento da jurisdição no órgão de origem
- Óbice que impede a admissibilidade do recurso especial quando não houve esgotamento das instâncias ordinárias, pois a Constituição (art. 105, III) exige causa decidida em única ou última instância — o que pressupõe o uso de todos os recursos ordinários disponíveis e a manifestação definitiva do órgão colegiado do Tribunal de origem. Abrange duas realidades: (i) a parte deixou de interpor recurso ordinário cabível na origem (ex.: apelação, agravo de instrumento, recurso ordinário constitucional); e (ii) a parte deixou de utilizar via recursal específica disponível antes de acessar a via especial (ex.: agravo regimental, embargos de divergência). Súmula 281 do STF (por analogia).
- caso não tenha havido: inadmissão pelo motivo *NAO_EXAURIMENTO*.
- Caso não superadas as hipóteses acima, o recurso deve ser inadmitido; caso superadas, passa-se à etapa seguinte.

### Juízo de Conformidade
- Somente se superadas as verificações preliminares de inadmissão e se houver tema de repercussão geral ou recurso repetitivo que se amolde perfeitamente ao caso concreto, nos termos do item 3 das Considerações Iniciais.
- O juízo de conformidade está relacionado à aplicação dos temas de recurso repetitivo (STJ) e de repercussão geral (STF) aos recursos especiais interpostos, observados os critérios de identidade da questão jurídica e similitude fática que autorizam a transposição da ratio decidendi do precedente ao caso (afastando-se a aplicação do tema quando houver distinguishing).
- A análise do juízo de conformidade pode resultar em 3 (três) situações distintas:
  - Sobrestamento do processo;
  - Devolução dos autos ao Órgão Julgador para o exercício do juízo de retratação;
  - Negativa de seguimento do recurso especial;
  
#### Verificar se é hipótese de sobrestamento (art. 1.030, III, do CPC)
- Se o tema identificado não tiver sido definitivamente julgado (trânsito em julgado), no âmbito do STJ e/ou do STF, deve ser adotada uma das seguintes alternativas:
  - Se não houve julgamento do Tema, o processo deve ser sobrestado até o julgamento do Tema pelo tribunal competente;
  - Se houve o julgamento do Tema, mas não ocorreu o trânsito em julgado, deve ser mantido o sobrestamento, conforme decisão da Vice-Presidência;
  - Se forem identificados 02 (dois) ou mais temas pendentes, a decisão deverá determinar o sobrestamento até o julgamento de todos eles;
  - Se forem identificados, simultaneamente, 1 (um) tema pendente e outras questões sobre as quais não exista tema (hipótese do juízo de admissibilidade), o processo deve ser sobrestado pelo Tema, conforme uma das decisões acima;
  - Na hipótese de sobrestamento por Tema não (definitivamente) julgado, as demais questões tratadas no recurso especial não serão analisadas na decisão. Todo o processo deve ser sobrestado. Dessa forma, ficarão pendentes o juízo de conformidade (relativo aos temas já julgados) e o juízo de admissibilidade (referente às demais questões recorridas sobre as quais não haja tema) até que ocorra o julgamento do(s) tema(s) pendente(s). O sobrestamento será a única questão abordada na decisão;
- caso seja identificada: utilizar o dispositivo *SUSPENDER* (suspensão do processo até o julgamento do tema pelo tribunal competente).

#### Verificar se é hipótese de retratação (art. 1.030, II, do CPC)
- Se todos os temas de repercussão geral ou de recursos repetitivos já estiverem definitivamente julgados (trânsito em julgado) e não houver outro tema pendente de julgamento, e se verificado que o acórdão recorrido **NÃO está** em conformidade com a tese firmada no Tema, o processo deverá ser devolvido à Turma Especializada para juízo de retratação;
- Na hipótese do juizo de retratação, as demais questões tratadas no recurso especial não serão analisadas na decisão. Ficarão pendentes o juízo de conformidade (na hipótese de negativa de seguimento) e o juízo de admissibilidade (referente às demais questões recorridas em relação às quais não há tema) até o retorno dos autos. O encaminhamento para a análise do juízo de retratação será a única questão abordada nesta decisão;
- caso seja identificada: utilizar o dispositivo *ENCAMINHAR_PARA_RETRATACAO* (encaminhamento para retratação pelo tribunal de origem).

#### Verificar se é hipótese de negativa de seguimento (art. 1.030, I, do CPC)
- Se todos os temas de repercussão geral ou de recursos repetitivos já estiverem definitivamente julgados (trânsito em julgado) e não houver outro tema pendente de julgamento, e se verificado que o acórdão recorrido **está** em conformidade com a tese firmada no Tema, o processo deverá ser negado seguimento ao recurso especial;
- Na hipótese da negativa de seguimento, as demais questões tratadas no recurso especial também deverão ser analisadas nesta mesma decisão. Deve ser analisado o juízo de conformidade e negado seguimento ao recurso, em relação a cada item que contrariar tese firmada em recurso repetitivo ou em repercussão geral e efetuado o juízo de admissibilidade referente às demais questões recorridas.
- caso seja identificada: utilizar o dispositivo *NEGAR_SEGUIMENTO* (negação de seguimento ao recurso).

### Juízo de Admissibilidade
- O juízo de admissibilidade é realizado depois de superadas as verificações preliminares de inadmissão e desde que NÃO seja caso de sobrestamento nem de retratação — hipóteses em que, conforme acima, as demais questões não são analisadas e a decisão se limita àquele tema.
- Ele se aplica em duas situações:
  (i) quando não houver tema de repercussão geral ou de recurso repetitivo sobre nenhuma das questões recorridas; ou
  (ii) quando for caso de negativa de seguimento (art. 1.030, I, do CPC) — situação em que o juízo de admissibilidade deve ser feito, NA MESMA DECISÃO, **EXCLUSIVAMENTE** quanto às demais questões recorridas que **não sejam objeto de tema repetitivo ou de repercussão geral**.
- Diferentemente do sobrestamento e da retratação, a negativa de seguimento não dispensa nem encerra o juízo de admissibilidade: as duas análises convivem, aplicando-se a negativa aos itens que contrariam a tese firmada e a admissibilidade aos demais itens não abrangidos pelo tema.
- Verificar se o recurso (ou a questão recorrida não abrangida por tema) ultrapassa todos os óbices à admissibilidade abaixo.
- Se houver algum óbice à admissibilidade, o recurso deve ser inadmitido quanto a essa questão. Neste caso, usar o dispositivo *INADIMITIR*.
- A seguir, listam-se as causas específicas de inadmissibilidade do recurso especial. Cada item traz a definição sucinta do óbice e o ID do texto-base que deve ser utilizado quando o óbice for reconhecido.:

#### Pressupostos Específicos do REsp — Prequestionamento e Esgotamento

#####	Ausência de Prequestionamento (Súmulas 282/STF e 356/STF; e 211/STJ)
- Óbice que impede a admissão do recurso especial quando a tese de lei federal apontada como violada não foi previamente debatida e decidida pelo Tribunal de origem. Abrange três realidades: (i) o Tribunal a quo, mesmo provocado por embargos de declaração, não se manifestou sobre os dispositivos — e não se configura o prequestionamento ficto do art. 1.025 do CPC porque o recurso especial não apontou ofensa ao art. 1.022; (ii) a parte sequer opôs embargos de declaração para provocar essa manifestação; e (iii) os dispositivos foram suscitados pela primeira vez no recurso especial (inovação recursal). Súmulas 282 e 356 do STF e 211 do STJ.
- caso seja identificada: inadmissão pelo motivo *AUSENCIA_PREQUESTIONAMENTO*.

#####	Fundamento constitucional autônomo não impugnado — Súmula 126/STJ
- Óbice que impede a admissão do recurso especial quando o acórdão recorrido se sustenta, ao mesmo tempo, em fundamento constitucional e em fundamento infraconstitucional, cada um suficiente por si só para manter a conclusão, e a parte não afasta eficazmente o fundamento constitucional perante o STF. Abrange duas realidades: (i) a parte não interpôs recurso extraordinário; ou (ii) interpôs RE, mas ele não abrangeu o fundamento constitucional autônomo. Em ambas, o acórdão permanece íntegro independentemente do resultado do recurso especial, tornando inútil seu processamento. Súmula 126 do STJ.
- caso seja identificada: inadmissão pelo motivo *FUNDAMENTO_CONSTITUCIONAL_AUTONOMO*

####	Pressupostos Específicos do REsp (relacionados à fundamentação)

#####	Deficiência de Fundamentação (Súmula 284/STF)
- Óbice que impede a admissão do recurso especial quando suas razões não permitem a exata compreensão da controvérsia, por falta de argumentação clara, individualizada e vinculada ao acórdão recorrido. Abrange três realidades: (i) fundamentação genérica ou abstrata, dissociada dos fundamentos do julgado; (ii) indicação dos dispositivos tidos por violados sem demonstrar, de forma analítica, como o acórdão os teria contrariado; e (iii) razões que atacam fundamentos inexistentes no acórdão ou discutem matéria não examinada na origem. Súmula 284 do STF (por analogia).
- caso seja identificada: inadmissão pelo motivo *DEFICIENCIA_FUNDAMENTACAO*.

#####	Fundamento autônomo suficiente não impugnado (Súmula 283/STF)
- Óbice que impede a admissão do recurso especial quando o acórdão recorrido se apoia em mais de um fundamento infraconstitucional, cada qual suficiente por si só para mantê-lo, e o recurso não impugna todos eles, deixando subsistir fundamento autônomo capaz de preservar a conclusão. Abrange duas realidades: (i) a recorrente impugnou parte dos fundamentos, mas não o fundamento autônomo que basta para manter o julgado; e (ii) a recorrente não impugnou esse fundamento autônomo. Em ambas, o provimento do recurso seria inútil. Súmula 283 do STF (por analogia). (Distingue-se do FUNDAMENTO_CONSTITUCIONAL_AUTONOMO: aqui os fundamentos suficientes são todos infraconstitucionais; lá há um fundamento constitucional que exigiria recurso extraordinário.)
- caso seja identificada: inadmissão pelo motivo *FUNDAMENTO_AUTONOMO*.

#####	Falta de cotejo analítico ou ausência de comprovação do dissídio (divergência jurisprudencial — alínea 'c');
- Óbice que impede o recurso especial fundado em divergência jurisprudencial (alínea 'c') quando a recorrente não cumpre o art. 1.029, §1º, do CPC, seja na prova formal da divergência (certidão, cópia ou citação de repositório oficial ou credenciado, ou reprodução do julgado com indicação da fonte), seja no cotejo analítico (transcrição dos trechos divergentes, identificação das circunstâncias que assemelham os casos e demonstração de soluções distintas para situações equivalentes). Abrange: (i) ausência total de cotejo analítico (mera transcrição de ementas ou menção genérica a julgados); (ii) ausência de prova formal da divergência (falta de certidão, cópia ou citação de repositório oficial/credenciado, ou de reprodução do julgado com indicação da fonte etc); (iii) ausência de similitude fática entre o caso e o paradigma; (iv) divergência já superada, com jurisprudência do STJ no sentido do acórdão recorrido (Súmula 83/STJ); e (v) paradigma inapropriado, do mesmo tribunal ou de instância inferior, e não de outro tribunal.
- caso a falha seja a ausência de cotejo analítico entre os acórdãos; a ausência de similitude fática entre o caso e o paradigma; a hipótese se tratar de divergência já superada, com jurisprudência do STJ no sentido do acórdão recorrido; e/ou a invocação de paradigma inapropriado, do mesmo tribunal ou de instância inferior, e não de outro tribunal: inadmissão pelo motivo *FALTA_DE_COTEJO_ANALITICO*.
- caso a falha seja a ausência de prova formal da divergência (certidão, cópia ou citação de repositório oficial/credenciado, ou reprodução do julgado com indicação da fonte etc): inadmissão pelo motivo *AUSENCIA_COMPROVACAO_DISSIDIO*.

####	Causas Relacionadas ao Cabimento / Mérito

#####	Reexame do contexto Fático-Probatório — Súmula 7/STJ
- Óbice que impede a admissão do recurso especial quando acolher a pretensão exigiria reexaminar fatos ou reavaliar as provas dos autos, e não apenas rever a interpretação da lei federal. Abrange duas realidades: (i) a parte sustenta tratar-se de questão puramente jurídica, mas o exame dependeria de rever as premissas fáticas fixadas na origem; e (ii) a parte alega violação às regras de prova (distribuição do ônus, valoração, força probante de documentos), o que não afasta o óbice quando, no fundo, se busca rever as conclusões fáticas do Tribunal de origem. Súmula 7 do STJ.
- caso seja identificada: inadmissão pelo motivo *FATICA_PROBATORIA*.

#####	Conformidade com a Jurisprudência do STJ — Súmula 83/STJ
- Óbice que impede a admissão do recurso especial quando o acórdão recorrido está em consonância com a jurisprudência dominante do STJ sobre a matéria. Abrange três realidades, conforme o fundamento do recurso: (i) interposto só pela alínea 'a' (violação de lei) — o óbice incide igualmente; (ii) interposto só pela alínea 'c' (divergência); e (iii) interposto por ambas. Em todas, por estar o julgado alinhado ao entendimento consolidado da Corte, a tese da recorrente não prospera. Súmula 83 do STJ.
- caso seja identificada: inadmissão pelo motivo *CONFORMIDADE_JURISPRUDENCIA*.

#####	Conformidade com a Jurisprudência do STJ - Súmula 83/STJ. Ausência de Omissão
- Óbice que impede o recurso especial quando a parte alega violação dos arts. 489 e/ou 1.022 do CPC (negativa de prestação jurisdicional por omissão, contradição ou obscuridade), mas o vício não existe, pois o acórdão recorrido enfrentou de forma clara e fundamentada os pontos essenciais da controvérsia. Apoia-se no entendimento consolidado do STJ de que o julgador não é obrigado a rebater individualmente todos os argumentos das partes, bastando expor fundamentadamente as razões de seu convencimento, e de que a mera discordância com o resultado ou a não adoção da tese defendida não configura vício de integração. Estando o acórdão alinhado a essa jurisprudência, incide a Súmula 83 do STJ.
- caso seja identificada: inadmissão pelo motivo *CONFORMIDADE_JURISPRUDENCIA_AUSENCIA_OMISSAO*.

#####	Interpretação de cláusula contratual — Súmula 5/STJ
- Óbice que impede a admissão do recurso especial quando seu acolhimento exigiria reinterpretar cláusulas contratuais fixadas nas instâncias ordinárias, o que escapa à via especial. Abrange três realidades: (i) a controvérsia se resume à interpretação da cláusula; (ii) a parte alega que pretende discutir questão legal (ex.: nulidade ou abusividade da cláusula), mas o exame pressupõe definir antes o conteúdo e o alcance da cláusula; e (iii) hipótese cumulada com a Súmula 7, quando rever a interpretação contratual também demanda reanalisar os fatos que cercaram a formação e a execução do contrato. Súmula 5 do STJ.
- caso seja identificada: inadmissão pelo motivo *CLAUSULA_CONTRATUAL*.

#####	Interpretação e aplicação de Atos Normativos Infralegais
- Óbice que impede a admissão do recurso especial quando a controvérsia depende de interpretar atos normativos infralegais (resoluções, portarias, instruções normativas, decretos regulamentares, regimentos internos), que não se enquadram no conceito estrito de "lei federal" do art. 105, III, da CF. Abrange quatro realidades: (i) a controvérsia se resume à interpretação do ato infralegal; (ii) a parte alega violação à lei federal, mas a ofensa é apenas reflexa, pois a solução parte da norma infralegal; (iii) o ato infralegal é de origem federal — o que é irrelevante, pois importa a hierarquia normativa, não a origem; e (iv) o acórdão mescla fundamento legal e infralegal, mas a ratio decidendi se assenta de forma determinante no ato secundário.
- caso seja identificada: inadmissão pelo motivo *ATOS_NORMATIVOS_INFRALEGAIS*.

#####	Direito Local — Súmula 280/STF
- Óbice que impede a admissão do recurso especial quando a controvérsia depende de interpretar legislação local (estadual, distrital ou municipal), que não se submete ao STJ pela via especial. Abrange quatro realidades: (i) a controvérsia se resume à interpretação da norma local; (ii) a parte invoca lei federal, mas a ofensa é apenas reflexa, pois a solução parte da norma local; (iii) a norma local reproduz ou regulamenta lei nacional — o que não afasta o óbice, pois se examina a norma local em si; e (iv) o acórdão mescla fundamento local e federal, mas a ratio decidendi se assenta de forma determinante na norma local. Súmula 280 do STF (por analogia).
- caso seja identificada: inadmissão pelo motivo *DIREITO_LOCAL*.

#####	Questão Exclusivamente Constitucional
- Óbice que impede a admissão do recurso especial quando a controvérsia é de índole exclusivamente constitucional, cuja apreciação compete ao STF pela via do recurso extraordinário. Abrange duas realidades: (i) a controvérsia se centra diretamente na interpretação de dispositivo, princípio ou garantia constitucional; e (ii) a parte invoca formalmente lei ordinária, mas o núcleo da tese é a interpretação direta da Constituição, configurando ofensa apenas reflexa à lei federal. Em ambas, o instrumento adequado é o recurso extraordinário (art. 102, III, CF).
- caso seja identificada: inadmissão pelo motivo *QUESTAO_EXCLUSIVAMENTE_CONSTITUCIONAL*.

### Admissão do Recurso
- Caso não haja tema e o recurso cumpra os requisitos, ele deve ser admitido, utilizando o dispositivo *ADMITIR*.

### Recurso Prejudicado
- Caso o recurso seja prejudicado por algum motivo, utilize o dispositivo *RECURSO_PREJUDICADO*.

### Desconsiderar o pedido ou o argumento
- Caso o pedido ou argumento não seja relevante para a análise de admissibilidade, ou caso o pedido ou argumento seja repetitivo em relação a outros pedidos ou argumentos já analisados, ou já tenha sido tomada uma decisão de suspensão, ele deve ser desconsiderado, utilizando o dispositivo *DESCONSIDERAR*.


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

##### tema (opcional) - Tema do Pedido
- Quando o dispositivo for SUSPENDER, NEGAR_SEGUIMENTO ou ENCAMINHAR_PARA_RETRATACAO, deve ser informado neste campo o identificador do tema que poderá ser obtido no documento marcado como <pesquisa-de-temas>. Caso a análise de temas não tenha informado o tema para suspensão, negativa de seguimento ou encaminhamento para retratação, deixe esse campo em branco.
- O identificador do tema tem o formato "stj-rr-123" ou "stf-rg-456", conforme o tribunal e o tipo de tema. Ele pode ser encontrado no documento marcado como <pesquisa-de-temas> em passagens como por exemplo: (ID: stf-rg-123) ou (ID: stj-rr-456).

##### motivo[] (opcional, opções: AUSENCIA_PREQUESTIONAMENTO, FUNDAMENTO_CONSTITUCIONAL_AUTONOMO, DEFICIENCIA_FUNDAMENTACAO, FUNDAMENTO_AUTONOMO, FALTA_DE_COTEJO_ANALITICO, AUSENCIA_COMPROVACAO_DISSIDIO, FATICA_PROBATORIA, CONFORMIDADE_JURISPRUDENCIA, CONFORMIDADE_JURISPRUDENCIA_AUSENCIA_OMISSAO, CLAUSULA_CONTRATUAL, ATOS_NORMATIVOS_INFRALEGAIS, DIREITO_LOCAL, QUESTAO_EXCLUSIVAMENTE_CONSTITUCIONAL) - Motivo da Inadmissão
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

##### motivo[] (opcional, opções: AUSENCIA_PREQUESTIONAMENTO, FUNDAMENTO_CONSTITUCIONAL_AUTONOMO, DEFICIENCIA_FUNDAMENTACAO, FUNDAMENTO_AUTONOMO, FALTA_DE_COTEJO_ANALITICO, AUSENCIA_COMPROVACAO_DISSIDIO, FATICA_PROBATORIA, CONFORMIDADE_JURISPRUDENCIA, CONFORMIDADE_JURISPRUDENCIA_AUSENCIA_OMISSAO, CLAUSULA_CONTRATUAL, ATOS_NORMATIVOS_INFRALEGAIS, DIREITO_LOCAL, QUESTAO_EXCLUSIVAMENTE_CONSTITUCIONAL) - Motivo da Inadmissão
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
