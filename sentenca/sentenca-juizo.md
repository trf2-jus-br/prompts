---
uuid: 2035bdb3-81c9-449b-82e1-306a919e407f
name: Juízo de Sentença
description: Prepare o juízo de prolação da sentença, com análise sequencial de premissas processuais, conformidade com teses vinculantes e mérito, atribuindo o desfecho aplicável a cada pedido.
sort: 3
share: oculto
piece_strategy: mais-relevantes-primeira-instancia
instance: [primeiro-grau]
context:
  action: minuta-editar
  instance: primeiro-grau
---

# PROMPT

Leia atentamente o conteúdo das peças processuais fornecidas abaixo.

{{textos}}

Você leu diversos documentos de um processo judicial em primeiro grau, em fase de prolação de sentença.

Você leu, também, um documento marcado como <pedidos-da-inicial-e-argumentos> que contém os pedidos formulados pelo autor (e pelo reconvinte, quando houver reconvenção) e os argumentos apresentados para embasar cada pedido. A extração dos pedidos e argumentos já foi realizada previamente e deve ser reaproveitada.

Você leu um documento marcado como <pesquisa-de-temas> que contém a análise jurídica da demanda com base em teses e súmulas vinculantes. Se você optar por utilizar essa análise, deverá transcrever os dados dessa análise nos campos apropriados da resposta. No entanto, é importante destacar que a análise realizada no documento marcado como <pesquisa-de-temas> não é definitiva e pode ser complementada ou corrigida com base em outras informações disponíveis sobre o processo. Portanto, você deve considerar todas as informações disponíveis para realizar uma análise completa e precisa.

Você pode ter lido, também, um levantamento analítico do processo (sistematização da lide, das premissas de julgamento, do confronto de teses e dos desfechos possíveis), produzido em etapa anterior. Se presente, utilize-o como insumo preparatório — ele não é vinculante e não dispensa as verificações próprias deste juízo.

## Considerações Iniciais

1. Juízo de Sentença

O juízo de sentença leva em consideração uma série de análises efetuadas.
- Essas análises seguem, em regra, uma ordem sequencial: cada etapa só é examinada depois de vencida a anterior;
- As premissas processuais (pressupostos processuais e condições da ação) têm primazia sobre o juízo de mérito — regra;
- Há, contudo, determinados vícios que autorizam afastar o exame do mérito com a extinção do processo sem resolução do mérito (hipóteses do art. 485 do CPC);
- A ordem sequencial comporta uma exceção relevante: nem toda hipótese de conformidade encerra a análise. O sobrestamento é terminal — incidindo, o julgamento limita-se ao tema e as demais questões não são analisadas. Já a improcedência por contrariedade a tese vinculante convive, na mesma sentença, com o juízo de mérito das questões que não sejam objeto de tema (decisão mista).

2. Óbices iniciais

Há hipóteses que podem levar à extinção do processo sem resolução do mérito e que devem ser analisadas antes mesmo da conformidade. São seis verificações iniciais principais:
2.1. Verificar se ocorreu coisa julgada;
2.2. Verificar se há litispendência;
2.3. Verificar se há perempção;
2.4. Verificar se as partes são legítimas;
2.5. Verificar se há interesse de agir;
2.6. Verificar se a petição inicial é apta (inépcia).
Caso não superada qualquer dessas hipóteses acima, o processo deve ser extinto sem resolução do mérito.

3. Juízo de Conformidade

Superadas as verificações iniciais, passa-se ao juízo de conformidade: é necessário verificar se há (ou não) um Tema Repetitivo (STJ) ou de Repercussão Geral (STF) que se amolde perfeitamente ao caso concreto. A mera existência de um Tema sobre matéria correlata não basta. O Tema só será aplicado quando houver (i) identidade da questão jurídica entre a demanda e o Tema e (ii) similitude fática suficiente para que a ratio decidendi do precedente seja transponível ao caso. Havendo elementos distintivos relevantes entre a controvérsia e o paradigma (distinguishing), o Tema não se aplica e a análise prossegue como se inexistisse. NUNCA sugira a aplicação de tese de repercussão geral na qual o STF tenha reconhecido a ausência de repercussão geral ou o caráter infraconstitucional da controvérsia. Confirmada a aplicação do Tema, deve ser analisada a conformidade, na seguinte sequência:
3.1. Verificar se é hipótese de sobrestamento (art. 313, VI, e art. 1.040 do CPC);
3.2. Verificar se é hipótese de procedência ou de improcedência com fundamento na tese.

4. Juízo de Mérito

Passa-se ao juízo de mérito quando: (i) não houver tema de repercussão geral ou de recurso repetitivo sobre as questões deduzidas; ou (ii) quando as demais questões não são abrangidas por tema.
Não se chega a esta etapa nas hipóteses de extinção sem resolução do mérito e de sobrestamento, que encerram o julgamento.
Para que o mérito seja apreciado, não deve haver tema que imponha sobrestamento, procedência ou improcedência pela tese, nem qualquer óbice processual extintivo.


## Roteiro de Verificação

Utilize a seguinte sequência de verificações para analisar:

### Verificações Preliminares de Extinção sem Resolução do Mérito
- Se houver algum óbice processual que impeça o exame do mérito, independente da análise do pedido específico, o processo deve ser extinto sem resolução do mérito.
- Neste caso, informe o motivo no campo "motivoGeral" do JSON.
- Este campo é um array, pois pode haver mais de um motivo geral.
- As opções de motivos gerais estão listadas abaixo.
- Antes de indicar a extinção, verifique se o vício era sanável e se houve oportunidade de correção (arts. 317 e 321 do CPC): consumada a oportunidade sem correção, a extinção subsiste.

#### Verificar coisa julgada
- Óbice que impede o exame do mérito quando já existe decisão judicial de mérito transitada em julgado sobre a mesma demanda, entre as mesmas partes, com a mesma causa de pedir e o mesmo pedido (identidade de partes, de causa de pedir e de pedido — art. 485, V, do CPC). A coisa julgada pode ser reconhecida de ofício (art. 485, §3º, do CPC; art. 507 do CPC).
- caso identificada: extinção sem resolução do mérito pelo motivo *COISA_JULGADA*.

#### Verificar litispendência
- Óbice que impede o exame do mérito quando se reproduz ação anteriormente ajuizada e ainda em curso, com identidade de partes, de causa de pedir e de pedido (art. 485, V, do CPC). Requer a demonstração da pendência da outra causa; não configurada a identidade, não há litispendência.
- caso identificada: extinção sem resolução do mérito pelo motivo *LITISPENDENCIA*.

#### Verificar perempção
- Óbice que impede o exame do mérito quando o autor dá causa, por 2 (duas) vezes, à extinção do processo por abandono da causa por mais de 30 dias (art. 485, III, do CPC), incidindo a vedação de renovar a mesma ação (art. 485, V, do CPC).
- caso identificada: extinção sem resolução do mérito pelo motivo *PERECAO*.

#### Verificar ilegitimidade de parte
- Óbice que impede o exame do mérito por ausência de legitimidade para a causa (arts. 17 e 18 do CPC; art. 485, VI, do CPC): falta ao autor legitimidade ativa quando, à luz do direito material aplicável, não é titular da situação jurídica afirmada; falta ao réu legitimidade passiva quando a pretensão deduzida não deveria ser dirigida contra ele. Verifique, antes, a possibilidade de substituição processual do réu ilegítimo (arts. 338 e 339 do CPC): provida a substituição, a ilegitimidade deixa de ser óbice; requirida a substituição e não provida (ou não requerida no prazo), subsiste a extinção.
- caso identificada: extinção sem resolução do mérito pelo motivo *ILEGITIMIDADE_DE_PARTE*.

#### Verificar falta de interesse de agir
- Óbice que impede o exame do mérito por ausência de interesse processual, condição da ação que exige a utilidade e a necessidade da tutela jurisdicional requerida (art. 485, VI, do CPC). Configura-se quando: (i) a pretensão já foi integralmente satisfeita pela parte adversa, inexistindo necessidade de providência jurisdicional; ou (ii) o provimento pedido é inútil ou inadequado para remover a situação de incerteza ou de lesão alegada, seja pela via eleita, seja pelo resultado perseguido.
- caso identificada: extinção sem resolução do mérito pelo motivo *FALTA_DE_INTERESSE_DE_AGIR*.

#### Verificar inépcia da petição inicial
- Óbice que impede o exame do mérito quando a petição inicial é inepta (art. 330, §1º, do CPC): (i) falta de pedido ou causa de pedir; (ii) narração dos fatos que não corresponda ao pedido, ou que dele não se possa deduzir a pretensão; (iii) pedido juridicamente impossível; (iv) pedido indeterminado, ressalvadas as hipóteses legais em que se permite. Considera-se inepta a inicial quando, mesmo em conjunto, não se possa deduzir do conjunto dos elementos a pretensão. A inépcia não sanada por emenda (art. 321 do CPC) conduz ao indeferimento da inicial e à extinção do processo (arts. 330 e 485, I, do CPC).
- caso identificada: extinção sem resolução do mérito pelo motivo *INEPCIA_DA_INICIAL*.
- Caso superadas as hipóteses acima, passa-se à etapa seguinte.

### Juízo de Conformidade
- Somente se superadas as verificações preliminares de extinção sem resolução do mérito e se houver tema de repercussão geral ou recurso repetitivo que se amolde perfeitamente ao caso concreto, nos termos do item 3 das Considerações Iniciais.
- O juízo de conformidade está relacionado à aplicação dos temas de recurso repetitivo (STJ) e de repercussão geral (STF) à controvérsia submetida ao juízo, observados os critérios de identidade da questão jurídica e similitude fática que autorizam a transposição da ratio decidendi do precedente ao caso (afastando-se a aplicação do tema quando houver distinguishing). NUNCA sugira a aplicação de tese de repercussão geral na qual o STF tenha reconhecido ausência de repercussão geral ou o caráter infraconstitucional da controvérsia.
- A análise do juízo de conformidade pode resultar em 2 (duas) situações distintas:
  - Sobrestamento/suspensão do processo, até o julgamento definitivo do tema;
  - Resolução da controvérsia pela própria tese firmada no tema, julgando o pedido com fundamento na tese vinculante (procedência ou improcedência, conforme o caso).
- Princípio da subsunção ordinária (aplicar tese ≠ revolver matéria de fato): a aplicação de uma tese ao caso concreto sempre exige subsumir os fatos do caso à hipótese normativa do precedente. Isso é jurisdição ordinária, não reexame probatório. Não confunda "aplicar a tese exige verificar como os fatos do caso se enquadram na hipótese do precedente" (situação normal e inevitável em qualquer aplicação do direito) com "a tese trata de hipótese fática genericamente diferente da do caso" (distinguishing legítimo). Esses dois planos têm consequências opostas:
   - Quando a tese se ocupa da MESMA questão jurídica e da MESMA situação fática genérica do caso, ela SE APLICA e deve fundamentar o julgamento do pedido (procedência ou improcedência, conforme o desfecho que a tese impõe), AINDA QUE a aplicação demande examinar como, naquele caso concreto, os elementos previstos na tese se realizam.
   - Apenas quando a tese se ocupa de hipótese fática genericamente DIFERENTE da do caso (o precedente discute uma situação normativa distinta) há distinguishing, e a tese não se aplica, prosseguindo a análise de mérito pelas demais questões.
- No julgamento de primeiro grau, o juiz aprecia livremente a prova produzida nos autos, ainda que não alegada pelas partes, indicando na sentença as razões do seu convencimento (arts. 369 e 371 do CPC): avaliar como os elementos do caso concreto se realizam na hipótese do precedente é o próprio ofício de julgar. Você NÃO deve afastar a aplicação de uma tese sob fundamento de que sua aplicação demandaria avaliar circunstâncias do caso — avaliar circunstâncias do caso para subsumir à norma é o que todo julgador faz. A tese apenas não resolve a controvérsia quando a questão for exclusivamente fático-probatória, sem questão jurídica alguma que a tese possa decidir — hipótese em que o julgamento se fará pela análise probatória, no juízo de mérito.
- Caso identificada hipótese de sobrestamento/suspensão, você não deve indicar procedência, improcedência ou prejudicialidade, pois o sobrestamento é hipótese de exclusão absoluta de todas as demais hipóteses.
  
#### Verificar se é hipótese de sobrestamento/suspensão (art. 313, VI, e art. 1.040, ambos do CPC)
- Se o tema de repercussão geral e/ou de recurso repetitivo identificado não tiver sido definitivamente julgado (trânsito em julgado), no âmbito do STJ e/ou do STF, deve ser adotada uma das seguintes alternativas:
  - Se não houve julgamento do Tema, o processo deve ser sobrestado até o julgamento do Tema pelo tribunal competente;
  - Se houve o julgamento do Tema, mas não ocorreu o trânsito em julgado, deve ser mantido o sobrestamento;
  - Se forem identificados 02 (dois) ou mais temas pendentes, de repercussão geral e/ou de recurso repetitivo, a decisão deverá determinar o sobrestamento até o julgamento de todos eles;
  - Se forem identificados, simultaneamente, 1 (um) tema pendente e outras questões sobre as quais não exista tema (hipótese de juízo de mérito), o processo deve ser sobrestado pelo Tema, conforme uma das decisões acima;
  - Na hipótese de sobrestamento por Tema não (definitivamente) julgado, as demais questões tratadas na demanda não serão analisadas na sentença. Todo o processo deve ser sobrestado. Ficarão pendentes o juízo de conformidade (relativo aos temas já julgados) e o juízo de mérito (referente às demais questões sobre as quais não haja tema) até que ocorra o julgamento do(s) tema(s) pendente(s). O sobrestamento será a única questão abordada na sentença. Caso identificada hipótese de sobrestamento/suspensão, você não deve indicar procedência, improcedência ou prejudicialidade, pois o sobrestamento é hipótese de exclusão absoluta de todas as demais hipóteses;
  - Se houver tema de repercussão geral não definitivamente julgado (hipóteses acima), o processo deve ser suspenso ainda que não se trate de recurso extraordinário;
- caso seja identificada: utilizar o dispositivo *SUSPENDER* (suspensão do processo até o julgamento do tema pelo tribunal competente).

#### Verificar se é hipótese de procedência com fundamento na tese
- Se todos os temas de repercussão geral ou de recursos repetitivos relevantes para a controvérsia já estiverem definitivamente julgados (trânsito em julgado) e não houver outro tema pendente de julgamento, e se verificado que a pretensão do autor DEVE ser acolhida nos termos da tese firmada no Tema, o pedido deve ser julgado procedente, com aplicação da tese vinculante ao caso concreto;
- Na hipótese de procedência com fundamento na tese, as demais questões tratadas na demanda também deverão ser analisadas na mesma sentença: aplica-se a tese à matéria a ela sujeita (com fundamento no art. 927, caput, do CPC) e efetua-se o juízo de mérito referente às demais questões.
- caso seja identificada: utilizar o dispositivo *PROCEDENTE* (julgamento procedente do pedido com aplicação da tese vinculante).

#### Verificar se é hipótese de improcedência com fundamento na tese
- Se todos os temas de repercussão geral ou de recursos repetitivos relevantes para a controvérsia já estiverem definitivamente julgados (trânsito em julgado) e não houver outro tema pendente de julgamento, e se verificado que a pretensão do autor NÃO DEVE ser acolhida, nos termos da tese firmada no Tema, o pedido deve ser julgado improcedente;
- Essa hipótese abrange as situações de improcedência liminar do art. 332 do CPC: pedido que contraria enunciado de súmula do STF ou do STJ, acórdão proferido em julgamento de recursos repetitivos, entendimento firmado em incidente de resolução de demandas repetitivas ou de assunção de competência, ou enunciado de súmula de tribunal de justiça sobre direito local, bem como a decadência ou a prescrição verificadas desde logo (art. 332, §1º, do CPC);
- Na hipótese de improcedência com fundamento na tese, as demais questões tratadas na demanda também deverão ser analisadas na mesma sentença: aplica-se a tese à matéria a ela sujeita (com fundamento no art. 927, caput, do CPC) e efetua-se o juízo de mérito referente às demais questões.
- caso seja identificada: utilizar o dispositivo *IMPROCEDENTE* (julgamento improcedente do pedido com aplicação da tese vinculante).

### Juízo de Mérito
- O juízo de mérito é realizado depois de superadas as verificações preliminares e desde que NÃO seja caso de sobrestamento — hipótese em que, conforme acima, as demais questões não são analisadas e o julgamento se limita àquele tema.
- Ele se aplica em duas situações:
  (i) quando não houver tema de repercussão geral ou de recurso repetitivo sobre nenhuma das questões deduzidas; ou
  (ii) quando houver questões que não sejam abrangidas por tema definitivamente julgado — situação em que essas questões devem ser julgadas, NA MESMA SENTENÇA, ainda que parte da controvérsia seja resolvida pela tese vinculante.

#### Julgamento das prejudiciais de mérito (prescrição e decadência)
- Antes de julgar o mérito de cada pedido, verifique a ocorrência de prescrição ou decadência, alegada pela parte ou reconhecível de ofício — neste caso, após oportunidade de manifestação das partes (art. 487, II, e parágrafo único, do CPC).
- O acolhimento da prescrição ou da decadência conduz ao julgamento de improcedência do pedido, com resolução do mérito (art. 487, II, do CPC), e NÃO à extinção do processo sem resolução do mérito.
- caso seja identificada: utilizar o dispositivo *IMPROCEDENTE*, indicando a prejudicial na fundamentação.

#### Julgamento do pedido no mérito (desfechos)
- Superadas as verificações preliminares, afastada a hipótese de sobrestamento, rejeitadas as prejudiciais de mérito, cada pedido deve ser julgado no mérito, com exame da matéria de fato e de direito suscitada.
- A tese firmada em tema definitivamente julgado deve ser aplicada de ofício (art. 927, caput, do CPC), vinculando o julgamento da matéria abrangida.
- Para cada pedido, verifique se ele é procedente, improcedente ou parcialmente procedente, à luz dos argumentos invocados, da legislação aplicável e do material probatório dos autos. Julgue cada pedido conforme o desfecho adequado:
  - se o pedido deve ser acolhido integralmente: utilizar o dispositivo *PROCEDENTE*;
  - se o pedido deve ser acolhido apenas em parte: utilizar o dispositivo *PROCEDENTE_PARCIAL*;
  - se o pedido deve ser rejeitado: utilizar o dispositivo *IMPROCEDENTE*.

### Pedido Prejudicado
O pedido recebe dispositivo *PREJUDICADO* quando, supervenientemente ao ajuizamento, fato ou ato processual esvazia o seu objeto, retirando a utilidade do exame de mérito. A perda de objeto deve ser verificada com cautela: só configura essa hipótese quando nenhum interesse remanescer em relação ao pedido.

#### Satisfação superveniente da pretensão
Quando a pretensão postulada é integralmente satisfeita no curso do processo — ex.: o réu promove o cancelamento da inscrição indevida, paga a quantia reclamada, cumpre a obrigação de fazer postulada —, o pedido correspondente fica prejudicado: a satisfação esvazia o objeto, retirando a utilidade do exame de mérito. Atribua *PREJUDICADO*.
- Cuidado: a prejudicialidade pressupõe satisfação integral e comprovada. Se a satisfação for parcial, ou se subsistir controvérsia (ex.: sobre parcelas acessórias, juros, correção monetária), não há prejudicialidade — o pedido deve ser julgado no mérito quanto ao remanescente.

*PREJUDICADO* aplica-se ao pedido cujo objeto desapareceu; os demais pedidos seguem análise normal.

### Desconsiderar o pedido ou o argumento
- Caso o pedido ou argumento não seja relevante para o juízo de sentença, ou caso o pedido ou argumento seja repetitivo em relação a outros pedidos ou argumentos já analisados, ou já tenha sido tomada uma decisão de suspensão, ele deve ser desconsiderado, utilizando o dispositivo *DESCONSIDERAR*.
- Pedido de gratuidade de justiça formulado na inicial NÃO é pedido de mérito. Trata-se de requerimento procedimental, dirigido ao juízo, sem matéria a ser examinada em juízo de conformidade ou de mérito. Atribua dispositivo *DESCONSIDERAR*.
  - Distinção essencial: eventual impugnação da parte adversa ao deferimento da gratuidade (art. 99, §§2º a 5º, do CPC) é questão incidental, resolvida em separado, sem dispositivo de mérito na sentença; o regime da gratuidade deferida (suspensão da exigibilidade das verbas sucumbenciais — art. 98, §3º, do CPC) deve ser observado na fase de sucumbência, não como pedido de mérito.
  - Critério prático: pergunte-se "este item busca um pronunciamento sobre o objeto da causa (condenar, declarar, constituir, anular) ou apenas uma providência procedimental do juízo?". Se for providência procedimental → *DESCONSIDERAR*.


## FIELDS

Os campos abaixo compõem o JSON de diretrizes que orientará a redação da sentença na etapa seguinte. O usuário poderá revisar e editar esse JSON antes da redação da sentença — preencha-o, portanto, com a sua melhor sugestão, de modo completo e fundamentado.

### motivoGeral[] (opcional, opções: COISA_JULGADA, LITISPENDENCIA, PERECAO, ILEGITIMIDADE_DE_PARTE, FALTA_DE_INTERESSE_DE_AGIR, INEPCIA_DA_INICIAL) - Motivo da Extinção sem Resolução do Mérito
- Quando for o caso de extinção do processo sem resolução do mérito por um motivo que independe da análise do pedido específico, deve ser informado neste campo o identificador do motivo da extinção.
- As opções de motivos estão listadas e explicadas no título Verificações Preliminares de Extinção sem Resolução do Mérito, acima.
- Caso haja mais de um motivo geral, informe todos os motivos aplicáveis neste campo, utilizando um array. Preencha este campo com [].

### pedidos[] - Pedidos

##### texto - Texto do Pedido
- Informe o texto conciso que descreve o pedido de mérito
- Esse texto deve ser copiado do documento ipsis litteris, do documento marcado como <pedidos-da-inicial-e-argumentos>.

##### dispositivo (opções: SUSPENDER, PROCEDENTE, PROCEDENTE_PARCIAL, IMPROCEDENTE, DESCONSIDERAR, PREJUDICADO) - Dispositivo do Pedido
- Se foi identificado um tema pendente de julgamento definitivo, utilize a opção SUSPENDER.
- Se um pedido anterior já foi marcado com SUSPENDER, e não houver tema ou motivo de extinção específico para o pedido atual, preencha este campo com DESCONSIDERAR.
- Quando um pedido vier marcado como SUBSIDIARIO ou ALTERNATIVO em relação a outro, e o pedido vinculado já tiver sido julgado procedente ou decidido em termos que o tornem prejudicado, o dispositivo do pedido subsidiário/alternativo deve ser DESCONSIDERAR. Caso o pedido vinculado tenha sido rejeitado sem afetar o subsidiário (ex.: rejeição da preliminar de nulidade não prejudica o pedido subsidiário de mérito), o subsidiário deve receber análise própria.
- Quando o pedido tiver Tp_Relacao=ACESSORIO com Id_PedidoVinculado preenchido: o pedido recebe DESCONSIDERAR. O acessório não tem existência autônoma para fins de julgamento — está contido na decisão sobre o principal (se este for procedente) ou é por ele prejudicado (se este for improcedente, suspenso ou desconsiderado). A análise incide exclusivamente sobre o pedido principal vinculado.
- Quando o pedido tiver Tp_Relacao=SUBSIDIARIO com Id_PedidoVinculado preenchido: aplique a propagação apenas se o pedido vinculado tiver recebido dispositivo PROCEDENTE — nesse caso, o subsidiário recebe DESCONSIDERAR (a pretensão principal foi acolhida, tornando inútil a alternativa). Em todos os demais casos (principal recebeu IMPROCEDENTE, PROCEDENTE_PARCIAL, SUSPENDER ou DESCONSIDERAR), o pedido subsidiário deve ser analisado autonomamente, recebendo dispositivo conforme as regras gerais deste campo.

##### tema[] (opcional) - Tema do Pedido
- Quando o dispositivo for SUSPENDER, PROCEDENTE ou IMPROCEDENTE com fundamento em tese vinculante, devem ser informados neste campo um ou mais identificadores dos temas que poderão ser obtidos no documento marcado como <pesquisa-de-temas>. Caso a análise de temas não tenha informado o tema para suspensão ou julgamento com fundamento na tese, deixe esse campo em branco.
- O identificador do tema tem o formato "stj-rr-123" ou "stf-rg-456", conforme o tribunal e o tipo de tema. Ele pode ser encontrado no documento marcado como <pesquisa-de-temas> em passagens como por exemplo: (ID: stf-rg-123) ou (ID: stj-rr-456).

##### fundamentacoes[] - Fundamentações Sugeridas do Pedido
- Liste sugestões de fundamentação a favor e contra o pedido, para orientar a redação da sentença na etapa seguinte.
- Apresente entre 2 e 4 sugestões de cada tipo (A_FAVOR e CONTRA). Extraia ou sintetize as sugestões a partir das peças (petição inicial, contestação, réplica), do documento marcado como <pesquisa-de-temas> (teses e súmulas aplicáveis) e, se presente, do levantamento analítico do processo — não as invente.
- O usuário poderá revisar este JSON e alterar as marcações (inclusive o próprio teor das fundamentações) antes da redação da sentença; a redação utilizará as fundamentações marcadas como roteiro.
- Quando o dispositivo do pedido for SUSPENDER, PREJUDICADO ou DESCONSIDERAR, o preenchimento deste campo é opcional (pode permanecer vazio).
- Para cada sugestão, preencha os campos texto, tipo e checked:

###### Tg_Texto - Texto da Fundamentação
- A fundamentação, formulada de modo conciso e aplicável ao caso concreto (não uma máxima abstrata).

###### Tipo (opções: A_FAVOR, CONTRA) - Tipo da Fundamentação
- Tipo: A_FAVOR (fundamentação que sustenta a procedência do pedido) ou CONTRA (fundamentação que sustenta o seu desacolhimento).

###### Lo_Selecionada - Selecionada
- Indicação de que a sugestão deve ser aproveitada na redação da sentença.
- Dentre as sugestões apresentadas, marque com true nas que entender pertinentes e mais importantes: tipicamente, as alinhadas com o dispositivo atribuído ao pedido e as contrárias relevantes que deverão ser enfrentadas na fundamentação. Marque checked=false nas demais. Isso é uma decisão da IA, que poderá ser revista pelo usuário antes da redação da sentença.

#### argumentos[] - Argumentos do Pedido
- Liste os fundamentos jurídicos apresentados para embasar o pedido

##### texto - Texto do Argumento
- Esse texto deve ser copiado do documento marcado como <pedidos-da-inicial-e-argumentos>.

##### dispositivo (opções: ACOLHER, REJEITAR, DESCONSIDERAR) - Dispositivo do Argumento
- Quando o pedido for julgado improcedente ou parcialmente procedente, cada um dos argumentos deve ser analisado individualmente, com o dispositivo ACOLHER ou REJEITAR, conforme o caso.
- Quando o pedido for julgado integralmente procedente, todos os argumentos devem receber DESCONSIDERAR, pois não há necessidade de enfrentá-los individualmente.
- Se o pedido for desconsiderado, todos os argumentos devem receber DESCONSIDERAR.

##### fundamentacoes[] - Fundamentações Sugeridas do Argumento
- Apresente, para o argumento, entre 1 e 2 sugestões A_FAVOR e entre 1 e 2 CONTRA.
- As fundamentacoes devem ser extraídas ou sintetizadas das peças, do documento marcado como <pesquisa-de-temas>, do documento marcado como <busca-de-jurisprudencia> e, se presente, do levantamento analítico do processo. Também podem ser extraídas de fundamentos jurídicos que o usuário tenha identificado e que não constem nos documentos acima. Não as invente.

###### Tg_Texto - Texto da Fundamentação
- A fundamentação, formulada de modo conciso e aplicável ao caso concreto (não uma máxima abstrata).

###### Tipo (opções: A_FAVOR, CONTRA) - Tipo da Fundamentação
- Tipo: A_FAVOR (fundamentação que sustenta o acolhimento do argumento) ou CONTRA (fundamentação que sustenta o seu desacolhimento).

###### Lo_Selecionada - Selecionada
- Indicação de que a sugestão deve ser aproveitada na redação da sentença.
- Dentre as sugestões apresentadas, marque com true as que entender pertinentes e mais importantes: tipicamente, as alinhadas com o dispositivo atribuído ao pedido e as contrárias relevantes que deverão ser enfrentadas na fundamentação. Marque false nas demais. Isso é uma sugestão da IA, que poderá ser revista pelo usuário antes da redação da sentença.


### Tg_ComandosAdicionais (opcional) - Comandos Adicionais
- Utilize este campo para informar quaisquer comandos adicionais que sejam necessários para redação da sentença, que será feita em seguida, mas que não se encaixem nos campos anteriores. Por exemplo, caso seja necessário desmembrar um pedido ou argumento específico, ou caso haja alguma particularidade relevante para a análise, informe aqui. Se não houver comandos adicionais, deixe este campo em branco. Não repita informações que já constem dos campos anteriores.

# FORMAT
{% if motivoGeral %}**Motivo(s) de Extinção sem Resolução do Mérito:** {{ motivoGeral | join(", ") }}
{% else %}
{% for d in pedidos %}**Pedido {{loop.index}}:** {= d.texto =}
- Dispositivo: {{ d.dispositivo }}{% if d.tema %}
- Tema(s): {{ d.tema | join(", ") }}{% endif %}

{% if d.argumentos %}Argumentos:{% for a in d.argumentos %}
{{loop.index}}. {= a.texto =} ({{ a.dispositivo }}){% endfor %}

{% endif %}{% if d.fundamentacoes %}Fundamentações:{% for f in d.fundamentacoes %}
{{loop.index}}. {{ "[x]" if f.Lo_Selecionada else "[ ]" }} ({{ f.Tipo }}) {= f.Tg_Texto =}{% endfor %}

{% endif %}{% endfor %}
{% endif %}
{% if Tg_ComandosAdicionais %}
**Comandos Adicionais:** {= Tg_ComandosAdicionais =}
{% endif %}
