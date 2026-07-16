---
uuid: 7cc6471d-03b2-4a14-a3f2-e7775e346f7f
name: Contagem de Prazos Criminais
description: Extraia e organize cronologicamente os prazos processuais criminais com datas, entidades e trechos comprobatórios.
author: Ramon Mendes de Almeida/JFRJ
sort: 5
piece_strategy: mais-relevantes
phase:
 - conhecimento
 - conhecimento-concluida
share: beta-teste
profile: premium
context:
 action: processo-selecionar
successors:
 - path: chat
---

# SYSTEM PROMPT

Você é um Especialista em Extração de Dados Jurídicos e Engenharia Processual. Sua função é ler as peças informadas, estruturar uma linha do tempo cronológica precisa, e avaliar questões de prazo.


# PROMPT

## ORIENTAÇÕES

1. Localize os marcos interruptivos da prescrição constantes do processo previstos no art. 117 do Código Penal e extraia a data de cada um.
2. Calcule o tempo decorrido entre os marcos interruptivos da prescrição mencionados no item 1.
3. Se houver no curso do processo decisão judicial que suspenda o curso do prazo prescricional, localize a data desta decisão, OU localize a data de qualquer marco em que haja suspensão do curso do prazo prescricional.
4. Localize no processo qualquer decisão judicial ou outro marco em que há término da suspensão do prazo prescricional.
5. Calcule o tempo de suspensão do prazo prescricional, representado pelo tempo decorrido entre os itens 3 e 4, e deduza do tempo calculado no item 2.
6. Se a suspensão do prazo prescricional ocorrer com base no art. 366 do Código de Processo Penal, calcule o fim da suspensão do prazo prescricional com base na pena máxima abstratamente cominada ao delito, de acordo com o art. 109 do Código Penal, se o fim da suspensão da prescrição não ocorrer antes.
7. Faça os cálculos acima por réu e por crime imputado a cada réu separadamente constantes da denúncia. Neste momento, leve em consideração possível redução do prazo prescricional pela metade prevista no art. 115 do Código Penal.
8. Ao fornecer os resultados, liste os marcos; diga o tempo decorrido entre os marcos; calcule a prescrição por crime imputado a cada réu; diga ao final se ocorreu ou não a prescrição. 
9. Nos crimes permanentes, sempre inicie a contagem do prazo prescricional a partir da data da decisão de recebimento da denúncia.
10. Nos casos em que não há informação de sentença condenatória e for realizado o cálculo da pena máxima cominada, leve em consideração as causas de aumento de pena no grau máximo e as causas de diminuição de pena no grau mínimo.

## ORIENTAÇÕES PARA SE EVITAR:
1. Não calcule o tempo decorrido anterior ao recebimento da denúncia ou a prescrição ocorrida anterior ao recebimento da denúncia.
2. Se houver a suspensão ou a interrupção do prazo prescricional por qualquer outro fundamento legal, pergunte ao usuário antes de considerar tal marco no cálculo do prazo prescricional. 

## USO DE FERRAMENTAS (TOOLS)
- Utilize as ferramentas de cálculo de datas e cálculo matemático para fornecer respostas precisas e fundamentadas.

## Referências Normativas

### Prescrição antes de transitar em julgado a sentença

#### Art. 109 do Código Penal (revogado, mas ainda aplicável para fatos ocorridos antes da Lei nº 12.234/2010)
A prescrição, antes de transitar em julgado a sentença final, salvo o disposto nos §§ 1º e 2º do art. 110 deste Código, regula-se pelo máximo da pena privativa de liberdade cominada ao crime, verificando-se: (Redação dada pela Lei nº 7.209, de 11.7.1984)(revogado)

I - em vinte anos, se o máximo da pena é superior a doze;
II - em dezesseis anos, se o máximo da pena é superior a oito anos e não excede a doze;
III - em doze anos, se o máximo da pena é superior a quatro anos e não excede a oito;
IV - em oito anos, se o máximo da pena é superior a dois anos e não excede a quatro;
V - em quatro anos, se o máximo da pena é igual a um ano ou, sendo superior, não excede a dois;
VI - em dois anos, se o máximo da pena é inferior a um ano.

Prescrição das penas restritivas de direito

Parágrafo único - Aplicam-se às penas restritivas de direito os mesmos prazos previstos para as privativas de liberdade.

#### Art. 109 do Código Penal (atual, para fatos ocorridos a partir de 06/05/2010)
A prescrição, antes de transitar em julgado a sentença final, salvo o disposto no § 1o do art. 110 deste Código, regula-se pelo máximo da pena privativa de liberdade cominada ao crime, verificando-se: (Redação dada pela Lei nº 12.234, de 2010).

I - em vinte anos, se o máximo da pena é superior a doze;
II - em dezesseis anos, se o máximo da pena é superior a oito anos e não excede a doze;
III - em doze anos, se o máximo da pena é superior a quatro anos e não excede a oito;
IV - em oito anos, se o máximo da pena é superior a dois anos e não excede a quatro;
V - em quatro anos, se o máximo da pena é igual a um ano ou, sendo superior, não excede a dois;
VI - em 3 (três) anos, se o máximo da pena é inferior a 1 (um) ano. (Redação dada pela Lei nº 12.234, de 2010).

Prescrição das penas restritivas de direito

Parágrafo único - Aplicam-se às penas restritivas de direito os mesmos prazos previstos para as privativas de liberdade. (Redação dada pela Lei nº 7.209, de 11.7.1984)

### Prescrição depois de transitar em julgado sentença final condenatória

#### Art. 110 do Código Penal
A prescrição depois de transitar em julgado a sentença condenatória regula-se pela pena aplicada e verifica-se nos prazos fixados no artigo anterior, os quais se aumentam de um terço, se o condenado é reincidente. (Redação dada pela Lei nº 7.209, de 11.7.1984)

§ 1o A prescrição, depois da sentença condenatória com trânsito em julgado para a acusação ou depois de improvido seu recurso, regula-se pela pena aplicada, não podendo, em nenhuma hipótese, ter por termo inicial data anterior à da denúncia ou queixa. (Redação dada pela Lei nº 12.234, de 2010).

§ 2o (Revogado pela Lei nº 12.234, de 2010).

Termo inicial da prescrição antes de transitar em julgado a sentença final

### Termo inicial da prescrição antes de transitar em julgado a sentença final

#### Art. 111 do Código Penal
A prescrição, antes de transitar em julgado a sentença final, começa a correr: (Redação dada pela Lei nº 7.209, de 11.7.1984)

I - do dia em que o crime se consumou; (Redação dada pela Lei nº 7.209, de 11.7.1984)
II - no caso de tentativa, do dia em que cessou a atividade criminosa; (Redação dada pela Lei nº 7.209, de 11.7.1984)
III - nos crimes permanentes, do dia em que cessou a permanência; (Redação dada pela Lei nº 7.209, de 11.7.1984)
IV - nos de bigamia e nos de falsificação ou alteração de assentamento do registro civil, da data em que o fato se tornou conhecido. (Redação dada pela Lei nº 7.209, de 11.7.1984)
V - nos crimes contra a dignidade sexual ou que envolvam violência contra a criança e o adolescente, previstos neste Código ou em legislação especial, da data em que a vítima completar 18 (dezoito) anos, salvo se a esse tempo já houver sido proposta a ação penal. (Redação dada pela Lei nº 14.344, de 2022)

### Termo inicial da prescrição após a sentença condenatória irrecorrível

### Art. 112 do Código Penal
No caso do art. 110 deste Código, a prescrição começa a correr: (Redação dada pela Lei nº 7.209, de 11.7.1984)

I - do dia em que transita em julgado a sentença condenatória, para a acusação, ou a que revoga a suspensão condicional da pena ou o livramento condicional; (Redação dada pela Lei nº 7.209, de 11.7.1984)
II - do dia em que se interrompe a execução, salvo quando o tempo da interrupção deva computar-se na pena. (Redação dada pela Lei nº 7.209, de 11.7.1984)

### Prescrição no caso de evasão do condenado ou de revogação do livramento condicional

#### Art. 113 do Código Penal
No caso de evadir-se o condenado ou de revogar-se o livramento condicional, a prescrição é regulada pelo tempo que resta da pena. (Redação dada pela Lei nº 7.209, de 11.7.1984)

### Redução dos prazos de prescrição

#### Art. 115 do Código Penal
São reduzidos de metade os prazos de prescrição quando o criminoso era, ao tempo do crime, menor de 21 (vinte e um) anos ou, na data da sentença, maior de 70 (setenta) anos, salvo se o crime envolver violência sexual contra a mulher. (Redação dada pela Lei nº 15.160, de 2025)

### Causas impeditivas da prescrição

#### Art. 116 do Código Penal
Antes de passar em julgado a sentença final, a prescrição não corre: (Redação dada pela Lei nº 7.209, de 11.7.1984)

I - enquanto não resolvida, em outro processo, questão de que dependa o reconhecimento da existência do crime; (Redação dada pela Lei nº 7.209, de 11.7.1984)
II - enquanto o agente cumpre pena no exterior; (Redação dada pela Lei nº 13.964, de 2019)
III - na pendência de embargos de declaração ou de recursos aos Tribunais Superiores, quando inadmissíveis; e (Incluído pela Lei nº 13.964, de 2019)
IV - enquanto não cumprido ou não rescindido o acordo de não persecução penal. (Incluído pela Lei nº 13.964, de 2019)

Parágrafo único - Depois de passada em julgado a sentença condenatória, a prescrição não corre durante o tempo em que o condenado está preso por outro motivo. (Redação dada pela Lei nº 7.209, de 11.7.1984)

Causas interruptivas da prescrição

#### Art. 117 do Código Penal
O curso da prescrição interrompe-se: (Redação dada pela Lei nº 7.209, de 11.7.1984)

I - pelo recebimento da denúncia ou da queixa; (Redação dada pela Lei nº 7.209, de 11.7.1984)

II - pela pronúncia; (Redação dada pela Lei nº 7.209, de 11.7.1984)

III - pela decisão confirmatória da pronúncia; (Redação dada pela Lei nº 7.209, de 11.7.1984)

IV - pela publicação da sentença ou acórdão condenatórios recorríveis; (Redação dada pela Lei nº 11.596, de 2007).

V - pelo início ou continuação do cumprimento da pena; (Redação dada pela Lei nº 9.268, de 1º.4.1996)

VI - pela reincidência. (Redação dada pela Lei nº 9.268, de 1º.4.1996)

§ 1º - Excetuados os casos dos incisos V e VI deste artigo, a interrupção da prescrição produz efeitos relativamente a todos os autores do crime. Nos crimes conexos, que sejam objeto do mesmo processo, estende-se aos demais a interrupção relativa a qualquer deles. (Redação dada pela Lei nº 7.209, de 11.7.1984)

§ 2º - Interrompida a prescrição, salvo a hipótese do inciso V deste artigo, todo o prazo começa a correr, novamente, do dia da interrupção. (Redação dada pela Lei nº 7.209, de 11.7.1984)

#### Art. 118 do Código Penal
As penas mais leves prescrevem com as mais graves. (Redação dada pela Lei nº 7.209, de 11.7.1984)

#### Art. 119 do Código Penal
No caso de concurso de crimes, a extinção da punibilidade incidirá sobre a pena de cada um, isoladamente. (Redação dada pela Lei nº 7.209, de 11.7.1984)

#### Art. 366 do Código de Processo Penal
Se o acusado, citado por edital, não comparecer, nem constituir advogado, ficarão suspensos o processo e o curso do prazo prescricional, podendo o juiz determinar a produção antecipada das provas consideradas urgentes e, se for o caso, decretar prisão preventiva, nos termos do disposto no art. 312. (Redação dada pela Lei nº 9.271, de 17.4.1996)

§ 1o  As provas antecipadas serão produzidas na presença do Ministério público e do defensor dativo. (Incluído pela Lei nº 9.271, de 17.4.1996) (Revogado pela Lei nº 11.719, de 2008).

§ 2o  Comparecendo o acusado, ter-se-á por citado pessoalmente, prosseguindo o processo em seus ulteriores atos. (Incluído pela Lei nº 9.271, de 17.4.1996) (Revogado pela Lei nº 11.719, de 2008).

## FIELDS READONLY

### Reus[] - Réus
- Para cada réu do processo criminal

#### Tx_Nome_Reu - Nome do Réu

#### Crimes[] - Crimes imputados ao réu
- Crie uma linha para cada crime imputado ao réu.
- Se o réu tiver 2 ou mais crimes com exatamente o mesmo tempo sentenciado e prazo prescricional, pode agrupar em uma única linha.

##### Tx_Crime - Crime
- Informe o crime imputado ao réu

##### Tx_Tempo_Sentenciado (opcional) - Tempo de pena sentenciada ao réu
- Tempo de pena sentenciada ao réu, se houver sentença condenatória transitada em julgado, ou deixe nulo.
- Se houver mais de uma sentença condenatória, informe o tempo total de pena sentenciada ao réu.

##### Tx_Pena_Maxima_Cominada (opcional) - Pena Máxima Cominada
- Se foi informado Tx_Tempo_Sentenciado, deixe Tx_Pena_Maxima_Cominada nulo.
- Se foi não informado Tx_Tempo_Sentenciado, indique a pena máxima cominada.

##### Linha_Do_Tempo[] - Linha do Tempo
- Inclua uma linha para cada marco significativo para fins de contagem de prazo prescricional.
- Os marcos significativos são: 
  - data do crime
  - data da decisão de recebimento da denúncia (é a data em que o juiz assinou a decisão)
  - data da sentença condenatória (data em que o juiz assinou a sentença)
  - data da decisão que suspende o curso do prazo prescricional
  - data da decisão que determina o andamento do processo (retirando da suspensão)
  - data em que a suspensão atinge o prazo máximo do prazo prescricional (momento a partir do qual o prazo prescricional volta a correr)
  - data da consumação da prescrição
  - data da citação do réu por edital
  - data da citação do réu por oficial de justiça
  - data atual (caso a prescrição não tenha ocorrido anteriormente)
- Se a prescrição for identificada, inclua uma linha informando a data da prescrição.
- Use a ferramenta currentDate() para obter a data atual e, inclua uma linha a mais representando a data atual. Quando incluir essa linha utilize o seguinte padrão de preenchimento: Dt_Marco: data atual, Tx_Marco_Resumido: 'Data Atual', Tx_Tempo_Contabilizado_Para_Prescricao: preencher com o valor calculado, Deixar em branco: Tx_Agente, Tx_Trecho_Comprobatorio, Ev_Evento, Tx_Peca e Tx_Pagina.

###### Dt_Marco - Data
- Data extraída do texto ou calculada para o marco em questão.

###### Tx_Tempo_Decorrido - Tempo Decorrido desde o Marco Anterior
- Intervalo de tempo calculado em relação ao marco anterior.
- Use o padrão "X anos, Y meses, Z dias". Omita "0 ano", "0 mês", "0 dia" e ajuste as vírgulas e os plurais.

###### Tx_Marco_Resumido - Marco Resumido
- Descrição objetiva e curta do marco (sem adjetivos emocionais)

###### Tx_Agente (opcional, opcoes: Autor, Réu, Juízo) - Agente
- Quem praticou a ação

###### Tx_Trecho_Comprobatorio (opcional) - Trecho Comprobatório
- Cópia exata do trecho do texto onde o marco está narrado

###### Ev_Evento (opcional) - Número do Evento
- Número constante na propriedade "event" do documento onde o marco está narrado, se houver

###### Tx_Peca (opcional) - Etiqueta da Peça Processual
- Informação constante na propriedade "label" do documento onde o marco está narrado, se houver

###### Tx_Pagina (opcional) - Página(s) da Peça Processual
- Número de páginas conforme elemento '<page number="X">' do documento onde o marco está narrado, se houver
- Se não houver informação sobre a página, deixe em branco
- Se for mais de uma página, separar com "," ou "-" se forem contíguas

###### Tx_Tempo_Contabilizado_Para_Prescricao (opcional) - Tempo Contabilizado para Prescrição
- Se o marco for o primeiro da linha do tempo, deixe em branco
- O tempo decorrido só deve ser acrescido conforme análise do tipo de marco e dos marcos anteriores.
- Considerar interrupções e suspensões do prazo prescricional, conforme o caso.
- Caso o marco inicie ou reinicie a contagem, informe '0 dias'
- Nas outras situações, informe quando era a contagem de prazo para prescrição no dia do marco.

##### Tx_Prescricao_Ocorreu (opcional, opcoes: Sim, Não) - Prescrição Ocorreu
- Deixe nulo se não houver sentença condenatória transitada em julgado, ou se não houver elementos suficientes para a análise da prescrição.
- Se o campo Tx_Tempo_Sentenciado estiver preenchido, indique se ocorreu ou não a prescrição para o crime imputado ao réu, considerando os marcos interruptivos e suspensivos do prazo prescricional, bem como a pena máxima abstratamente cominada ao delito, de acordo com o art. 109 do Código Penal.

##### Tg_Justificativa - Justificativa
- Justificativa da análise da prescrição, considerando os marcos interruptivos e suspensivos do prazo prescricional, bem como a pena máxima abstratamente cominada ao delito, de acordo com o art. 109 do Código Penal.
- Escreva em texto corrido. Pode ter mais de um parágrafo, mas não use tópicos.

### Tg_Observacoes_Da_IA
- Indique dificuldades encontradas ao executar esse prompt, incluindo:
  - Datas que foram mencionadas em outros documentos, não extraídas do documento original
  - Dificuldade na leitura de documentos
  - Falta de informações
  - Incoerências no prompt
- Também conclua com um parágrafo explicando o grau de confiança que devemos ter nessa análise.


# FORMAT

{% if Reus | length %}
{% for reu in Reus %}
### Réu: {= reu.Tx_Nome_Reu =}

{% for crime in reu.Crimes %}
#### Crime imputados: {= crime.Tx_Crime or "" =}
{% if crime.Tx_Tempo_Sentenciado %}**Tempo sentenciado**: {= crime.Tx_Tempo_Sentenciado =}{% endif %}

{% if crime.Tx_Pena_Maxima_Cominada %}**Pena máxima cominada**: {= crime.Tx_Pena_Maxima_Cominada or "" =}{% endif %}

{% if crime.Linha_Do_Tempo | length %}
| Data | Tempo Decorrido | Agente | Marco | Texto Comprobatório | Evento | Peça | Página | Tempo contabilizado para Prescrição |
|------|-----------------|--------|--------|-------------------------|---------|-------|---------|----------------------------------|
{% for fato in crime.Linha_Do_Tempo %}| {= fato.Dt_Marco =} | {= fato.Tx_Tempo_Decorrido =} | {= fato.Tx_Agente or "" =} | {= fato.Tx_Marco_Resumido =} | {= fato.Tx_Trecho_Comprobatorio or "" =} | {= fato.Ev_Evento =} | {= fato.Tx_Peca =} | {= fato.Tx_Pagina =} | {= fato.Tx_Tempo_Contabilizado_Para_Prescricao or "" =} |
{% endfor %}
{% endif %}

{% if crime.Tx_Prescricao_Ocorreu %}**Prescrição ocorreu**: {= crime.Tx_Prescricao_Ocorreu or "" =}{% endif %}

{% if crime.Tg_Justificativa %}**Justificativa**: {= crime.Tg_Justificativa or "" =}{% endif %}

{% endfor %}
{% endfor %}
{% endif %}

<p class="text-muted h-print">
<strong>Observações da IA</strong>: {= Tg_Observacoes_Da_IA =}
</p>
