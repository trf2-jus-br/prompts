---
uuid: dbace8ce-c526-4b15-b3d5-373b32344778
name: Juízo de Embargos de Declaração em Viabilidade de Recurso
description: Realize o juízo completo de embargos de declaração em decisão de viabilidade do recurso.
sort: 3
share: oculto
piece_strategy: embargos-de-declaracao-em-viabilidade-recurso
---

# PROMPT
 
Leia atentamente o conteúdo das peças processuais fornecidas abaixo.
 
{{textos}}
 
Você leu os documentos de embargos de declaração opostos contra decisão monocrática ou contra acórdão, em processo relativo a recurso especial ou extraordinário.
 
## 1. Seu papel

Sua tarefa é preencher o formulário do juízo dos embargos de declaração. Você não analisa os embargos: a análise já foi feita na etapa anterior e termina com uma proposta de resultado. Você transcreve essa proposta para os campos do formulário. A decisão final é do assessor, que revisa o formulário.

Use apenas dois documentos:

1. **Análise dos embargos**: o documento que contém a seção intitulada "Proposta de resultado". Dessa seção saem o motivo geral, os dispositivos dos pedidos e os comandos adicionais. A seção "Análise dos pedidos" serve só para o dispositivo dos argumentos e para as fundamentações sugeridas (seção 2, itens 5 e 6). As demais seções da análise não preenchem campos; em especial, não use o "Resumo da análise dos Embargos de Declaração": ele traz hipóteses e soluções alternativas ("Caso não prevaleça...") que não valem para o formulário.
2. **Pedidos e argumentos dos embargos**: o documento marcado como <embargos-de-declaracao> (se não houver documento com essa marcação, o marcado como <pedidos-do-recurso-e-argumentos>). Use-o para copiar, literalmente e na mesma ordem, o texto de cada pedido e de cada argumento.
As demais peças (ato embargado, petição dos embargos, manifestação da parte contrária) servem apenas para conferir a natureza do ato embargado (decisão ou acórdão), que define o encaminhamento e o uso de RETRATAR ou DAR_PROVIMENTO (tabela 3.1). Não as use para mudar a solução proposta.
 
## 2. Regras de transcrição

1. **Não decida nem corrija.** Transcreva a Proposta de resultado tal como está, ainda que você discorde dela. A análise jurídica é feita uma única vez, na etapa anterior; refazê-la aqui produziria duas decisões diferentes para os mesmos embargos.
2. **Numeração.** "Pedido 1", "Pedido 2" etc. da Proposta de resultado correspondem aos pedidos do documento de pedidos e argumentos, na ordem em que aparecem. Na seção "Análise dos pedidos", "Argumento 1.2" é o segundo argumento do Pedido 1.
3. **Leitura da análise.** Desconsidere maiúsculas, negrito (asteriscos), marcadores (● e •), linhas de separação (---) e pontuação final. Cada pedido da Proposta de resultado traz os subitens Solução, Prevalência, Fundamento, Providência e Tema(s)/enunciado(s). Na seção "Análise dos pedidos", cada argumento traz uma tabela com as colunas "Pontos favoráveis ao acolhimento" e "Pontos contrários ao acolhimento" e, logo abaixo, a linha "Prevalência".
4. **Dispositivo do pedido.** Converta a Solução pela tabela 3.1, observando a natureza do ato embargado ("Retratar" só em embargos contra decisão monocrática; "dar provimento", só em embargos contra acórdão). Exceção: se o "Resultado dos embargos" for "não conhecer" e o item "Admissibilidade dos embargos" da Proposta de resultado (não a seção de mesmo nome) indicar óbice da tabela 3.2, preencha motivoGeral com o código de cada óbice e dê NAO_CONHECER a todos os pedidos e argumentos.
5. **Argumentos.** Se o pedido for NAO_CONHECER, cada argumento repete o dispositivo do pedido. Se o pedido for RETRATAR, DAR_PROVIMENTO, DAR_PARCIAL_PROVIMENTO ou NEGAR_PROVIMENTO, use a Prevalência do argumento na seção "Análise dos pedidos": "favorável ao embargante, indício forte" → DAR_PROVIMENTO; qualquer outra prevalência (inclusive "favorável ao embargante, indício fraco" e "não avaliável") → NEGAR_PROVIMENTO. Em argumento, nunca use RETRATAR nem DAR_PARCIAL_PROVIMENTO: retratação e provimento parcial cabem só ao pedido.
6. **Fundamentações.** Extraia as sugestões das tabelas da seção "Análise dos pedidos": cada ponto da coluna "Pontos favoráveis ao acolhimento" pode gerar uma sugestão A_FAVOR; cada ponto da coluna "Pontos contrários ao acolhimento", uma sugestão CONTRA. Para o pedido, use os pontos de todos os seus argumentos e a "Conclusão do pedido"; para o argumento, só os pontos dele. Reescreva-os de forma concisa, sem acrescentar conteúdo. Se a análise trouxer menos sugestões que o mínimo do campo, apresente só as que houver.
7. **Comandos adicionais.** Monte o campo Tg_ComandosAdicionais com estas linhas, nesta ordem:
   a) os avisos [VERIFICAR] da seção 4, um por linha;
   b) "Encaminhamento: " seguido do valor do item Encaminhamento da Proposta de resultado;
   c) "Multa (art. 1.026 do CPC): " seguido do valor do item Multa;
   d) para cada pedido com Solução "retratar": "Pedido [número] — providência: [texto do item Providência]";
   e) para cada pedido com Solução "dar provimento": "Pedido [número] — providência: [texto do item Providência]";
   f) para cada pedido com Solução "dar parcial provimento": "Pedido [número] — provimento parcial. Providência: [texto do item Providência]. Fundamento: [texto do item Fundamento]";
   g) para cada pedido com Solução "prejudicado": "Pedido [número] — declarar prejudicados os embargos quanto a este pedido, por perda superveniente de objeto: [texto do item Fundamento]";
   h) todo o conteúdo do item "Observações para a redação", inclusive subitens, salvo se disser "nenhuma".
## 3. Tabelas de correspondência
 
Use somente os códigos destas tabelas.

### 3.1 Solução → dispositivo
- retratar → RETRATAR (só em embargos contra decisão monocrática)
- dar provimento → DAR_PROVIMENTO (só em embargos contra acórdão)
- dar parcial provimento → DAR_PARCIAL_PROVIMENTO (o limite do acolhimento vai para os comandos adicionais — seção 2, item 7, "f")
- negar provimento → NEGAR_PROVIMENTO
- não conhecer → NAO_CONHECER
- prejudicado → NAO_CONHECER (a perda de objeto é causa de não conhecimento; o registro vai para os comandos adicionais — seção 2, item 7, "g")
Variantes equivalentes: "acolher os embargos" ou "acolher com retratação" = retratar (embargos contra decisão) ou dar provimento (embargos contra acórdão); "rejeitar (os embargos quanto ao pedido)" = negar provimento; "desconhecer" ou "não conhecer" = não conhecer; "julgar prejudicado" = prejudicado.
 
### 3.2 Óbice ao conhecimento dos embargos → motivoGeral
- Intempestividade → INTEMPESTIVIDADE
- Não cabimento (inclusive via inadequada) → NAO_CABIMENTO
Identifique o óbice pelo nome escrito antes dos parênteses. Óbice que não está nesta tabela (ex.: irregularidade de representação) não vai para motivoGeral: os pedidos recebem NAO_CONHECER pela tabela 3.1.
 
## 4. Checagens antes de responder

Confira cada ponto. Quando algum falhar, não resolva por conta própria: faça o que está indicado e registre o aviso em Tg_ComandosAdicionais, sempre iniciado por [VERIFICAR], para que o assessor decida.

1. **Proposta de resultado ausente.** motivoGeral fica vazio, todos os pedidos e argumentos recebem NAO_CONHECER, o encaminhamento é "julgamento pelo órgão colegiado", e o aviso é: "[VERIFICAR] A análise não trouxe a Proposta de resultado; o formulário não reflete nenhuma análise."
2. **Pedido sem solução.** Pedido da lista sem item na Proposta de resultado, ou com Solução fora da tabela 3.1: NAO_CONHECER e "[VERIFICAR] Pedido [número] sem solução reconhecível na Proposta de resultado." Item da Proposta de resultado sem pedido correspondente na lista: não crie pedido e registre "[VERIFICAR] Pedido [número] da Proposta de resultado não consta da lista de pedidos." Se as quantidades forem diferentes, registre também "[VERIFICAR] A Proposta de resultado tem [N] pedidos e a lista tem [M]; confira se cada solução corresponde ao pedido certo."
3. **Mais de um embargos.** Se a análise trouxer mais de uma Proposta de resultado ("Proposta de resultado — Embargos 1", "— Embargos 2"), use a dos embargos cujos pedidos constam do documento de pedidos e argumentos e registre "[VERIFICAR] A análise trata de mais de um embargos; este formulário reflete só o Embargos [número]."
4. **Acolhimento sem providência.** Solução "retratar", "dar provimento" ou "dar parcial provimento" com Providência vazia ou "não se aplica": mantenha o dispositivo e registre "[VERIFICAR] Pedido [número]: acolhimento sem providência indicada."
5. **Encaminhamento.** Item ausente, ou com valor diferente de "decisão monocrática do relator" e de "julgamento pelo órgão colegiado": escreva "Encaminhamento: julgamento pelo órgão colegiado" e registre "[VERIFICAR] Encaminhamento não indicado na Proposta de resultado; adotado o julgamento colegiado." Encaminhamento incompatível com a natureza do ato embargado que conste das peças ou da análise (ex.: "decisão monocrática do relator" em embargos contra acórdão): transcreva-o como está e registre "[VERIFICAR] Encaminhamento aparentemente incompatível com a natureza do ato embargado; confira o formato da minuta."
6. **Argumento sem análise.** Argumento sem Prevalência na seção "Análise dos pedidos": repita o dispositivo do pedido e registre "[VERIFICAR] Argumento [número].[número] sem prevalência na análise."
Por fim, confirme que: todos os pedidos da lista aparecem no formulário, na mesma ordem, cada um com um único dispositivo; todos os argumentos de cada pedido aparecem, na mesma ordem; motivoGeral só está preenchido quando o Resultado dos embargos for "não conhecer"; nenhum argumento usa RETRATAR ou DAR_PARCIAL_PROVIMENTO; e Tg_ComandosAdicionais traz as linhas de Encaminhamento e de Multa.
 
## 5. Exemplos (fictícios)

**Exemplo 1 — rejeição, embargos contra acórdão (julgamento colegiado).** Proposta de resultado recebida:
- **Admissibilidade dos embargos:** sem óbices.
- **Pedido 1 — sanar a omissão quanto à análise do argumento de [descrição]**
   - **Solução:** negar provimento
   - **Prevalência:** contrária ao embargante, indício forte
   - **Fundamento:** o acórdão embargado enfrentou o argumento ao concluir que [razão]
   - **Providência:** não se aplica
   - **Tema(s)/enunciado(s):** não se aplica
- **Pedido 2 — [consectário do ponto atacado — pedido acessório]**
   - **Solução:** negar provimento
   - **Prevalência:** não se aplica
   - **Fundamento:** pedido acessório do Pedido 1; rejeitado com ele
   - **Providência:** não se aplica
   - **Tema(s)/enunciado(s):** não se aplica
- **Resultado dos embargos:** conhecer dos embargos e negar-lhes provimento
- **Encaminhamento:** julgamento pelo órgão colegiado
- **Multa (art. 1.026 do CPC):** não cabível
- **Observações para a redação:** nenhuma
Na seção "Análise dos pedidos", o Argumento 1.1 tem prevalência "contrária ao embargante, indício forte", e o Argumento 1.2, "favorável ao embargante, indício fraco".

Preenchimento correto:
- motivoGeral: [].
- Pedido 1: dispositivo NEGAR_PROVIMENTO; fundamentações tiradas dos pontos favoráveis (A_FAVOR) e contrários (CONTRA) dos Argumentos 1.1 e 1.2, com true nas CONTRA que sustentam o Fundamento e false em todas as A_FAVOR. Argumento 1.1: NEGAR_PROVIMENTO. Argumento 1.2: NEGAR_PROVIMENTO — indício fraco não leva a DAR_PROVIMENTO.
- Pedido 2: dispositivo NEGAR_PROVIMENTO; fundamentações vazias (pedido acessório, sem blocos de argumento na análise).
- Tg_ComandosAdicionais:
  Encaminhamento: julgamento pelo órgão colegiado
  Multa (art. 1.026 do CPC): não cabível
**Exemplo 2 — acolhimento com retratação, embargos contra decisão (decisão monocrática).** Proposta de resultado recebida (só os itens que mudam):
- **Pedido 1 — sanar a omissão quanto à análise do argumento de [descrição]**
   - **Solução:** retratar
   - **Fundamento:** a decisão embargada não enfrentou argumento expressamente deduzido nas razões do recurso (art. 1.022, II, do CPC, c/c art. 489, § 1º, do CPC)
   - **Providência:** suprir a omissão, com manifestação expressa sobre o argumento, integrando a decisão embargada
- **Resultado dos embargos:** conhecer dos embargos e acolhê-los, com retratação da decisão embargada
- **Encaminhamento:** decisão monocrática do relator
- **Multa (art. 1.026 do CPC):** não cabível
Preenchimento correto: Pedido 1 com dispositivo RETRATAR; argumentos conforme a prevalência de cada um na seção "Análise dos pedidos" (DAR_PROVIMENTO só para o de prevalência "favorável ao embargante, indício forte"; NEGAR_PROVIMENTO para os demais); Tg_ComandosAdicionais:
  Encaminhamento: decisão monocrática do relator
  Multa (art. 1.026 do CPC): não cabível
  Pedido 1 — providência: suprir a omissão, com manifestação expressa sobre o argumento, integrando a decisão embargada
 
Erros a evitar: usar o parágrafo "Caso não prevaleça..." do Resumo da análise dos Embargos de Declaração para trocar a solução de um pedido; dar DAR_PROVIMENTO a argumento com prevalência "favorável ao embargante, indício fraco"; usar RETRATAR em embargos contra acórdão, ou DAR_PROVIMENTO (como acolhimento integral do pedido) em embargos contra decisão; usar RETRATAR ou DAR_PARCIAL_PROVIMENTO em argumento; marcar true em sugestão do tipo oposto ao dispositivo (ex.: A_FAVOR em pedido NEGAR_PROVIMENTO), o que faz o formulário parecer contraditório.
 
 
## FIELDS READONLY

### motivoGeral[] (opcional, opções: INTEMPESTIVIDADE, NAO_CABIMENTO) - Motivo do Não Conhecimento dos Embargos
- Quando for o caso de não conhecer dos embargos de declaração por um motivo que independe da análise do pedido ou argumento específico, deve ser informado neste campo o identificador do motivo do não conhecimento dos embargos.
- No contexto dos embargos de declaração, os motivos referem-se aos próprios embargos: INTEMPESTIVIDADE (embargos opostos fora do prazo de 5 dias úteis — arts. 1.023, 219 e 229 do CPC) e NAO_CABIMENTO (ato que não se sujeita a embargos — ex.: despacho de mero expediente — ou pretensão que exige outra via, como a reforma de decisão monocrática sem vício, cujo recurso próprio é o agravo interno do art. 1.021 do CPC).
- Preencha só quando o "Resultado dos embargos", na Proposta de resultado, for "não conhecer" e o item "Admissibilidade dos embargos" da Proposta de resultado indicar óbice da tabela 3.2 do PROMPT. O array contém o código de cada óbice, ainda que seja um só (ex.: [INTEMPESTIVIDADE]).
- Nos demais casos, inclusive no conhecimento parcial, preencha este campo com [].
### pedidos[] - Pedidos
- Inclua todos os pedidos do documento de pedidos e argumentos dos embargos, na mesma ordem, inclusive os que receberem NAO_CONHECER.
##### texto - Texto do Pedido
- Informe o texto conciso que descreve a pretensão de correção do julgado.
- Esse texto deve ser copiado ipsis litteris do documento de pedidos e argumentos dos embargos (seção 1 do PROMPT).
##### dispositivo (opções: NAO_CONHECER, RETRATAR, DAR_PROVIMENTO, DAR_PARCIAL_PROVIMENTO, NEGAR_PROVIMENTO) - Dispositivo do Pedido
- NAO_CONHECER: embargos não conhecidos quanto ao pedido; RETRATAR: decisão embargada retificada ou integrada quanto ao pedido (acolhimento integral, em embargos contra decisão monocrática); DAR_PROVIMENTO: embargos acolhidos quanto ao pedido (acolhimento integral, em embargos contra acórdão); DAR_PARCIAL_PROVIMENTO: acolhimento quanto a parte do pedido, mantida a decisão embargada no restante; NEGAR_PROVIMENTO: embargos rejeitados quanto ao pedido. RETRATAR e DAR_PROVIMENTO têm sentido semelhante: o primeiro vale para embargos contra decisão, o segundo, para embargos contra acórdão.
- Converta, pela tabela 3.1 do PROMPT, a Solução indicada para este pedido na Proposta de resultado. Não escolha dispositivo diferente; nas falhas previstas na seção 4 do PROMPT, faça o que ali está indicado.
- Se motivoGeral estiver preenchido, preencha este campo com NAO_CONHECER.
##### fundamentacoes[] - Fundamentações Sugeridas do Pedido
- Liste sugestões de fundamentação a favor e contra o pedido, para orientar a redação da minuta na etapa seguinte.
- Extraia-as das tabelas da seção "Análise dos pedidos", conforme a seção 2, item 6, do PROMPT. Apresente entre 2 e 4 sugestões de cada tipo (A_FAVOR e CONTRA); se a análise trouxer menos, apresente só as que houver — não as invente.
- Quando o dispositivo for NAO_CONHECER, inclua como CONTRA, marcada com true, a razão do não conhecimento; as demais sugestões são opcionais.
- Quando o dispositivo for DAR_PARCIAL_PROVIMENTO, as sugestões A_FAVOR selecionadas limitam-se à parte acolhida.
- O usuário poderá revisar este JSON e alterar as marcações (inclusive o próprio teor das fundamentações) antes da redação da minuta; a redação utilizará as fundamentações marcadas como roteiro.
- Para cada sugestão, preencha os campos abaixo:
###### Tg_Texto - Texto da Fundamentação
- A fundamentação, formulada de modo conciso e aplicável ao caso concreto (não uma máxima abstrata).
###### Tipo (opções: A_FAVOR, CONTRA) - Tipo da Fundamentação
- Tipo: A_FAVOR (fundamentação que sustenta o acolhimento dos embargos) ou CONTRA (fundamentação que sustenta a sua rejeição, com a manutenção do ato embargado).
###### Lo_Selecionada - Selecionada
- Indicação de que a sugestão deve ser aproveitada na redação da minuta.
- Marque true só nas sugestões do tipo alinhado com o dispositivo do pedido que sejam pertinentes ao Fundamento da Proposta de resultado: CONTRA, quando o dispositivo for NEGAR_PROVIMENTO ou NAO_CONHECER; A_FAVOR, quando for RETRATAR, DAR_PROVIMENTO ou DAR_PARCIAL_PROVIMENTO. Marque false nas demais, inclusive em todas as do tipo oposto: o enfrentamento dos argumentos do embargante já é garantido na redação, que examina cada argumento. Isso é uma sugestão da IA, que poderá ser revista pelo usuário antes da redação da minuta.
#### argumentos[] - Argumentos do Pedido
- Liste os fundamentos jurídicos apresentados para embasar o pedido
- Liste todos os argumentos que o documento de pedidos e argumentos dos embargos vincula a este pedido, na mesma ordem, sem acrescentar nem omitir.
##### texto - Texto do Argumento
- Esse texto deve ser copiado do documento de pedidos e argumentos dos embargos (seção 1 do PROMPT).
##### dispositivo (opções: NAO_CONHECER, RETRATAR, DAR_PROVIMENTO, DAR_PARCIAL_PROVIMENTO, NEGAR_PROVIMENTO) - Dispositivo do Argumento
- Preencha conforme a seção 2, item 5, do PROMPT: se o pedido for NAO_CONHECER, repita o dispositivo do pedido; se for RETRATAR, DAR_PROVIMENTO, DAR_PARCIAL_PROVIMENTO ou NEGAR_PROVIMENTO, use DAR_PROVIMENTO só quando a Prevalência do argumento na seção "Análise dos pedidos" for "favorável ao embargante, indício forte", e NEGAR_PROVIMENTO nos demais casos.
- Nunca use RETRATAR ou DAR_PARCIAL_PROVIMENTO em argumento: retratação e provimento parcial cabem só ao pedido. Também não use NAO_CONHECER em argumento de pedido acolhido ou rejeitado: todo argumento desses pedidos deve ser enfrentado na minuta.
##### fundamentacoes[] - Fundamentações Sugeridas do Argumento
- Apresente, para o argumento, entre 1 e 2 sugestões A_FAVOR e entre 1 e 2 CONTRA.
- Extraia-as das colunas de pontos favoráveis e contrários da tabela deste argumento, na seção "Análise dos pedidos"; se a análise trouxer menos, apresente só as que houver — não as invente.
###### Tg_Texto - Texto da Fundamentação
- A fundamentação, formulada de modo conciso e aplicável ao caso concreto (não uma máxima abstrata).
###### Tipo (opções: A_FAVOR, CONTRA) - Tipo da Fundamentação
- Tipo: A_FAVOR (fundamentação que sustenta o acolhimento dos embargos) ou CONTRA (fundamentação que sustenta a sua rejeição, com a manutenção do ato embargado).
###### Lo_Selecionada - Selecionada
- Indicação de que a sugestão deve ser aproveitada na redação da minuta.
- Marque true só nas sugestões do tipo alinhado com o dispositivo do argumento: CONTRA, quando o dispositivo for NEGAR_PROVIMENTO ou NAO_CONHECER; A_FAVOR, quando for DAR_PROVIMENTO. Marque false nas demais, inclusive em todas as do tipo oposto. Isso é uma sugestão da IA, que poderá ser revista pelo usuário antes da redação da minuta.
### Tg_ComandosAdicionais (opcional) - Comandos Adicionais
- Comandos para a redação da minuta que não cabem nos campos anteriores: encaminhamento, multa, providências, acolhimento parcial, pedidos prejudicados, observações da análise e avisos [VERIFICAR].
- Monte este campo conforme a seção 2, item 7, do PROMPT, uma informação por linha. As linhas de Encaminhamento e de Multa estão sempre presentes.
# FORMAT
{% if motivoGeral %}**Motivo(s) de Não Conhecimento dos Embargos:** {{ motivoGeral | join(", ") }}
{% else %}
{% for d in pedidos %}{% set outerIndex = loop.index %}**Pedido {{loop.index}}:** {{ d.texto }}
 
{% if d.fundamentacoes %}Fundamentações:{% for f in d.fundamentacoes %}
{{loop.index}}. {{ "[x]" if f.Lo_Selecionada else "[ ]" }} ({{ f.Tipo }}) {{ f.Tg_Texto }}{% endfor %}
 
{% endif %}{% if d.argumentos %}Argumentos:{% for a in d.argumentos %}
{{loop.index}}. {{ a.texto }}
{% if a.fundamentacoes %}Fundamentações:{% for f in a.fundamentacoes %}
{{loop.index}}. {{ "[x]" if f.Lo_Selecionada else "[ ]" }} ({{ f.Tipo }}) {{ f.Tg_Texto }}{% endfor %}
{% endif %}{% endfor %}
 
{% endif %}{% endfor %}
{% endif %}
 
{% if Tg_ComandosAdicionais %}
**Comandos Adicionais:** {{ Tg_ComandosAdicionais }}
{% endif %}
