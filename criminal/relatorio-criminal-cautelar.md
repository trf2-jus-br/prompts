---
uuid: 214ccb70-9ff5-49a8-bb55-9cf64c0c4ac0
name: Relatório Criminal Cautelar
description: Analise medidas cautelares criminais e obtenha um relatório completo, uma análise preliminar e um índice de peças.
share: beta-teste
piece_strategy: todas
---

# PROMPT

Você foi designado para ler todo o texto de uma ação judicial e fazer uma análise do processo. 

Leia atentamente os textos abaixo:

{{textos}}

## TAREFA PRINCIPAL

ANALISE EM DETALHE o caso jurídico fornecido TODOS OS DOCUMENTOS, INCORPORE NUANCES e forneça uma ARGUMENTAÇÃO LÓGICA.
- Ao escrever o RELATÓRIO, assegure-se de prover uma riqueza de detalhes.
- Quando for referenciar um documento do processo que está sendo analisado, entre parênteses, indique o número do evento (event), o rótulo do documento (label) e, se houver, as páginas de início e término. Por exemplo: **Petição Inicial** (evento 1, OUT1, pág. 5/7).
- Quando for referenciar um documento de outro processo, após o número do envento, indique o número do processo. Por exemplo: (evento 1, processo X, OUT1, pág. 5/7).
- Mantenha as referências estritamente dentro do escopo do caso fornecido.
- Não faça um resumo, entre em detalhes e apresente as informações de forma completa.


## EXEMPLO E MODELO E ESTRUTURA

Formate sua resposta conforme exemplo a seguir, demarcado por <modelo>.

<modelo>
# Relatório

[Descrição geral do pedido]

[Se houver manifestação do Ministério Público, escreva um parágrafo introdutório e depois cite as principais passagens, usando blockquotes.]

[Descrição do modus-operandi e como cada um dos investigados se encaixa.]

[Inclua um longo parágrafo para cada investigado, não faça divisão em tópicos, seja detalhista e apresente toda a informação, inclua:
- o nome em negrito;
- uma descrição detalhada dos fatos relevantes e atos dos quais está sendo acusado;
- seu papel e sua participação no crime;
- Também informe sua relação com os outros investigados, valores e empresas envolvidas, se houver;
- Caso referencie alguma peça processual, inclua a referência no formato descrito acima.]

# Problema Jurídico

# Questão Central
[Estabeleça com clareza a questão central]

# Pontos Controvertidos
1. [Delimite os pontos controvertidos, se há houver decisão, informe também a decisão e a referência ao documento onde ela pode ser encontrada.]

# Direito Aplicável
- [Defina as normas aplicáveis ao caso, referenciadas nos documentos]

# Análise e Aplicação
## Argumentos e Provas da Polícia
1. [LISTE os argumentos e provas da Polícia COM INFERÊNCIA LÓGICA]

## Argumentos e Provas do Ministério Público
1. [LISTE os argumentos e provas do Ministério Público COM INFERÊNCIA LÓGICA]

## Análise Preliminar
[Analise cada elemento da norma, dos argumentos e dos fatos para verificar se as normas se aplicam ao caso]

# Índice
- [LISTE todos os documentos do processo na ordem em que aparecem. Para cada documento, indique o tipo da peça processual, resuma o contúdo em um parágrafo, indique o número do evento (event), o rótulo do documento (label) e, se houver, a página (pages) onde ele inicia e termina. Se for apenas uma página, basta indicar a página de início. Por exemplo: **Petição Inicial** - [Conteúdo resumido da petição] (evento 1, OUT1, pág. 1/22)].

</modelo>