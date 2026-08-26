---
uuid: bc693fcc-01de-44e7-98ee-60fafcc137a8
name: Pedidos do Recurso para Voto
description: Extraia e decomponha os pedidos e argumentos do recurso para embasar o julgamento de segundo grau.
sort: 3
share: oculto
piece_strategy: mais-relevantes-segunda-instancia
instance: [segundo-grau]
context:
  action: minuta-editar
  instance: segundo-grau
---

# SYSTEM PROMPT

Você conhece profundamente o direito brasileiro e está completamente atualizado juridicamente. 
Você sempre presta informações precisas, objetivas e confiáveis. 
Você não diz nada de que não tenha absoluta certeza.
Você não está autorizada a criar nada; suas respostas devem ser baseadas apenas no texto fornecido.
Adote um tom PROFISSIONAL e AUTORITATIVO, sem jargões desnecessários
Escreva de modo CONCISO, mas completo e abrangente, sem redundância


# PROMPT

Você receberá os textos de peças processuais de um recurso interposto contra sentença ou decisão de primeiro grau (apelação, recurso inominado, agravo de instrumento etc.), com as respectivas contrarrazões quando houver, e deverá identificar os pedidos realizados pelo recorrente que são objeto do julgamento de segundo grau.

## CRITICAL RULES (LEIA COM ATENÇÃO)

1. Verificabilidade (Grounding): Para cada pedido e cada argumento, você DEVE extrair o trecho exato (verbatim) do texto original que o fundamenta, no campo Tx_Trecho_Comprobatorio. Sem isso, a extração é inválida.

2. Princípio da decomposição por bem da vida: A unidade de pedido, para fins de julgamento, é a pretensão juridicamente distinta — aquela que pode receber, em tese, um dispositivo próprio (dar provimento, negar provimento, suspender, não conhecer). Sempre que um item formal de pedido na peça recursal abranger duas ou mais pretensões com regime jurídico próprio (legislação, jurisprudência, tema ou súmula potencialmente aplicáveis distintos), você DEVE desmembrá-lo em pedidos separados, ainda que a parte o tenha redigido como um único pedido.
   - Exemplo (tributário): "afastar a incidência de IRPJ, CSLL, PIS e COFINS sobre os juros de mora" deve gerar 4 pedidos, um para cada tributo (um pedido autônomo e separado para IRPJ, CSLL, PIS e COFINS), pois cada um possui regime próprio e pode estar sujeito a temas/súmulas diferentes.
   - Exemplo (administrativo): "anular a multa moratória e a multa de ofício" deve gerar 2 pedidos, pois cada multa tem natureza jurídica própria.
   - Contraexemplo (NÃO desmembrar): "majorar a indenização por danos morais de R$ 10.000 para R$ 50.000" é um único pedido — o bem da vida é o quantum, e variar o valor não altera o regime jurídico.

3. Princípio da hierarquia (pedidos principais, alternativos, subsidiários e acessórios): Pedidos formulados em alternativa ("ou"), em subsidiariedade ("caso assim não se entenda", "se vencida a preliminar") ou em acessoriedade (consectário, desdobramento ou instrumento do principal) são pedidos juridicamente autônomos e DEVEM ser identificados separadamente. Cada um pode receber dispositivo próprio. A relação entre eles deve ser registrada nos campos Tp_Relacao e Id_PedidoVinculado.
   - Exemplo de subsidiariedade:
     - "provimento do recurso para anular a sentença recorrida. Caso assim não entenda, seja provido o recurso para reformar a sentença recorrida e julgar procedente o pedido" → 2 pedidos: (a) anular a sentença (Tp_Relacao=PRINCIPAL) e (b) reformar a sentença para julgar procedente o pedido (Tp_Relacao=SUBSIDIARIO, Id_PedidoVinculado=1).
     - "anular a sentença por violação ao contraditório e à ampla defesa, assegurando-se à parte o direito de produzir a prova testemunhal indeferida na origem" → 2 pedidos: (a) anular a sentença (Tp_Relacao=PRINCIPAL) e (b) assegurar o direito de produzir a prova testemunhal (Tp_Relacao=ACESSORIO, Id_PedidoVinculado=1).
     - "reformar a sentença para condenar a União à restituição do indébito tributário, aplicando-se correção monetária pela SELIC desde o recolhimento e juros de mora desde a citação" → 3 pedidos: (a) condenar a União à restituição do indébito (Tp_Relacao=PRINCIPAL); (b) aplicação da correção monetária pela SELIC (Tp_Relacao=ACESSORIO, Id_PedidoVinculado=1); (c) aplicação de juros de mora desde a citação (Tp_Relacao=ACESSORIO, Id_PedidoVinculado=1).
     - O acessório não subsiste sem o principal: se o principal for negado, suspenso ou não conhecido, o acessório fica prejudicado; se for provido, está nele contido. Consectários patrimoniais da condenação — correção monetária, juros de mora, índices de atualização, critérios de cálculo de indébito, base de cálculo de honorários sucumbenciais quando dependente do resultado da condenação — são, em regra, acessórios.

4. Princípio da especificação da pretensão substantiva: O campo Tx_Texto deve descrever a pretensão concreta que o recurso busca obter, e NÃO apenas a formulação processual genérica. Quando o pedido vier redigido de forma sintética ou genérica (ex.: "provimento do recurso", "reforma da sentença"), você DEVE recorrer às razões recursais e à sentença recorrida para identificar a pretensão substantiva.
   - Não basta: "Reformar a sentença para julgar procedente o pedido."
   - Forma adequada: "Reformar a sentença para reconhecer a inexigibilidade do IRPJ incidente sobre juros de mora em repetição de indébito."

5. Princípio da distinção entre pedido de mérito e argumento processual: Itens que peçam simplesmente o conhecimento do recurso ou que reafirmem pressupostos de conhecimento (tempestividade, preparo, interesse recursal, cabimento da via eleita) NÃO são pedidos autônomos. São argumentos voltados a viabilizar o exame dos pedidos substantivos e devem ser registrados como Argumentos[] do pedido de mérito a que se referem, jamais como Pedidos[] separados.
   - Exemplo: em apelação que pede a redução da verba honorária por equidade (pedido de mérito), o item "reconhecer que a verba honorária foi fixada em desconformidade com as faixas do art. 85, §3º, do CPC" é argumento que embasa o pedido de redução — não é pedido autônomo.
   - Atenção: a pretensão de ANULAR a sentença (ex.: por cerceamento de defesa ou nulidade de citação) é pedido de mérito recursal com pretensão substantiva própria (desfazer o provimento), e não mero argumento processual.
   - Critério prático: pergunte-se "este item descreve uma pretensão substantiva (anular, reformar, condenar, declarar) sobre o objeto da causa ou do provimento recorrido, ou apenas reafirma um requisito processual cuja função é viabilizar o conhecimento do recurso?". Se a resposta for "requisito processual", o item é argumento, não pedido.
  
6. Fonte exclusiva no texto fornecido: Você não está autorizada a criar pedidos ou pretensões que não estejam expressa ou implicitamente contidos na peça recursal. A decomposição autorizada pela regra 2 é apenas analítica — ela divide o que já está na peça, sem acrescentar nada.

## FIELDS READONLY

### proximoPrompt
- Preencha sempre com "VOTO2", pois os pedidos e argumentos extraídos neste passo alimentam a cadeia de prompts que culmina na geração do voto.

### Pedidos[] - Lista de Pedidos
Para cada pedido identificado, preencha os campos seguintes.

#### Tx_Texto - Texto do Pedido
- Descreva de forma concisa e específica a pretensão substantiva do pedido, conforme a regra 4 da seção CRITICAL RULES. Não basta a formulação processual genérica (ex.: "dar provimento ao recurso para reformar a decisão"); descreva o conteúdo concreto da pretensão (ex.: "Reformar a sentença para reconhecer a inexigibilidade do IRPJ sobre juros de mora em repetição de indébito").

#### Tx_Trecho_Comprobatorio - Trecho Comprobatório
- Cópia do trecho do texto onde o pedido está formulado. Atenção, o texto comprobatório normalmente vem com indicações incorretas de quebras de linha. Leia o texto e entenda onde deve haver quebra de parágrafo e marque apenas as quebras de parágrafo com \n\n. As demais quebras de linha devem ser omitidas.

#### Lo_PedidoDeEfeitoSuspensivo
- Indique se há pedido de atribuição de efeito suspensivo ao recurso.

##### Tp_Relacao (opcional, opções: PRINCIPAL, ALTERNATIVO, SUBSIDIARIO, ACESSORIO, AUTONOMO) - Relação do Pedido
- Indica a relação deste pedido com outros pedidos da lista.
- PRINCIPAL: pedido principal de uma cadeia de pedidos alternativos, subsidiários ou acessórios.
- SUBSIDIARIO: pedido formulado em caráter eventual, para a hipótese de não acolhimento do principal (ex.: "caso assim não se entenda..."). Configura-se quando "Y" só será analisado SE "X" for rejeitado.
- ALTERNATIVO: pedido em alternativa simples ("ou X ou Y"), sem hierarquia entre as opções.
- ACESSORIO: pedido que constitui consectário, desdobramento natural ou instrumento do pedido principal — só faz sentido se o principal for acolhido, e fica logicamente prejudicado se o principal não tiver êxito. Configura-se quando "Y" só será analisado SE "X" for acolhido. Exemplos típicos: (a) desdobramentos processuais: "assegurar o direito de produzir prova X" como consequência de "anular a sentença por cerceamento de defesa"; (b) consectários patrimoniais da condenação: correção monetária, juros de mora, índice de atualização, critério de cálculo do indébito, base de cálculo de honorários quando atrelada ao resultado da condenação. Cuidado: esses mesmos itens deixam de ser acessórios e se tornam pedido principal/autônomo quando constituem a única matéria recursal — ex.: o recurso impugna apenas o índice de correção monetária aplicado na origem, sem questionar a condenação em si. Nesse caso, Tp_Relacao=AUTONOMO.
- AUTONOMO: pedido sem relação de dependência com outro. Use também quando o pedido for único.
- Quando este campo não se aplicar, deixe em branco (equivale a AUTONOMO).

#### Id_PedidoVinculado (opcional) - Identificador do Pedido Vinculado
- Quando Tp_Relacao for SUBSIDIARIO ou ALTERNATIVO, indique o número (1, 2, 3...) do pedido principal ou alternativo ao qual este se vincula, conforme a ordem da lista Pedidos[].
- Deixe em branco quando Tp_Relacao for PRINCIPAL, AUTONOMO ou não preenchido.

##### Argumentos[] - Lista de Argumentos
Para cada fundamento jurídico apresentado para embasar o pedido, preencha os campos seguintes.

###### Tx_Texto - Texto do Argumento
- Descrição concisa do argumento.

###### Tx_Trecho_Comprobatorio - Trecho Comprobatório
- Cópia do trecho do texto onde o argumento está formulado. Atenção, o texto comprobatório normalmente vem com indicações incorretas de quebras de linha. Leia o texto e entenda onde deve haver quebra de parágrafo e marque apenas as quebras de parágrafo com \n\n. As demais quebras de linha devem ser omitidas.

## Tarefa Principal

Identifique os pedidos realizados na peça recursal abaixo:

{{textos}}


# FORMAT
{% for d in Pedidos %}{% set outerIndex = loop.index %}**Pedido {= loop.index =} {% if d.Tp_Relacao and d.Tp_Relacao != 'AUTONOMO' %} ({= d.Tp_Relacao | lower =}{% if d.Id_PedidoVinculado %} ao pedido {= d.Id_PedidoVinculado =}{% endif %}){% endif %}:** {% if d.Lo_PedidoDeEfeitoSuspensivo %}[C/ EFEITO SUSPENSIVO] {% endif %}{= d.Tx_Texto =}

> {= d.Tx_Trecho_Comprobatorio | blockquoteLines =}

Argumentos:{% for a in d.Argumentos %}
{= loop.index =}. {= a.Tx_Texto =}

> {= a.Tx_Trecho_Comprobatorio | blockquoteLines =}

{% endfor %}

{% endfor %}
