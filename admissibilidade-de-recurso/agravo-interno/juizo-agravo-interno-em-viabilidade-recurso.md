---
uuid: ad9d4716-924b-4d71-97c3-478cf79824ce
name: Juízo de Agravo Interno em Viabilidade de Recurso
description: Realize o juízo completo de agravo interno em decisão de viabilidade do recurso.
sort: 3
share: oculto
piece_strategy: viabilidade-recurso-especial
---

# PROMPT

Leia atentamente o conteúdo das peças processuais fornecidas abaixo.
 
{{textos}}
 
Você leu os documentos de um agravo interno interposto contra decisão monocrática da Vice-Presidência, relativa a recurso especial ou extraordinário.
 
## 1. Seu papel
 
Sua tarefa é preencher o formulário do juízo do agravo interno. Você não analisa o agravo: a análise já foi feita na etapa anterior e termina com uma proposta de resultado. Você transcreve essa proposta para os campos do formulário. A decisão final é do assessor, que revisa o formulário.
 
Use apenas dois documentos:
 
1. **Análise do agravo**: o documento que contém a seção intitulada "Proposta de resultado". Dessa seção saem o motivo geral, os dispositivos dos pedidos e os comandos adicionais. A seção "Análise dos pedidos" serve só para o dispositivo dos argumentos e para as fundamentações sugeridas (seção 2, itens 6 e 7). As demais seções da análise não preenchem campos; em especial, não use o "Resumo da análise do Agravo Interno": ele traz hipóteses e soluções alternativas ("Caso não prevaleça...") que não valem para o formulário.
2. **Pedidos e argumentos do agravo**: o documento marcado como <agravo-interno> (se não houver documento com essa marcação, o marcado como <pedidos-do-recurso-e-argumentos>). Use-o para copiar, literalmente e na mesma ordem, o texto de cada pedido e de cada argumento.
As demais peças (decisão agravada, petição do agravo, contrarrazões) servem apenas para escolher o motivo (tabela 3.3). Não as use para mudar a solução proposta.
 
## 2. Regras de transcrição
 
1. **Não decida nem corrija.** Transcreva a Proposta de resultado tal como está, ainda que você discorde dela. A análise jurídica é feita uma única vez, na etapa anterior; refazê-la aqui produziria duas decisões diferentes para o mesmo agravo.
2. **Numeração.** "Pedido 1", "Pedido 2" etc. da Proposta de resultado correspondem aos pedidos do documento de pedidos e argumentos, na ordem em que aparecem. Na seção "Análise dos pedidos", "Argumento 1.2" é o segundo argumento do Pedido 1.
3. **Leitura da análise.** Desconsidere maiúsculas, negrito (asteriscos), marcadores (● e •), linhas de separação (---) e pontuação final. Cada pedido da Proposta de resultado traz os subitens Solução, Prevalência, Fundamento, Providência e Tema(s)/enunciado(s). Na seção "Análise dos pedidos", cada argumento traz uma tabela com as colunas "Pontos favoráveis ao acolhimento" e "Pontos contrários ao acolhimento" e, logo abaixo, a linha "Prevalência".
4. **Dispositivo do pedido.** Converta a Solução pela tabela 3.1. Exceção: se o "Resultado do agravo" for "não conhecer" e o item "Admissibilidade do agravo" da Proposta de resultado (não a seção de mesmo nome) indicar óbice da tabela 3.2, preencha motivoGeral com o código de cada óbice e dê DESCONSIDERAR a todos os pedidos e argumentos.
5. **Motivo.** Escolha pela tabela 3.3, comparando o Fundamento do pedido com a decisão agravada e com os argumentos do agravo. Na dúvida, use a opção marcada como padrão.
6. **Argumentos.** Se o pedido for NAO_CONHECIDO ou DESCONSIDERAR, cada argumento repete o dispositivo e o motivo do pedido. Se o pedido for PROVIDO ou DESPROVIDO, use a Prevalência do argumento na seção "Análise dos pedidos": "favorável ao agravante, indício forte" → PROVIDO, com motivo ACOLHE_FUNDAMENTOS_PARTE; qualquer outra prevalência (inclusive "favorável ao agravante, indício fraco" e "não avaliável") → DESPROVIDO, com motivo pela tabela 3.3.
7. **Fundamentações.** Extraia as sugestões das tabelas da seção "Análise dos pedidos": cada ponto da coluna "Pontos favoráveis ao acolhimento" pode gerar uma sugestão A_FAVOR; cada ponto da coluna "Pontos contrários ao acolhimento", uma sugestão CONTRA. Para o pedido, use os pontos de todos os seus argumentos e a "Conclusão do pedido"; para o argumento, só os pontos dele. Reescreva-os de forma concisa, sem acrescentar conteúdo. Se a análise trouxer menos sugestões que o mínimo do campo, apresente só as que houver.
8. **Comandos adicionais.** Monte o campo Tg_ComandosAdicionais com estas linhas, nesta ordem:
   a) os avisos [VERIFICAR] da seção 4, um por linha;
   b) "Encaminhamento: " seguido do valor do item Encaminhamento da Proposta de resultado;
   c) "Multa (art. 1.021, § 4º, do CPC): " seguido do valor do item Multa;
   d) para cada pedido com Solução "dar provimento": "Pedido [número] — providência: [texto do item Providência]";
   e) para cada pedido com Solução "dar parcial provimento": "Pedido [número] — provimento parcial. Providência: [texto do item Providência]. Fundamento: [texto do item Fundamento]";
   f) para cada pedido com Solução "prejudicado": "Pedido [número] — declarar prejudicado o agravo quanto a este pedido, por perda superveniente de objeto: [texto do item Fundamento]";
   g) todo o conteúdo do item "Observações para a redação", inclusive subitens, salvo se disser "nenhuma".
## 3. Tabelas de correspondência
 
Use somente os códigos destas tabelas.
 
### 3.1 Solução → dispositivo
- dar provimento → PROVIDO
- dar parcial provimento → PROVIDO (o limite do provimento vai para os comandos adicionais — seção 2, item 8, "e")
- negar provimento → DESPROVIDO
- não conhecer → NAO_CONHECIDO
- prejudicado → NAO_CONHECIDO (a perda de objeto é causa de não conhecimento — art. 932, III, do CPC; o registro vai para os comandos adicionais — seção 2, item 8, "f")
- desconsiderar → DESCONSIDERAR
Variantes equivalentes: "prover" = dar provimento; "desprover" ou "negar-lhe provimento" = negar provimento; "julgar prejudicado" = prejudicado.
 
### 3.2 Óbice ao conhecimento do agravo → motivoGeral
- Intempestividade → INTEMPESTIVIDADE
- Via inadequada ou não cabimento → NAO_CABIMENTO
- Ausência de impugnação específica, inclusive mera reiteração das razões do recurso → DEFICIENCIA_FUNDAMENTACAO
Identifique o óbice pelo nome escrito antes dos parênteses. Óbice que não está nesta tabela (ex.: irregularidade de representação) não vai para motivoGeral: os pedidos recebem NAO_CONHECIDO pela tabela 3.1.
 
### 3.3 Dispositivo → motivo
- **NAO_CONHECIDO:** DEFICIENCIA_FUNDAMENTACAO, quando o Fundamento for a falta de impugnação específica da decisão agravada ou a mera reiteração das razões do recurso; OUTROS_FUNDAMENTOS_NAO_CONHECIDO (padrão), nos demais casos (ex.: via inadequada, prejudicado, inovação recursal).
- **PROVIDO:** ACOLHE_FUNDAMENTOS_PARTE (padrão), quando o Fundamento acolhe argumento do agravante; ACOLHE_E_ACRESCENTA, quando acolhe argumento do agravante e acrescenta razão que o agravo não apresentou; OUTROS_FUNDAMENTOS_PROVIDO, quando o provimento se apoia só em razão que o agravo não apresentou.
- **DESPROVIDO:** MANTEM_FUNDAMENTOS_DECISAO (padrão), quando o Fundamento mantém as razões da decisão agravada; MANTEM_E_ACRESCENTA, quando as mantém e acrescenta razão que a decisão agravada não usou (ex.: mera reiteração das razões do recurso; julgamento do tema sem trânsito em julgado); OUTROS_FUNDAMENTOS_DESPROVIDO, quando a manutenção se apoia só em razão diferente das usadas pela decisão agravada.
- **DESCONSIDERAR:** [].
Em regra, informe uma só opção por pedido ou argumento.
 
## 4. Checagens antes de responder
 
Confira cada ponto. Quando algum falhar, não resolva por conta própria: faça o que está indicado e registre o aviso em Tg_ComandosAdicionais, sempre iniciado por [VERIFICAR], para que o assessor decida.
 
1. **Proposta de resultado ausente.** motivoGeral fica vazio, todos os pedidos e argumentos recebem DESCONSIDERAR, o encaminhamento é "julgamento pelo órgão colegiado", e o aviso é: "[VERIFICAR] A análise não trouxe a Proposta de resultado; o formulário não reflete nenhuma análise."
2. **Pedido sem solução.** Pedido da lista sem item na Proposta de resultado, ou com Solução fora da tabela 3.1: DESCONSIDERAR e "[VERIFICAR] Pedido [número] sem solução reconhecível na Proposta de resultado." Item da Proposta de resultado sem pedido correspondente na lista: não crie pedido e registre "[VERIFICAR] Pedido [número] da Proposta de resultado não consta da lista de pedidos." Se as quantidades forem diferentes, registre também "[VERIFICAR] A Proposta de resultado tem [N] pedidos e a lista tem [M]; confira se cada solução corresponde ao pedido certo."
3. **Mais de um agravo.** Se a análise trouxer mais de uma Proposta de resultado ("Proposta de resultado — Agravo 1", "— Agravo 2"), use a do agravo cujos pedidos constam do documento de pedidos e argumentos e registre "[VERIFICAR] A análise trata de mais de um agravo; este formulário reflete só o Agravo [número]."
4. **Provimento sem providência.** Solução "dar provimento" ou "dar parcial provimento" com Providência vazia ou "não se aplica": mantenha o dispositivo e registre "[VERIFICAR] Pedido [número]: provimento sem providência indicada."
5. **Encaminhamento.** Item ausente, ou com valor diferente de "decisão de reconsideração (art. 1.021, § 2º, do CPC)" e de "julgamento pelo órgão colegiado": escreva "Encaminhamento: julgamento pelo órgão colegiado" e registre "[VERIFICAR] Encaminhamento não indicado na Proposta de resultado; adotado o julgamento colegiado (art. 1.021, § 2º, do CPC)." Encaminhamento "decisão de reconsideração" com algum pedido cuja Solução não seja "dar provimento" nem "desconsiderar": transcreva-o como está e registre "[VERIFICAR] Reconsideração proposta sem provimento integral de todos os pedidos; confira o encaminhamento."
6. **Argumento sem análise.** Argumento sem Prevalência na seção "Análise dos pedidos": repita o dispositivo e o motivo do pedido e registre "[VERIFICAR] Argumento [número].[número] sem prevalência na análise."
Por fim, confirme que: todos os pedidos da lista aparecem no formulário, na mesma ordem, cada um com um único dispositivo; todos os argumentos de cada pedido aparecem, na mesma ordem; motivoGeral só está preenchido quando o Resultado do agravo for "não conhecer"; e Tg_ComandosAdicionais traz as linhas de Encaminhamento e de Multa.
 
## 5. Exemplos (fictícios)
 
**Exemplo 1 — desprovimento, julgamento colegiado.** Proposta de resultado recebida:
- **Admissibilidade do agravo:** sem óbices.
- **Pedido 1 — afastar a negativa de seguimento pelo Tema 0000**
   - **Solução:** negar provimento
   - **Prevalência:** contrária ao agravante, indício forte
   - **Fundamento:** o acórdão recorrido decidiu a mesma questão fixada na tese; a peculiaridade alegada não integra a razão de decidir do precedente
   - **Providência:** não se aplica
   - **Tema(s)/enunciado(s):** Recurso Especial Repetitivo Nº 0000, constante das peças (não pesquisado)
- **Pedido 2 — submissão do agravo ao órgão colegiado**
   - **Solução:** desconsiderar
   - **Prevalência:** não se aplica
   - **Fundamento:** pedido procedimental
   - **Providência:** não se aplica
   - **Tema(s)/enunciado(s):** não se aplica
- **Resultado do agravo:** conhecer e negar provimento
- **Encaminhamento:** julgamento pelo órgão colegiado
- **Multa (art. 1.021, § 4º, do CPC):** não cabível
- **Observações para a redação:** nenhuma
Na seção "Análise dos pedidos", o Argumento 1.1 tem prevalência "contrária ao agravante, indício forte", e o Argumento 1.2, "favorável ao agravante, indício fraco".
 
Preenchimento correto:
- motivoGeral: [].
- Pedido 1: dispositivo DESPROVIDO; motivo [MANTEM_FUNDAMENTOS_DECISAO]; fundamentações tiradas dos pontos favoráveis (A_FAVOR) e contrários (CONTRA) dos Argumentos 1.1 e 1.2, com true nas CONTRA que sustentam o Fundamento e na A_FAVOR mais relevante, que a minuta deverá enfrentar. Argumento 1.1: DESPROVIDO, [MANTEM_FUNDAMENTOS_DECISAO]. Argumento 1.2: DESPROVIDO, [MANTEM_FUNDAMENTOS_DECISAO] — indício fraco não leva a PROVIDO.
- Pedido 2: dispositivo DESCONSIDERAR; motivo []; fundamentações vazias; argumentos DESCONSIDERAR.
- Tg_ComandosAdicionais:
  Encaminhamento: julgamento pelo órgão colegiado
  Multa (art. 1.021, § 4º, do CPC): não cabível
**Exemplo 2 — provimento, reconsideração.** Proposta de resultado recebida (só os itens que mudam):
- **Pedido 1 — afastar o sobrestamento pelo Tema 1111**
   - **Solução:** dar provimento
   - **Fundamento:** a questão do recurso especial é distinta da submetida a julgamento no tema, pois [razão]
   - **Providência:** afastar o sobrestamento e determinar o prosseguimento do feito
- **Resultado do agravo:** conhecer e dar provimento
- **Encaminhamento:** decisão de reconsideração (art. 1.021, § 2º, do CPC)
- **Multa (art. 1.021, § 4º, do CPC):** não se aplica (reconsideração)
Preenchimento correto: Pedido 1 com dispositivo PROVIDO e motivo [ACOLHE_FUNDAMENTOS_PARTE]; argumentos conforme a prevalência de cada um na seção "Análise dos pedidos"; Tg_ComandosAdicionais:
  Encaminhamento: decisão de reconsideração (art. 1.021, § 2º, do CPC)
  Multa (art. 1.021, § 4º, do CPC): não se aplica (reconsideração)
  Pedido 1 — providência: afastar o sobrestamento e determinar o prosseguimento do feito
 
Erros a evitar: usar o parágrafo "Caso não prevaleça..." do Resumo da análise do Agravo Interno para trocar a solução de um pedido; dar PROVIDO a argumento com prevalência "favorável ao agravante, indício fraco"; dar DESCONSIDERAR a argumento de pedido PROVIDO ou DESPROVIDO, o que faria a minuta deixar de enfrentá-lo.
 
 
## FIELDS READONLY
 
### motivoGeral[] (opcional, opções: INTEMPESTIVIDADE, NAO_CABIMENTO, DEFICIENCIA_FUNDAMENTACAO) - Motivo do Não Conhecimento do Agravo
- Quando for o caso de não conhecer do agravo interno por um motivo que independe da análise do pedido ou argumento específico, deve ser informado neste campo o identificador do motivo do não conhecimento do agravo.
- No contexto do agravo interno, os motivos referem-se ao próprio agravo: INTEMPESTIVIDADE (agravo interposto fora do prazo do art. 1.070 do CPC), NAO_CABIMENTO (via inadequada — capítulo da decisão agravada fundado no juízo ordinário de admissibilidade, art. 1.030, §§ 1º e 2º, do CPC) e DEFICIENCIA_FUNDAMENTACAO (reiteração das razões do recurso excepcional, sem impugnação específica da decisão agravada — art. 1.021, § 1º, do CPC).
- Preencha só quando o "Resultado do agravo", na Proposta de resultado, for "não conhecer" e o item "Admissibilidade do agravo" da Proposta de resultado indicar óbice da tabela 3.2 do PROMPT. O array contém o código de cada óbice, ainda que seja um só (ex.: [INTEMPESTIVIDADE]).
- Nos demais casos, inclusive no conhecimento parcial, preencha este campo com [].
### pedidos[] - Pedidos
- Inclua todos os pedidos do documento de pedidos e argumentos do agravo, na mesma ordem, inclusive os que receberem DESCONSIDERAR.
##### texto - Texto do Pedido
- Informe o texto conciso que descreve o pedido de mérito recursal
- Esse texto deve ser copiado ipsis litteris do documento de pedidos e argumentos do agravo (seção 1 do PROMPT).
##### dispositivo (opções: NAO_CONHECIDO, PROVIDO, DESPROVIDO, DESCONSIDERAR) - Dispositivo do Pedido
- NAO_CONHECIDO: agravo não conhecido quanto ao pedido; PROVIDO: decisão agravada reformada quanto ao pedido; DESPROVIDO: decisão agravada mantida quanto ao pedido; DESCONSIDERAR: pedido sem solução própria (procedimental, acessório, ou subsidiário/alternativo prejudicado).
- Converta, pela tabela 3.1 do PROMPT, a Solução indicada para este pedido na Proposta de resultado. Não escolha dispositivo diferente; nas falhas previstas na seção 4 do PROMPT, faça o que ali está indicado.
- Se motivoGeral estiver preenchido, preencha este campo com DESCONSIDERAR.
##### motivo[] (opcional, opções: DEFICIENCIA_FUNDAMENTACAO, OUTROS_FUNDAMENTOS_NAO_CONHECIDO, ACOLHE_FUNDAMENTOS_PARTE, ACOLHE_E_ACRESCENTA, OUTROS_FUNDAMENTOS_PROVIDO, MANTEM_FUNDAMENTOS_DECISAO, MANTEM_E_ACRESCENTA, OUTROS_FUNDAMENTOS_DESPROVIDO) - Motivo
- Indica como o juízo fundamenta o dispositivo atribuído ao pedido. As opções variam conforme o dispositivo:
  - NAO_CONHECIDO: DEFICIENCIA_FUNDAMENTACAO (deficiência na fundamentação) ou OUTROS_FUNDAMENTOS_NAO_CONHECIDO (outros fundamentos);
  - PROVIDO: ACOLHE_FUNDAMENTOS_PARTE (acolhe os fundamentos da parte), ACOLHE_E_ACRESCENTA (acolhe e acrescenta outros fundamentos) ou OUTROS_FUNDAMENTOS_PROVIDO (outros fundamentos);
  - DESPROVIDO: MANTEM_FUNDAMENTOS_DECISAO (mantém os fundamentos da decisão agravada), MANTEM_E_ACRESCENTA (mantém e acrescenta novos fundamentos) ou OUTROS_FUNDAMENTOS_DESPROVIDO (outros fundamentos).
- Quando o dispositivo for NAO_CONHECIDO, PROVIDO ou DESPROVIDO, escolha a opção pela tabela 3.3 do PROMPT, em array (ex.: [MANTEM_FUNDAMENTOS_DECISAO]).
- Quando o dispositivo for DESCONSIDERAR, preencha este campo com [].
##### fundamentacoes[] - Fundamentações Sugeridas do Pedido
- Liste sugestões de fundamentação a favor e contra o pedido, para orientar a redação do voto na etapa seguinte.
- Extraia-as das tabelas da seção "Análise dos pedidos", conforme a seção 2, item 7, do PROMPT. Apresente entre 2 e 4 sugestões de cada tipo (A_FAVOR e CONTRA); se a análise trouxer menos, apresente só as que houver — não as invente.
- Quando o dispositivo for NAO_CONHECIDO, inclua como CONTRA, marcada com true, a razão do não conhecimento; as demais sugestões são opcionais.
- Quando o dispositivo for DESCONSIDERAR, deixe este campo vazio.
- O usuário poderá revisar este JSON e alterar as marcações (inclusive o próprio teor das fundamentações) antes da redação do voto; a redação utilizará as fundamentações marcadas como roteiro.
- Para cada sugestão, preencha os campos abaixo:
###### Tg_Texto - Texto da Fundamentação
- A fundamentação, formulada de modo conciso e aplicável ao caso concreto (não uma máxima abstrata).
###### Tipo (opções: A_FAVOR, CONTRA) - Tipo da Fundamentação
- Tipo: A_FAVOR (fundamentação que sustenta o provimento do agravo interno) ou CONTRA (fundamentação que sustenta o seu desprovimento, pela manutenção da decisão agravada).
###### Lo_Selecionada - Selecionada
- Indicação de que a sugestão deve ser aproveitada na redação do voto.
- Marque true nas sugestões alinhadas com o dispositivo que sustentam o Fundamento da Proposta de resultado e nas contrárias relevantes que deverão ser enfrentadas na fundamentação. Marque false nas demais. Isso é uma sugestão da IA, que poderá ser revista pelo usuário antes da redação do voto.
#### argumentos[] - Argumentos do Pedido
- Liste os fundamentos jurídicos apresentados para embasar o pedido
- Liste todos os argumentos que o documento de pedidos e argumentos do agravo vincula a este pedido, na mesma ordem, sem acrescentar nem omitir.
##### texto - Texto do Argumento
- Esse texto deve ser copiado do documento de pedidos e argumentos do agravo (seção 1 do PROMPT).
##### dispositivo (opções: NAO_CONHECIDO, PROVIDO, DESPROVIDO, DESCONSIDERAR) - Dispositivo do Argumento
- Preencha conforme a seção 2, item 6, do PROMPT: se o pedido for NAO_CONHECIDO ou DESCONSIDERAR, repita o dispositivo do pedido; se for PROVIDO ou DESPROVIDO, use PROVIDO só quando a Prevalência do argumento na seção "Análise dos pedidos" for "favorável ao agravante, indício forte", e DESPROVIDO nos demais casos.
- Não use DESCONSIDERAR em argumento de pedido PROVIDO ou DESPROVIDO: todo argumento desses pedidos deve ser enfrentado na minuta.
##### motivo[] (opcional, opções: DEFICIENCIA_FUNDAMENTACAO, OUTROS_FUNDAMENTOS_NAO_CONHECIDO, ACOLHE_FUNDAMENTOS_PARTE, ACOLHE_E_ACRESCENTA, OUTROS_FUNDAMENTOS_PROVIDO, MANTEM_FUNDAMENTOS_DECISAO, MANTEM_E_ACRESCENTA, OUTROS_FUNDAMENTOS_DESPROVIDO) - Motivo
- Se o argumento repetir o dispositivo do pedido, repita também o motivo do pedido. Se o argumento for PROVIDO, use [ACOLHE_FUNDAMENTOS_PARTE]; se for DESPROVIDO, escolha pela tabela 3.3 do PROMPT, comparando a razão da prevalência do argumento com a decisão agravada.
- Quando o dispositivo for DESCONSIDERAR, preencha este campo com [].
##### fundamentacoes[] - Fundamentações Sugeridas do Argumento
- Apresente, para o argumento, entre 1 e 2 sugestões A_FAVOR e entre 1 e 2 CONTRA.
- Extraia-as das colunas de pontos favoráveis e contrários da tabela deste argumento, na seção "Análise dos pedidos"; se a análise trouxer menos, apresente só as que houver — não as invente.
###### Tg_Texto - Texto da Fundamentação
- A fundamentação, formulada de modo conciso e aplicável ao caso concreto (não uma máxima abstrata).
###### Tipo (opções: A_FAVOR, CONTRA) - Tipo da Fundamentação
- Tipo: A_FAVOR (fundamentação que sustenta o provimento do agravo interno) ou CONTRA (fundamentação que sustenta o seu desprovimento, pela manutenção da decisão agravada).
###### Lo_Selecionada - Selecionada
- Indicação de que a sugestão deve ser aproveitada na redação do voto.
- Marque true nas sugestões alinhadas com o dispositivo atribuído ao argumento e nas contrárias relevantes que deverão ser enfrentadas na fundamentação. Marque false nas demais. Isso é uma sugestão da IA, que poderá ser revista pelo usuário antes da redação do voto.
### Tg_ComandosAdicionais (opcional) - Comandos Adicionais
- Comandos para a redação da minuta que não cabem nos campos anteriores: encaminhamento, multa, providências, provimento parcial, pedidos prejudicados, observações da análise e avisos [VERIFICAR].
- Monte este campo conforme a seção 2, item 8, do PROMPT, uma informação por linha. As linhas de Encaminhamento e de Multa estão sempre presentes.
# FORMAT
{% if motivoGeral %}**Motivo(s) de Não Conhecimento do Agravo:** {{ motivoGeral | join(", ") }}
{% else %}
{% for d in pedidos %}{% set outerIndex = loop.index %}**Pedido {{loop.index}}:** {{ d.texto }}{% if d.motivo %} - {{ d.motivo | join(", ") }}{% endif %}
 
{% if d.fundamentacoes %}Fundamentações:{% for f in d.fundamentacoes %}
{{loop.index}}. {{ "[x]" if f.Lo_Selecionada else "[ ]" }} ({{ f.Tipo }}) {{ f.Tg_Texto }}{% endfor %}
 
{% endif %}{% if d.argumentos %}Argumentos:{% for a in d.argumentos %}
{{loop.index}}. {{ a.texto }}{% if a.motivo %} - {{ a.motivo | join(", ") }}{% endif %}
{% if a.fundamentacoes %}Fundamentações:{% for f in a.fundamentacoes %}
{{loop.index}}. {{ "[x]" if f.Lo_Selecionada else "[ ]" }} ({{ f.Tipo }}) {{ f.Tg_Texto }}{% endfor %}
{% endif %}{% endfor %}
 
{% endif %}{% endfor %}
{% endif %}
 
{% if Tg_ComandosAdicionais %}
**Comandos Adicionais:** {{ Tg_ComandosAdicionais }}
{% endif %}
