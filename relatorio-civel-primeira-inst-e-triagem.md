---
uuid: b0718f6e-6632-4e5a-9f2f-918c26766584
name: Relatório Cívil de 1ª Instância e Triagem
description: Obtenha relatório e triagem para uma visão rápida e completa do estado do processo.
author: Renato Crivano/TRF2
sort: 1
piece_strategy: mais-relevantes
batch_report: true
successors:
  - path: chat
---

# PROMPT

Você foi designado para elaborar a análise de uma ação judicial proposta na justiça federal. 
Por favor, leia com atenção os textos a seguir:

{{textos}}

Formate sua análise de acordo com o modelo a seguir, demarcado por <modelo> e </modelo>:

<modelo>
# Relatório
[Gere um relatório conforme as orientações abaixo:

1. ESTRUTURA DO RELATÓRIO:
   - Inicie com "Trata-se de [tipo de ação] ajuizada por [parte autora] contra [parte ré], em que requer [copie os pedidos principais substantivos da parte autora]"
   - Os textos estão em ordem cronológica e o relatório deve seguir a mesma ordem
   - Diferentes eventos só devem ser agrupados no mesmo parágrafo caso tenham o mesmo teor
   - Divida o texto em parágrafos
   - Encerre apenas com "É o relatório." sem parágrafos conclusivos

2. CONTEÚDO ESSENCIAL:
   - Inclua apenas os pedidos principais substantivos, omitindo pedidos processuais formais como condenação em custas, honorários, concessão de gratuidade ou intimações. 
   - Em processos previdenciários, sempre mencione a data de entrada do requerimento administrativo (DER) e o motivo do indeferimento
   - resuma a fundamentação jurídica apresentada pela parte autora, sem omitir argumentos (exceção: pode emitir questões sobre opção pelo juízo 100% digital) e sem analisar o mérito;
    - nos processos de juizado previdenciário, verifique os argumentos do INSS que são relevantes para o caso, resumindo-os, sem analisar o mérito.
   -  nos demais processos, resuma a fundamentação jurídica apresentada pela parte ré, sem omitir argumentos e sem analisar o mérito.
   - Identifique claramente a origem de cada documento médico citado (ex: "conforme laudo médico-pericial do INSS", "segundo o laudo pericial judicial", "de acordo com atestado do médico assistente");
   - Nos processos que tramitam pelo procedimento comum, resuma a fundamentação jurídica da réplica, sem omitir argumentos e sem analisar o mérito.
   - Descreva todos os atos processuais relevantes em ordem cronológica, sempre referenciando as peças correspondentes.

3. O QUE RIGOROSAMENTE EVITAR:
   - Dados pessoais detalhados desnecessários (qualificação completa, CPF, endereços)
   - Formatação em negrito, itálico, sublinhado, subtítulos ou tópicos
   - Valor da causa, salvo se for determinante para o mérito
   - Pedidos processuais formais (como custas, honorários, gratuidade, citações)
   - Contestações genéricas do INSS sobre correção monetária, juros e prescrição
   - Qualquer análise de mérito, valoração de provas, laudos periciais ou conclusões sobre o caso
   - Parágrafos finais de síntese ou conclusão (o relatório deve ser completamente descritivo)
   - Termos como "alega", "sustenta", "afirma" ou similares que possam indicar dúvida sobre as afirmações
   - Referir-se ao juiz como "o juiz", prefira "o Juízo"

4. REFERÊNCIAS:
   - Quando referenciar uma peça ou um documento, entre parênteses, indique: (evento [atributo "event" do documento], [atributo "label" do documento, se houver], página [número da página se houver]). Por exemplo: (evento 1, INIC1) ou (evento 1, 1º Grau, INIC1).
   - Não mencione páginas específicas, a menos que absolutamente necessário

5. CASOS ESPECIAIS
   - Em se tratando de procedimento de juizado previdenciário, seja mais conciso, mas sem omitir argumentos relevantes e, se houver mais mais de um laudo, use apenas o laudo pericial do INSS e o laudo pericial do perito nomeado pelo juiz.]

# Questão Central
[Estabeleça com clareza a questão central]

# Pontos Controvertidos
1. [Delimite os pontos controvertidos]

# Normas/Jurisprudência Invocadas
- [CITE as normas que foram citadas na sentença ou no recurso inominado, apenas uma norma por linha, use uma maneira compacta e padronizada de se referir a norma, se houver referência ao número do artigo, inclua após uma vírgula, por exemplo: L 1234/2010, Art. 1º]

# Palavras-Chave
- [Inclua palavras-chave que possam caracterizar o caso ou as entidades envolvidas. Apenas uma palavra-chave por linha. Comece com a primeira letra maiúscula, como se fosse um título. Não inclua "Recurso Inominado" ou "Sentença". Não inclua referências à normas legais.]

# Triagem
[Escreva um título que será utilizado para agrupar processos semelhantes. O título deve ir direto ao ponto e ser bem compacto, como por exemplo: "Benefício por incapacidade", "Benefício de prestação continuada - LOAS", "Seguro desemprego", "Salário maternidade", "Aposentadoria por idade", "Aposentadoria por idade rural", "Aposentadoria por tempo de contribuição", "Tempo especial", "Auxílio reclusão", "Pensão por morte", "Revisão da vida toda", "Revisão teto EC 20/98 e EC 41/03"]

</modelo>

Certifique-se de:
- Formatar o texto usando Markdown
- Não repita as instruções na análise.