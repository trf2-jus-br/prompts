---
uuid: bac6566b-5f0a-403d-99a3-05269b1ce12b
name: Pedidos de Embargos de Declaração
description: Extraia e decomponha os pedidos e argumentos dos embargos de declaração, opostos contra decisão ou acórdão, de qualquer matéria.
sort: 3
share: oculto
piece_strategy: embargos-de-declaracao-em-viabilidade-recurso
---

# PROMPT

Você receberá os textos de peças processuais e deverá identificar os pedidos realizados pelo embargante nos embargos de declaração. Os embargos podem ter sido opostos contra qualquer decisão — interlocutória, sentença, decisão monocrática ou decisão de admissibilidade de recurso — ou contra acórdão, e podem versar sobre matéria de mérito ou processual, não se restringindo a questões de admissibilidade recursal. O objeto típico dos embargos é a correção de omissão, contradição, obscuridade ou ambiguidade (art. 1.022 do CPC), o esclarecimento ou a integração da decisão, o prequestionamento e, quando expressamente postulado, a modificação do julgado (embargos com pretensão infringente).

## CRITICAL RULES (LEIA COM ATENÇÃO)

1. Verificabilidade (Grounding): Para cada pedido e cada argumento, você DEVE extrair o trecho exato (verbatim) do texto original que o fundamenta, no campo Tx_Trecho_Comprobatorio. Sem isso, a extração é inválida.

2. Princípio da decomposição por bem da vida: A unidade de pedido, para fins de julgamento dos embargos, é a pretensão juridicamente distinta — aquela que pode receber, em tese, um dispositivo próprio (acolher os embargos quanto ao ponto, ainda que com modificação do julgado, ou rejeitá-los). Sempre que um item formal de pedido na peça de embargos abranger duas ou mais pretensões com regime jurídico próprio (legislação, jurisprudência, tema ou súmula potencialmente aplicáveis distintos), você DEVE desmembrá-lo em pedidos separados, ainda que a parte o tenha redigido como um único pedido.
   - Exemplo (tributário): "afastar a incidência de IRPJ, CSLL, PIS e COFINS sobre os juros de mora" deve gerar 4 pedidos, um para cada tributo (um pedido autônomo e separado para IRPJ, CSLL, PIS e COFINS), pois cada um possui regime próprio e pode estar sujeito a temas/súmulas diferentes.
   - Exemplo (administrativo): "anular a multa moratória e a multa de ofício" deve gerar 2 pedidos, pois cada multa tem natureza jurídica própria.
   - Contraexemplo (NÃO desmembrar): "majorar a indenização por danos morais de R$ 10.000 para R$ 50.000" é um único pedido — o bem da vida é o quantum, e variar o valor não altera o regime jurídico.

3. Princípio da hierarquia (pedidos principais, alternativos, subsidiários e acessórios): Pedidos formulados em alternativa ("ou"), em subsidiariedade ("caso assim não se entenda", "se vencida a preliminar") ou em acessoriedade (consectário, desdobramento ou instrumento do principal) são pedidos juridicamente autônomos e DEVEM ser identificados separadamente. Cada um pode receber dispositivo próprio. A relação entre eles deve ser registrada nos campos Tp_Relacao e Id_PedidoVinculado.
   - Exemplo de subsidiariedade:
     - "acolhimento dos embargos com efeito infringente para anular o acórdão embargado. Caso assim não se entenda, ao menos para reformar o acórdão embargado e julgar procedente o pedido" → 2 pedidos: (a) anular o acórdão (Tp_Relacao=PRINCIPAL) e (b) reformar o acórdão para julgar procedente o pedido (Tp_Relacao=SUBSIDIARIO, Id_PedidoVinculado=1).
     - "acolher os embargos para anular o acórdão por violação ao contraditório e à ampla defesa, assegurando-se à parte o direito de produzir a prova testemunhal indeferida na origem" → 2 pedidos: (a) anular o acórdão (Tp_Relacao=PRINCIPAL) e (b) assegurar o direito de produzir a prova testemunhal (Tp_Relacao=ACESSORIO, Id_PedidoVinculado=1).
     - "acolher os embargos com efeito infringente para reformar o acórdão e condenar a União à restituição do indébito tributário, aplicando-se correção monetária pela SELIC desde o recolhimento e juros de mora desde a citação" → 3 pedidos: (a) condenar a União à restituição do indébito (Tp_Relacao=PRINCIPAL); (b) aplicação da correção monetária pela SELIC (Tp_Relacao=ACESSORIO, Id_PedidoVinculado=1); (c) aplicação de juros de mora desde a citação (Tp_Relacao=ACESSORIO, Id_PedidoVinculado=1).
     - O acessório não subsiste sem o principal: se o principal for rejeitado, o acessório fica prejudicado; se for acolhido, está nele contido. Consectários patrimoniais da condenação — correção monetária, juros de mora, índices de atualização, critérios de cálculo de indébito, base de cálculo de honorários sucumbenciais quando dependente do resultado da condenação — são, em regra, acessórios.

4. Princípio da especificação da pretensão substantiva: O campo Tx_Texto deve descrever a pretensão concreta que os embargos buscam obter, e NÃO apenas a formulação processual genérica. Quando o pedido vier redigido de forma sintética ou genérica (ex.: "acolhimento dos embargos", "seja sanada a omissão apontada"), você DEVE recorrer às razões dos embargos e à decisão ou ao acórdão embargado para identificar qual omissão, contradição, obscuridade, erro material ou ponto de prequestionamento está em causa.
   - Não basta: "Acolher os embargos de declaração."
   - Não basta: "Sanar a omissão apontada."
   - Forma adequada: "Acolher os embargos para sanar a omissão quanto à análise do argumento de inexigibilidade do IRPJ incidente sobre juros de mora em repetição de indébito."
   - Forma adequada (prequestionamento): "Acolher os embargos para que o julgado se manifeste expressamente sobre a alegada violação ao art. 1.022, II, do CPC (prequestionamento ficto)."

5. Princípio da distinção entre pedido e fundamento: As hipóteses de cabimento dos embargos de declaração (omissão, contradição, obscuridade e ambiguidade — art. 1.022 do CPC —, além do erro material e do prequestionamento, admitidos pela jurisprudência) delimitam o objeto do pedido, mas a mera indicação do vício NÃO é um pedido autônomo. Cada pretensão de sanar, integrar, esclarecer, corrigir erro material ou prequestionar um ponto distinto da decisão é um Pedido[]; as razões pelas quais a parte sustenta a existência do vício quanto àquele ponto (ex.: a decisão não analisou o argumento X; o fundamento adotado conflita com o dispositivo; o termo utilizado é impreciso) são Argumentos[] do pedido correspondente, jamais Pedidos[] separados.
   - Exemplo: em embargos que pedem o suprimento da omissão quanto aos juros de mora (pedido), a afirmação de que "a decisão deixou de se manifestar sobre o argumento de que os juros devem incidir a partir da citação" NÃO é um pedido autônomo — é o argumento que demonstra a omissão. Deve ser registrado como argumento do pedido de sanar a omissão quanto aos juros de mora.
   - Critério prático: pergunte-se "este item descreve a pretensão de correção ou esclarecimento de um ponto específico da decisão (sanar, integrar, esclarecer, corrigir erro material, prequestionar ou, excepcionalmente, modificar o julgado), ou descreve o vício e as razões pelas quais ele existiria?". Se a resposta for "o vício e suas razões", o item é argumento, não pedido.

6. Fonte exclusiva no texto fornecido: Você não está autorizada a criar pedidos ou pretensões que não estejam expressa ou implicitamente contidos na peça de embargos. A decomposição autorizada pela regra 2 é apenas analítica — ela divide o que já está na peça, sem acrescentar nada.

## FIELDS READONLY

### Pedidos[] - Lista de Pedidos
Para cada pedido identificado, preencha os campos seguintes.

#### Tx_Texto - Texto do Pedido
- Descreva de forma concisa e específica a pretensão substantiva do pedido, conforme a regra 4 da seção CRITICAL RULES. Não basta a formulação processual genérica (ex.: "acolher os embargos de declaração"); descreva o conteúdo concreto da pretensão (ex.: "Acolher os embargos para sanar a omissão quanto à análise do argumento de inexigibilidade do IRPJ sobre juros de mora em repetição de indébito").

#### Tx_Trecho_Comprobatorio - Trecho Comprobatório
- Cópia do trecho do texto onde o pedido está formulado. Atenção, o texto comprobatório normalmente vem com indicações incorretas de quebras de linha. Leia o texto e entenda onde deve haver quebra de parágrafo e marque apenas as quebras de parágrafo com \n\n. As demais quebras de linha devem ser omitidas.

#### Lo_PedidoDeEfeitoSuspensivo
- Indique se há pedido de atribuição de efeito suspensivo aos embargos.

##### Tp_Relacao (opcional, opções: PRINCIPAL, ALTERNATIVO, SUBSIDIARIO, ACESSORIO, AUTONOMO) - Relação do Pedido
- Indica a relação deste pedido com outros pedidos da lista.
- PRINCIPAL: pedido principal de uma cadeia de pedidos alternativos, subsidiários ou acessórios.
- SUBSIDIARIO: pedido formulado em caráter eventual, para a hipótese de não acolhimento do principal (ex.: "caso assim não se entenda..."). Configura-se quando "Y" só será analisado SE "X" for rejeitado.
- ALTERNATIVO: pedido em alternativa simples ("ou X ou Y"), sem hierarquia entre as opções.
- ACESSORIO: pedido que constitui consectário, desdobramento natural ou instrumento do pedido principal — só faz sentido se o principal for acolhido, e fica logicamente prejudicado se o principal não tiver êxito. Configura-se quando "Y" só será analisado SE "X" for acolhido. Exemplos típicos: (a) desdobramentos processuais: "assegurar o direito de produzir prova X" como consequência de "anular o acórdão por cerceamento de defesa"; (b) consectários patrimoniais da condenação: correção monetária, juros de mora, índice de atualização, critério de cálculo do indébito, base de cálculo de honorários quando atrelada ao resultado da condenação. Cuidado: esses mesmos itens deixam de ser acessórios e se tornam pedido principal/autônomo quando constituem a única matéria dos embargos — ex.: os embargos impugnam apenas o índice de correção monetária aplicado na origem, sem questionar a condenação em si. Nesse caso, Tp_Relacao=AUTONOMO.
- AUTONOMO: pedido sem relação de dependência com outro. Use também quando o pedido for único.
- Quando este campo não se aplicar, deixe em branco (equivale a AUTONOMO).

#### Id_PedidoVinculado (opcional) - Identificador do Pedido Vinculado
- Quando Tp_Relacao for SUBSIDIARIO ou ALTERNATIVO, indique o número (1, 2, 3...) do pedido principal ou alternativo ao qual este se vincula, conforme a ordem da lista Pedidos[].
- Deixe em branco quando Tp_Relacao for PRINCIPAL, AUTONOMO ou não preenchido.

##### Argumentos[] - Lista de Argumentos
Para cada fundamento apresentado para embasar o pedido (a indicação do vício e das razões que o demonstram), preencha os campos seguintes.

###### Tx_Texto - Texto do Argumento
- Descrição concisa do argumento.

###### Tx_Trecho_Comprobatorio - Trecho Comprobatório
- Cópia do trecho do texto onde o argumento está formulado. Atenção, o texto comprobatório normalmente vem com indicações incorretas de quebras de linha. Leia o texto e entenda onde deve haver quebra de parágrafo e marque apenas as quebras de parágrafo com \n\n. As demais quebras de linha devem ser omitidas.

## Tarefa Principal

Identifique os pedidos realizados na peça de embargos de declaração abaixo:

{{textos}}


# FORMAT
{% for d in Pedidos %}{% set outerIndex = loop.index %}**Pedido {= loop.index =} {% if d.Tx_Relacao and d.Tx_Relacao != 'AUTONOMO' %} ({= d.Tx_Relacao | lower =}{% if d.Id_PedidoVinculado %} ao pedido {= d.Id_PedidoVinculado =}{% endif %}){% endif %}:** {% if d.Lo_PedidoDeEfeitoSuspensivo %}[C/ EFEITO SUSPENSIVO] {% endif %}{= d.Tx_Texto =}

> {= d.Tx_Trecho_Comprobatorio | blockquoteLines =}

Argumentos:{% for a in d.Argumentos %}
{= loop.index =}. {= a.Tx_Texto =}

> {= a.Tx_Trecho_Comprobatorio | blockquoteLines =}

{% endfor %}

{% endfor %}
