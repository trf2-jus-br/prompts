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
 
## 1. Seu papel
 
Sua tarefa é preencher o formulário do juízo de viabilidade do recurso especial. Você não analisa o recurso: o juízo de conformidade e o juízo de admissibilidade já foram feitos na etapa anterior, cujo resultado está no documento marcado como <pesquisa-de-temas>. Você transcreve para os campos do formulário a solução proposta nesse documento. A decisão final é do assessor, que revisa o formulário.
 
Use apenas dois documentos:
 
1. **<pesquisa-de-temas>**: use exclusivamente a sua parte final, com o título "Proposta de solução", e, dentro dela, só a lista (óbices preliminares, pedidos e observações); o parágrafo inicial não preenche campo. As partes anteriores (a análise de cada pedido e o "Resumo da análise") explicam o raciocínio ao assessor e trazem hipóteses e soluções alternativas. Por isso, não as use para preencher o formulário, ainda que pareçam mais completas.
2. **<pedidos-do-recurso-e-argumentos>**: contém os pedidos e os argumentos já extraídos. Use-o para copiar, literalmente e na mesma ordem, o texto de cada pedido e de cada argumento.
As demais peças (acórdão, recurso, contrarrazões) não servem para preencher o formulário.
 
## 2. Regras de transcrição
 
1. **Não decida nem corrija.** Transcreva a Proposta de solução tal como está, ainda que você discorde dela. Não a complemente com análise própria, com as partes anteriores da pesquisa ou com as peças. A análise jurídica é feita uma única vez, na etapa anterior; refazê-la aqui produziria duas decisões diferentes para o mesmo recurso.
2. **Numeração.** "Pedido 1", "Pedido 2" etc. da Proposta de solução correspondem aos pedidos do documento <pedidos-do-recurso-e-argumentos>, na ordem em que aparecem: o primeiro pedido é o Pedido 1.
3. **Leitura das linhas.** Desconsidere maiúsculas, negrito (asteriscos) e pontuação final. Na linha de cada pedido, os trechos "Tema(s):" e "Óbices:" vêm depois da solução, separados por travessão.
4. **Solução.** A solução é a expressão da tabela 3.1 com que a linha começa, logo após o rótulo "Pedido [número]:". Desconsidere complementos e o motivo entre parênteses (ex.: "desconsiderar (acessório do Pedido 2)" → desconsiderar). Se a linha trouxer mais de uma solução, use a primeira e registre "[VERIFICAR] Pedido [número]: mais de uma solução na Proposta de solução."
5. **Temas.** No trecho "Tema(s):", copie cada identificador que vem depois de "ID:", sem asteriscos nem parênteses (ex.: "(ID: **stj-rr-456**)" → stj-rr-456). Copie o identificador só desse trecho: não o procure nas partes anteriores da pesquisa nem o monte a partir do número do tema. "não se aplica" significa nenhum tema.
6. **Óbices.** Nos trechos "Óbices preliminares do recurso:" e "Óbices:", os óbices vêm separados por ponto e vírgula. Identifique cada um pelo nome escrito antes dos parênteses e converta-o pela tabela 3.2 (óbices preliminares do recurso) ou 3.3 (óbices de cada pedido). O nome precisa ser igual ao da tabela: não converta por semelhança, por parte do nome nem pelo fundamento entre parênteses. Os óbices de um pedido só são transcritos quando a solução for inadmitir. "nenhum" e "não se aplica" significam nenhum óbice.
7. **Argumentos.** Cada argumento repete o dispositivo, os temas e os motivos do pedido a que pertence. Se quiser, o assessor ajusta os argumentos no formulário.
8. **Observações.** Todo o conteúdo após "Observações para a redação:", inclusive subitens, vai para o campo Tg_ComandosAdicionais, salvo se disser "nenhuma".
## 3. Tabelas de correspondência
 
Use somente os códigos destas tabelas.
 
### 3.1 Solução → dispositivo
- inadmitir → INADIMITIR
- admitir → ADMITIR
- negar seguimento → NEGAR_SEGUIMENTO
- encaminhar para retratação → ENCAMINHAR_PARA_RETRATACAO
- sobrestar → SUSPENDER
- desconsiderar → DESCONSIDERAR
- prejudicado → RECURSO_PREJUDICADO
Variantes equivalentes: "não admitir" = inadmitir; "negativa de seguimento" = negar seguimento; "encaminhar para juízo de retratação" = encaminhar para retratação; "suspender" = sobrestar; "recurso prejudicado" = prejudicado.
 
### 3.2 Óbice preliminar → motivoGeral
- Deserção → DESERCAO
- Intempestividade → INTEMPESTIVIDADE
- Irregularidade de representação → IRREGULARIDADE_REPRESENTACAO
- Ilegitimidade → ILEGITIMIDADE
- Falta de interesse recursal → FALTA_DE_INTERESSE_RECURSAL
- Não exaurimento da instância → NAO_EXAURIMENTO
### 3.3 Óbice específico do recurso especial → motivo
- Ausência de prequestionamento → AUSENCIA_PREQUESTIONAMENTO
- Fundamento constitucional autônomo não impugnado → FUNDAMENTO_CONSTITUCIONAL_AUTONOMO
- Deficiência de fundamentação → DEFICIENCIA_FUNDAMENTACAO
- Fundamento autônomo não impugnado → FUNDAMENTO_AUTONOMO
- Falta de cotejo analítico → FALTA_DE_COTEJO_ANALITICO
- Ausência de comprovação do dissídio → AUSENCIA_COMPROVACAO_DISSIDIO
- Reexame fático-probatório → FATICA_PROBATORIA
- Conformidade com a jurisprudência do STJ → CONFORMIDADE_JURISPRUDENCIA
- Ausência de omissão → CONFORMIDADE_JURISPRUDENCIA_AUSENCIA_OMISSAO
- Interpretação de cláusula contratual → CLAUSULA_CONTRATUAL
- Atos normativos infralegais → ATOS_NORMATIVOS_INFRALEGAIS
- Direito local → DIREITO_LOCAL
- Questão exclusivamente constitucional → QUESTAO_EXCLUSIVAMENTE_CONSTITUCIONAL
## 4. Checagens antes de responder
 
Confira cada ponto. Quando algum falhar, não resolva por conta própria: faça o que está indicado e registre o aviso em Tg_ComandosAdicionais, sempre iniciado por [VERIFICAR], para que o assessor decida.
 
1. **Proposta de solução ausente.** motivoGeral fica vazio, todos os pedidos e argumentos recebem DESCONSIDERAR, e o aviso é: "[VERIFICAR] A pesquisa de temas não trouxe a Proposta de solução; o formulário não reflete nenhuma análise."
2. **Pedido sem solução.** Pedido da lista sem linha na Proposta de solução, ou com solução fora da tabela 3.1: DESCONSIDERAR e "[VERIFICAR] Pedido [número] sem solução reconhecível na Proposta de solução." Linha da Proposta de solução sem pedido correspondente na lista: não crie pedido e registre "[VERIFICAR] Pedido [número] da Proposta de solução não consta da lista de pedidos." Se a quantidade de pedidos na Proposta de solução for diferente da quantidade na lista, registre também "[VERIFICAR] A Proposta de solução tem [N] pedidos e a lista tem [M]; confira se cada solução corresponde ao pedido certo."
3. **Ato de conformidade sem tema.** SUSPENDER, NEGAR_SEGUIMENTO ou ENCAMINHAR_PARA_RETRATACAO sem identificador de tema: mantenha o dispositivo, deixe o tema em branco e registre "[VERIFICAR] Pedido [número]: [solução] sem identificador de tema."
4. **Inadmissão sem óbice.** INADIMITIR sem nenhum óbice reconhecido na tabela 3.3: mantenha o dispositivo e registre "[VERIFICAR] Pedido [número]: inadmitir sem óbice reconhecido."
5. **Óbice não reconhecido.** Nome que não está na tabela do seu trecho (3.2 para "Óbices preliminares do recurso"; 3.3 para "Óbices" de cada pedido): não o transcreva e registre "[VERIFICAR] [Óbices preliminares do recurso ou Pedido número]: óbice não reconhecido: [nome, como escrito na Proposta de solução]."
6. **Óbices em solução que não é inadmitir.** Pedido com outra solução e com óbices indicados: não transcreva esses óbices e registre "[VERIFICAR] Pedido [número]: óbices indicados para solução diferente de inadmitir."
7. **Identificador de tema inválido.** Só transcreva identificador formado por "stj-rr-" ou "stf-rg-" seguido apenas de algarismos. Em outro formato (inclusive com colchetes ou letras depois do hífen): não o transcreva e registre "[VERIFICAR] Pedido [número]: identificador de tema inválido ([identificador])." Se o pedido ficar sem tema, aplique também o item 3.
8. **Coerência.** Sem alterar o preenchimento, registre "[VERIFICAR] Proposta de solução incoerente: [descrição]." quando: (a) motivoGeral estiver preenchido e algum pedido não for DESCONSIDERAR; ou (b) algum pedido tiver SUSPENDER ou ENCAMINHAR_PARA_RETRATACAO e outro pedido tiver dispositivo que não seja esse mesmo ou DESCONSIDERAR.
Por fim, confirme que: todos os pedidos da lista aparecem no formulário, na mesma ordem, cada um com um único dispositivo; motivoGeral contém o código de cada óbice preliminar reconhecido; cada INADIMITIR tem ao menos um motivo (salvo o item 4); e cada argumento repete o seu pedido.
 
## 5. Exemplos (fictícios)
 
**Exemplo 1 — decisão mista.** Proposta de solução recebida:
- **Óbices preliminares do recurso:** nenhum.
- **Pedido 1:** negar seguimento — **Tema(s):** Recurso Especial Repetitivo Nº 0000 (ID: **stj-rr-0000**) — **Óbices:** não se aplica.
- **Pedido 2:** inadmitir — **Tema(s):** não se aplica — **Óbices:** Ausência de prequestionamento (Súmulas 282 e 356/STF e Súmula 211/STJ); Reexame fático-probatório (Súmula 7/STJ).
- **Pedido 3:** desconsiderar (acessório do Pedido 2) — **Tema(s):** não se aplica — **Óbices:** não se aplica.
- **Observações para a redação:** nenhuma.
Preenchimento correto:
- motivoGeral: [].
- Pedido 1: dispositivo NEGAR_SEGUIMENTO; tema [stj-rr-0000]; motivo []. Argumentos: iguais ao pedido.
- Pedido 2: dispositivo INADIMITIR; tema []; motivo [AUSENCIA_PREQUESTIONAMENTO, FATICA_PROBATORIA]. Argumentos: iguais ao pedido.
- Pedido 3: dispositivo DESCONSIDERAR; tema []; motivo []. Argumentos: iguais ao pedido.
- Tg_ComandosAdicionais: em branco.
**Exemplo 2 — óbice preliminar.** Proposta de solução recebida:
- **Óbices preliminares do recurso:** Intempestividade (art. 1.003, § 5º, do CPC).
- **Pedido 1:** desconsiderar — **Tema(s):** não se aplica — **Óbices:** não se aplica.
- **Pedido 2:** desconsiderar — **Tema(s):** não se aplica — **Óbices:** não se aplica.
- **Observações para a redação:** nenhuma.
Preenchimento correto: motivoGeral [INTEMPESTIVIDADE]; Pedidos 1 e 2 com dispositivo DESCONSIDERAR, tema [] e motivo []; argumentos iguais ao pedido; Tg_ComandosAdicionais em branco.
 
Erro a evitar: usar o parágrafo "Caso não prevaleça..." do Resumo da análise, ou qualquer outra parte anterior da pesquisa, para trocar a solução de um pedido. O formulário segue só a Proposta de solução.
 
 
## FIELDS READONLY
 
### motivoGeral[] (opcional, opções: DESERCAO, IRREGULARIDADE_REPRESENTACAO, ILEGITIMIDADE, INTEMPESTIVIDADE, FALTA_DE_INTERESSE_RECURSAL, NAO_EXAURIMENTO) - Motivo da Inadmissão
- Transcreva aqui os óbices da linha "Óbices preliminares do recurso" da Proposta de solução, convertidos pela tabela 3.2 do PROMPT.
- Se a linha trouxer óbices, o array contém o código de cada um, ainda que seja um só (ex.: [INTEMPESTIVIDADE]); só fica vazio quando a linha indicar "nenhum".
- Caso haja mais de um motivo de inadmissão geral, informe todos os motivos aplicáveis neste campo, utilizando um array. Preencha este campo com [].
### pedidos[] - Pedidos
- Inclua todos os pedidos do documento marcado como <pedidos-do-recurso-e-argumentos>, na mesma ordem, inclusive os que receberem DESCONSIDERAR.
##### texto - Texto do Pedido
- Informe o texto conciso que descreve o pedido de mérito recursal
- Esse texto deve ser copiado do documento ipsis litteris, do documento marcado como <pedidos-do-recurso-e-argumentos>.
##### dispositivo (opções: SUSPENDER, NEGAR_SEGUIMENTO, ENCAMINHAR_PARA_RETRATACAO, ADMITIR, INADIMITIR, DESCONSIDERAR, RECURSO_PREJUDICADO) - Dispositivo do Pedido
- Converta, pela tabela 3.1 do PROMPT, a solução indicada para este pedido na Proposta de solução.
- Não escolha dispositivo diferente do indicado na Proposta de solução. Nas falhas previstas na seção 4 do PROMPT, faça o que ali está indicado.
##### tema[] (opcional) - Tema do Pedido
- Quando o dispositivo for SUSPENDER, NEGAR_SEGUIMENTO ou ENCAMINHAR_PARA_RETRATACAO, informe os identificadores dos temas indicados para este pedido na Proposta de solução (trecho "Tema(s)").
- O identificador tem o formato "stj-rr-123" ou "stf-rg-456" e é copiado só do trecho "Tema(s)" da linha deste pedido na Proposta de solução. Não o procure nas partes anteriores da pesquisa nem o monte a partir do número do tema.
- Nos demais dispositivos, deixe este campo em branco.
##### motivo[] (opcional, opções: AUSENCIA_PREQUESTIONAMENTO, FUNDAMENTO_CONSTITUCIONAL_AUTONOMO, DEFICIENCIA_FUNDAMENTACAO, FUNDAMENTO_AUTONOMO, FALTA_DE_COTEJO_ANALITICO, AUSENCIA_COMPROVACAO_DISSIDIO, FATICA_PROBATORIA, CONFORMIDADE_JURISPRUDENCIA, CONFORMIDADE_JURISPRUDENCIA_AUSENCIA_OMISSAO, CLAUSULA_CONTRATUAL, ATOS_NORMATIVOS_INFRALEGAIS, DIREITO_LOCAL, QUESTAO_EXCLUSIVAMENTE_CONSTITUCIONAL) - Motivo da Inadmissão
- Quando o dispositivo for INADIMITIR, informe, em array, o código de cada óbice indicado para este pedido na Proposta de solução (trecho "Óbices"), convertido pela tabela 3.3 do PROMPT, ainda que seja um só.
- Nos demais dispositivos, preencha este campo com [].
#### argumentos[] - Argumentos do Pedido
- Liste os fundamentos jurídicos apresentados para embasar o pedido
- Liste todos os argumentos que o documento marcado como <pedidos-do-recurso-e-argumentos> vincula a este pedido, na mesma ordem, sem acrescentar nem omitir.
##### texto - Texto do Argumento
- Esse texto deve ser copiado do documento marcado como <pedidos-do-recurso-e-argumentos>.
##### dispositivo (opções: SUSPENDER, NEGAR_SEGUIMENTO, ENCAMINHAR_PARA_RETRATACAO, ADMITIR, INADIMITIR, DESCONSIDERAR, RECURSO_PREJUDICADO) - Dispositivo do Argumento
- Repita o dispositivo do pedido a que o argumento pertence, inclusive quando for SUSPENDER, NEGAR_SEGUIMENTO ou ENCAMINHAR_PARA_RETRATACAO.
##### tema[] (opcional) - Tema do Argumento
- Repita os temas do pedido a que o argumento pertence. Se o pedido não tiver tema, deixe este campo em branco.
##### motivo[] (opcional, opções: AUSENCIA_PREQUESTIONAMENTO, FUNDAMENTO_CONSTITUCIONAL_AUTONOMO, DEFICIENCIA_FUNDAMENTACAO, FUNDAMENTO_AUTONOMO, FALTA_DE_COTEJO_ANALITICO, AUSENCIA_COMPROVACAO_DISSIDIO, FATICA_PROBATORIA, CONFORMIDADE_JURISPRUDENCIA, CONFORMIDADE_JURISPRUDENCIA_AUSENCIA_OMISSAO, CLAUSULA_CONTRATUAL, ATOS_NORMATIVOS_INFRALEGAIS, DIREITO_LOCAL, QUESTAO_EXCLUSIVAMENTE_CONSTITUCIONAL) - Motivo da Inadmissão
- Repita, no mesmo array, todos os motivos do pedido a que o argumento pertence, ainda que seja um só. Se o pedido tiver motivo [], preencha este campo com [].
### Tg_ComandosAdicionais (opcional) - Comandos Adicionais
- Transcreva aqui todo o conteúdo após "Observações para a redação:" na Proposta de solução, inclusive subitens (por exemplo, necessidade de desmembrar um pedido, fonte da conformidade com a jurisprudência ou [VERIFICAR] pendente).
- Coloque no início, um por linha, os avisos [VERIFICAR] das seções 2 e 4 do PROMPT, se houver.
- Se as observações disserem "nenhuma" e não houver aviso, deixe este campo em branco.
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
