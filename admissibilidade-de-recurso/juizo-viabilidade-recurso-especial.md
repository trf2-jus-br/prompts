---
uuid: 89dfafb9-0961-415d-871a-62a52351a75c
name: Juízo de Viabilidade de Recurso Especial
sort: 3
share: oculto
piece_strategy: viabilidade-recurso-especial
grupo:
  slug: decisao-de-viabilidade
  titulo: Admissibilidade de Recursos
---

# PROMPT

Leia atentamente o conteúdo das peças processuais fornecidas abaixo.

{{textos}}

Você leu diversos documentos relacionados a Recurso Especial em processo judicial.

Você leu, também, um documento marcado como <pedidos-do-recurso-e-argumentos> que contém os pedidos formulados no recurso judicial e os argumentos apresentados para embasar cada pedido. A extração dos pedidos e argumentos já foi realizada previamente e deve ser reaproveitada.

Você leu um documento marcado como <pesquisa-de-temas> que contém a análise de viabilidade jurídica do recurso com base em teses e súmulas vinculantes. Se você optar por utilizar essa análise, deverá trascrever os dados dessa análise nos campos apropriados da resposta. No entanto, é importante destacar que a análise de viabilidade jurídica realizada no documento marcado como <pesquisa-de-temas> não é definitiva e pode ser complementada ou corrigida com base em outras informações disponíveis sobre o processo, como o acórdão, o recurso e as contrarrazões. Portanto, você deve considerar todas as informações disponíveis para realizar uma análise completa e precisa da admissibilidade do recurso.

## Considerações Iniciais

1. Juízo de Viabilidade do REsp (Recurso Especial)

O juízo de viabilidade do Recurso Especial leva em consideração uma séria de análises efetuadas pela Vice-Presidência do Tribunal (juízo de conformidade e juízo de viabilidade).
- Essas análises devem ser feitas de forma sequencial, pois as etapas seguintes são analisadas apenas depois de superadas as etapas anteriores;
- O juízo de conformidade tem primazia sobre o juízo de admissibilidade – regra (STJ);
- Há, contudo, determinados vícios que autorizam seja afastada a aplicação do juízo de conformidade para o exercício do juízo de admissibilidade (hipóteses de inadmissão).

2. Óbices iniciais à admissibilidade (Manual STJ, p. 26-27)

Há hipóteses que podem levar à inadmissibilidade do recurso (juízo de admissibilidade) e que devem ser analisadas antes mesmo da conformidade. São três verificações iniciais principais:
2.1. Verificar se houve preparo;
2.2. Verificar se o recurso é tempestivo (art. 1.036, § 3º, do CPC).
2.3. Verificar se houve o esgotamento da jurisdição no órgão de origem;
Caso não superada qualquer dessas hipóteses acima, o recurso deve ser inadmitido


3. Juízo de Conformidade

Verificado o preparo, a tempestividade e o esgotamento da instância, passa-se ao juízo de conformidade, ou seja, é necessário verificar se há (ou não) um Tema Repetitivo (STJ) ou de Repercussão Geral (STF). Caso haja um Tema relativo a qualquer das matérias que seja objeto do recurso, deve ser analisada a conformidade, na seguinte sequência:
3.1. Verificar se é hipótese de sobrestamento (art. 1.030, III, do CPC);
3.2. Verificar se é hipótese de retratação (art. 1.030, II, do CPC);
3.3. Verificar se é hipótese de negativa de seguimento (art. 1.030, I, do CPC).

4. Juízo de Admissibilidade

Ultrapassadas as etapas acima, passa-se à análise do juízo de admissibilidade do Recurso.
Para que o recurso seja admitido é necessário que não haja nenhum óbice à sua admissão

5. Admissão

O recurso especial somente será admitido, caso não haja um tema (ou caso haja e não seja exercido o juízo de retratação), e nem a incidência de uma hipótese de inadmissão


## Roteiro de Verificação

Utilize a seguinte sequência de verificações para analisar a admissibilidade do recurso especial:

### Verificações Preliminares de Inadmissão
- Se houver algum motivo de inadmissão geral, independente da análise do pedido ou argumento específico, o recurso deve ser inadmitido.
- Neste caso, informe o motivo da inadmissão no campo "motivoGeral" do JSON.
- Este campo é um array, pois pode haver mais de um motivo de inadmissão geral.
- As opções de motivos de inadmissão geral estão listadas abaixo.

#### Verificar se houve preparo
- caso não haja: inadmissão pelo motivo *DESERCAO*.

####  Verificar Irregularidade da representação processual
- caso seja identificada: inadmissão pelo motivo *IRREGULARIDADE_REPRESENTACAO*.
- Caso não superadas as hipóteses acima, o recurso deve ser inadmitido; caso superada, passa-se à etapa seguinte.

####  Verificar Ilegitimidade
- caso seja identificada: inadmissão pelo motivo *ILEGITIMIDADE*.

#### Verificar se o recurso é tempestivo
- caso não seja: inadmissão pelo motivo *INTEMPESTIVIDADE*.

####  Verificar Falta de interesse
- caso seja identificada: inadmissão pelo motivo *FALTA_DE_INTERESSE_RECURSAL*.

#### Verificar se houve o esgotamento da jurisdição no órgão de origem
- caso não tenha havido: inadmissão pelo motivo *NAO_EXAURIMENTO*.

### Juízo de Conformidade
- Somente se superadas as verificações preliminares de inadmissão e se houver tema de repercussão geral ou recurso repetitivo
- O juízo de conformidade está relacionado à aplicação dos temas de recurso repetitivo (STJ) e de repercussão geral (STF) aos recursos especiais interpostos.
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
- Se todos os temas de repercussão geral ou de recursos repetitivos já estiverem definitivamente julgados (trânsito em julgado) e não houver outro tema pendente de julgamento, e se verificado que o acórdão recorrido **está** em conformidade com a tese firmada no Tema, o processo deverá ser devolvido à Turma Especializada para juízo de retratação;
- Na hipótese do juizo de retratação, as demais questões tratadas no recurso especial não serão analisadas na decisão. Ficarão pendentes o juízo de conformidade (na hipótese de negativa de seguimento) e o juízo de admissibilidade (referente às demais questões recorridas em relação às quais não há tema) até o retorno dos autos. O encaminhamento para a análise do juízo de retratação será a única questão abordada nesta decisão;
- caso seja identificada: utilizar o dispositivo *ENCAMINHAR_PARA_RETRATACAO* (encaminhamento para retratação pelo tribunal de origem).

#### Verificar se é hipótese de negativa de seguimento (art. 1.030, I, do CPC)
- Se todos os temas de repercussão geral ou de recursos repetitivos já estiverem definitivamente julgados (trânsito em julgado) e não houver outro tema pendente de julgamento, e se verificado que o acórdão recorrido **não está** em conformidade com a tese firmada no Tema, o processo deverá ser negado seguimento ao recurso especial;
- Na hipótese da negativa de seguimento, as demais questões tratadas no recurso especial também deverão ser analisadas nesta mesma decisão. Deve ser analisado o juízo de conformidade e negado seguimento ao recurso, em relação a cada item que contrariar tese firmada em recurso repetitivo ou em repercussão geral e efetuado o juízo de admissibilidade referente às demais questões recorridas.
- caso seja identificada: utilizar o dispositivo *NEGAR_SEGUIMENTO* (negação de seguimento ao recurso).

### Juízo de Admissibilidade
- Somente se superadas as verificações preliminares de inadmissão as hipóteses de sobrestamento, retratação e negativa de seguimento, ou se não houver tema de repercussão geral ou recurso repetitivo.
-	Verificar se o recurso ultrapassa todos os óbices à admissibilidade abaixo.
- Se houver algum óbice à admissibilidade, o recurso deve ser inadmitido. Neste caso, usar o dispositivo *INADIMITIR*.

#####	Ausência de Prequestionamento (Súmulas 282/STF e 356/STF; e 211/STJ)
- caso seja identificada: inadmissão pelo motivo *AUSENCIA_PREQUESTIONAMENTO*.

#####	Fundamento constitucional autônomo não impugnado — Súmula 126/STJ
- caso seja identificada: inadmissão pelo motivo *FUNDAMENTO_CONSTITUCIONAL_AUTONOMO*

####	Pressupostos Específicos do REsp (relacionados à fundamentação)

#####	Deficiência de Fundamentação (Súmula 284/STF)
- caso seja identificada: inadmissão pelo motivo *DEFICIENCIA_FUNDAMENTACAO*.

#####	Fundamento autônomo suficiente não impugnado (Súmula 283/STF)
- caso seja identificada: inadmissão pelo motivo *FUNDAMENTO_AUTONOMO*.

#####	Falta de cotejo analítico (divergência jurisprudencial — alínea 'c');
- caso seja identificada: inadmissão pelo motivo *FALTA_DE_COTEJO_ANALITICO*.

#####	Ausência de comprovação do dissídio jurisprudencial;
- caso seja identificada: inadmissão pelo motivo *AUSENCIA_COMPROVACAO_DISSIDIO*.

####	Causas Relacionadas ao Cabimento / Mérito

#####	Reexame do contexto Fático-Probatório — Súmula 7/STJ
- caso seja identificada: inadmissão pelo motivo *FATICA_PROBATORIA*.

#####	Conformidade com a Jurisprudência do STJ — Súmula 83/STJ
- caso seja identificada: inadmissão pelo motivo *CONFORMIDADE_JURISPRUDENCIA*.

#####	Interpretação de cláusula contratual — Súmula 5/STJ
- caso seja identificada: inadmissão pelo motivo *CLAUSULA_CONTRATUAL*.

#####	Interpretação e aplicação de Atos Normativos Infralegais
- caso seja identificada: inadmissão pelo motivo *ATOS_NORMATIVOS_INFRALEGAIS*.

#####	Direito Local — Súmula 280/STF
- caso seja identificada: inadmissão pelo motivo *DIREITO_LOCAL*.

#####	Questão Exclusivamente Constitucional
- caso seja identificada: inadmissão pelo motivo *QUESTAO_EXCLUSIVAMENTE_CONSTITUCIONAL*.

### Admissão do Recurso
- Caso não haja tema e o recurso cumpra os requisitos, ele deve ser admitido, utilizando o dispositivo *ADMITIR*.

### Recurso Prejudicado
- Caso o recurso seja prejudicado por algum motivo, utilize o dispositivo *RECURSO_PREJUDICADO*.

### Desconsiderar o pedido ou o argumento
- Caso o pedido ou argumento não seja relevante para a análise de admissibilidade, ou caso o pedido ou argumento seja repetitivo em relação a outros pedidos ou argumentos já analisados, ou já tenha sido tomada uma decisão de suspensão, ele deve ser desconsiderado, utilizando o dispositivo *DESCONSIDERAR*.


## FIELDS READONLY

### motivoGeral[] - Motivo da Inadmissão
- Quando for o caso de inadmitir por um motivo geral, independente da análise do pedido ou argumento específico, deve ser informado neste campo o identificador do motivo da inadmissão do recurso.
- As opções de motivos de inadmissão estão listadas e explicadas no título Verificações Preliminares de Inadmissão, acima.

### pedidos[] - Pedidos

##### texto - Texto do Pedido
- Informe o texto conciso que descreve o pedido de mérito recursal
- Esse texto deve ser copiado do documento ipsis litteris, do documento marcado como <pedidos-do-recurso-e-argumentos>.

##### dispositivo
- O pedido pode ter como dispositivo uma das seguintes opções: SUSPENDER, NEGAR_SEGUIMENTO, ENCAMINHAR_PARA_RETRATACAO, ADMITIR, INADIMITIR, DESCONSIDERAR. Ainda existe a possibilidade de o pedido não ter dispositivo definido, caso em que esse campo deve ser deixado em branco.
- Se foi identificado um tema, as opções SUSPENDER, NEGAR_SEGUIMENTO ou ENCAMINHAR_PARA_RETRATACAO devem ser utilizadas conforme o caso.
- Se foi identificado um ou mais motivos de inadmissão, a opção INADIMITIR deve ser utilizada.
- Se não houver conclusão sobre o pedido, deixe esse campo em branco.
- Se um pedido anterior já foi marcado com SUSPENDER, e não houver tema ou motivo de inadmissão específico para o pedido atual, deixe esse campo em branco.

##### tema - Tema do Pedido
- Quando o dispositivo for SUSPENDER, NEGAR_SEGUIMENTO ou ENCAMINHAR_PARA_RETRATACAO, deve ser informado neste campo o identificador do tema que poderá ser obtido no documento marcado como <pesquisa-de-temas>. Caso a análise de temas não tenha informado o tema para suspensão, negativa de seguimento ou encaminhamento para retratação, deixe esse campo em branco.
- O identificador do tema tem o formato "stj-rr-123" ou "stf-rg-456", conforme o tribunal e o tipo de tema. Ele pode ser encontrado no documento marcado como <pesquisa-de-temas> em passagens como por exemplo: (ID: stf-rg-123) ou (ID: stj-rr-456).

##### motivo[] - Motivo da Inadmissão
- Quando o dispositivo for INADIMITIR, deve ser informado neste campo o identificador do motivo da inadmissão do recurso.
- Caso o pedido de inadmissão não tenha um motivo específico informado no documento marcado como <pesquisa-de-temas>, deixe esse campo em branco.
- As opções de motivos de inadmissão estão listadas e explicadas no título Juízo de Admissibilidade, acima.

#### argumentos[] - Argumentos do Pedido
- Liste os fundamentos jurídicos apresentados para embasar o pedido

##### texto - Texto do Argumento
- Esse texto deve ser copiado do documento marcado como <pedidos-do-recurso-e-argumentos>.

##### dispositivo
- Se desejar informar um dispositivo especificamente para o argumento, preencha este campo. Caso contrário, deixe em branco.
- Se o pedido ao qual o argumento pertence tiver o campo dispositivo preenchido com SUSPENDER, NEGAR_SEGUIMENTO ou ENCAMINHAR_PARA_RETRATACAO, deixe esse campo em branco.

##### tema - Tema do Pedido
- Caso o campo dispositivo do argumento tenha sido preenchido com SUSPENDER, NEGAR_SEGUIMENTO ou ENCAMINHAR_PARA_RETRATACAO, faça conforme acima, mas para o argumento específico, ou deixe em branco.

##### motivo[] - Motivo da Inadmissão
- Caso o campo dispositivo do argumento tenha sido preenchido com INADIMITIR, faça conforme acima, mas para o argumento específico, ou deixe em branco.
- As opções de motivos de inadmissão estão listadas e explicadas no título Juízo de Admissibilidade, acima.


# FORMAT
AAA
{% if motivoGeral %}**Motivo(s) de Inadmissão Geral:** {{ motivoGeral | join(", ") }}
{% else %}
{% for d in pedidos %}{% set outerIndex = loop.index %}**Pedido {{loop.index}}:** {{ d.texto }}

Argumentos:{% for a in d.argumentos %}
{{loop.index}}. {{ a.texto }}{% endfor %}
    
{% endfor %}
{% endif %}