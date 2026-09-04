# AGENTS.md — diretrizes para agentes de IA

Este repositório (`apoia-prompts`) é o banco de prompts em Markdown consumido pela plataforma **apoia**. Cada `.md` (com frontmatter YAML) é um prompt.

A maior parte de cada arquivo é prosa livre e pode ser editada normalmente. A exceção é a seção iniciada por **`## FIELDS`** ou **`## FIELDS READONLY`**: ela é **estrutural**, processada por código, e precisa ter sua sintaxe e organização preservadas. Ao editar prompts, **não reorganize, reformate ou "embeleze" essa seção** — siga as regras abaixo.

## Como a seção FIELDS funciona

O parser está no projeto irmão: `../apoia/lib/ai/auto-json.ts` (testes com exemplos de gramática: `../apoia/__tests__/auto-json.test.ts`). Em tempo de execução, a plataforma:

1. Localiza a linha exata `## FIELDS` ou `## FIELDS READONLY` e interpreta os headings `###` a `######` do bloco como a definição das variáveis de saída do modelo;
2. Gera automaticamente o **JSON Schema** da resposta a partir desses headings e o envia como structured output;
3. Insere, antes do marcador, um bloco fixo de instruções de preenchimento que contém o placeholder `{{jsonSchema}}` — por isso esses placeholders e o campo `errorMessage` (sempre acrescentado ao schema) **não devem ser escritos manualmente** no markdown.

### `## FIELDS` vs `## FIELDS READONLY`

A gramática dos dois é idêntica. A diferença é apenas o comportamento na UI (`isInformationExtractionPrompt()` do parser):

| Marcador | Efeito |
|---|---|
| `## FIELDS` | resultado exibido como **formulário editável** pelo usuário |
| `## FIELDS READONLY` | mesmo parsing/schema, mas resultado exibido **somente leitura** |

Nunca troque um pelo outro, nem adicione/remova o sufixo `READONLY`, nem crie variações (ex.: `## Fields`, `## CAMPOS`, `## FIELDS (readonly)`) — só as duas formas exatas são reconhecidas. Use **um único marcador por arquivo**; se houver mais de um, apenas o primeiro bloco é considerado.

## Gramática do bloco

### Limites do bloco

- A linha do marcador deve conter **exatamente** `## FIELDS` ou `## FIELDS READONLY`, sozinha na linha.
- O bloco vai do marcador até o **próximo heading de nível 1 ou 2** (`# ` ou `## `) ou até o fim do arquivo. Em geral ele é a última seção do prompt.
- **Nunca insira headings `#`/`##` dentro do bloco** — isso trunca silenciosamente o parsing.

### Headings = estrutura do JSON

- `###` (nível 3) abre os campos-raiz; cada heading de nível mais profundo aninha sob o heading anterior de nível menos profundo (a lacuna de níveis é permitida: `###` → `#####` é válido).
- Heading com filhos = objeto; heading sem filhos = campo primitivo.
- `######` (nível 6) só pode ser campo primitivo — nunca objeto, nunca array (erro de parsing).

### Sintaxe do heading

```
### Nome[] (opcional, opções: VALOR1, VALOR2) - Rótulo do campo
```

- **Nome** — texto antes do primeiro ` - `. Vira o nome da propriedade no JSON, sanitizado automaticamente (acentos removidos, espaços → `_`, caracteres inválidos removidos, máx. 64 caracteres). **Nomes duplicados no mesmo nível causam erro de parsing.**
- **`[]`** — sufixo de array: com filhos → array de objetos; sem filhos → array de primitivos (tipo inferido do nome).
- **`(opcional)`** — o campo permanece obrigatório no schema, mas passa a aceitar `null`.
- **`(opções: A, B, C)`** — enum; só é válido em primitivos e arrays primitivos (nunca em objetos/arrays de objetos). Cuidado: `opções:` consome tudo o que vier depois dele dentro dos parênteses — por isso `opcional` deve vir **antes** de `opções:`.
- **`- Rótulo`** — texto após o primeiro ` - `, usado como rótulo de exibição na UI.

### Tipos primitivos por prefixo do nome

| Prefixo | Tipo | Preenchimento |
|---|---|---|
| `Dt_` | data | dd/mm/aaaa |
| `Ma_` | mês/ano | mm/aaaa |
| `Ev_` | string | número do evento |
| `Nr_` | number | número |
| `Lo_` | boolean | `true`/`false` |
| `Tx_` | string | texto curto (≤ 300 caracteres) |
| `Tg_` | string | texto longo, multilinha |

Sem prefixo: nome contendo "texto", "resumo" ou "conclusão" → texto longo; caso contrário → string. O prefixo é a forma recomendada de tipar um campo.

### Descrições e instruções

- A **primeira** linha não-heading após um heading vira a descrição do campo (exibida na UI). As linhas seguintes (bullets) são ignoradas pelo parser, mas chegam ao modelo como texto do prompt — é nelas que ficam as instruções de preenchimento.
- O JSON Schema gerado **não contém descrições**: a estrutura chega ao modelo pelo schema e as instruções pelo texto do prompt.

### Achatar (flatten) e unicidade de nomes

Quando o schema é gerado a partir do markdown, os objetos intermediários são **dissolvidos**: campos aninhados sobem para a raiz (o aninhamento serve para agrupar a exibição na UI) e os itens de arrays ficam com seus campos primitivos diretos. Consequência prática: **nomes de campos devem ser globalmente únicos** — dois campos com o mesmo nome em ramos diferentes do colapso colidem e um deles se perde silenciosamente no schema. Os prefixos (`Tx_`, `Dt_`, ...) ajudam a garantir isso.

### Exemplo mínimo válido

```markdown
## FIELDS

### processo - Dados do Processo
Informações gerais do processo.

#### Tx_Classe - Classe Processual
- Classe do processo.

#### Dt_Distribuicao (opcional) - Data de Distribuição
- Data de distribuição, se houver.

#### pedidos[] - Pedidos
##### Tx_Texto - Texto do Pedido
- Texto integral do pedido.

##### dispositivo (opções: DAR_PROVIMENTO, NEGAR_PROVIMENTO) - Dispositivo
- Resultado pretendido para o pedido.

### Lo_Tutela_Urgencia (opcional) - Tutela de Urgência
- Indicar se há pedido de tutela de urgência.
```

Erros de parsing que o bloco não pode conter: array ou objeto em heading nível 6, nomes duplicados no mesmo nível, `opções:` em objeto/array de objetos, metadado desconhecido nos parênteses (só `opcional` e `opções:` são aceitos).

## Regras de edição para o agente

**Nunca faça** (salvo se o pedido do usuário for explicitamente sobre isso):

1. Remover, renomear, mover ou reformular a linha `## FIELDS` / `## FIELDS READONLY`;
2. Alterar o nível (`###`…`######`) de headings existentes, ou convertê-los em negrito, lista, tabela, texto corrido ou code fence;
3. Inserir headings `#`/`##` dentro do bloco, ou reordenar campos;
4. Renomear campos, alterar enums, adicionar/remover campos ou trocar `## FIELDS` por `## FIELDS READONLY` (e vice-versa) — isso muda o **contrato JSON** de saída e pode quebrar a UI e integrações que consomem o resultado;
5. "Embelezar" o bloco: padronizar capitalização, remover/normalizar `(opcional)`, `[]` ou prefixos, refazer o exemplo em outro formato;
6. Escrever manualmente `errorMessage` ou `{{jsonSchema}}`;
7. Alterar o frontmatter YAML (em especial o `uuid`, cuja duplicidade é validada no pre-commit).

**Pode fazer** (conforme o pedido):

- Editar livremente a prosa fora do bloco;
- Ajustar as instruções de preenchimento (bullets) sob um campo, ou a descrição do campo (primeira linha após o heading);
- Incluir/excluir/alterar campos e opções seguindo estritamente a gramática acima, conferindo colisão de nomes no mesmo nível (e, de preferência, no arquivo todo) e o tipo correto pelo prefixo.

Em caso de dúvida sobre o efeito de uma mudança, consulte o parser em `../apoia/lib/ai/auto-json.ts` antes de editar.

## Como validar alterações

1. **Pre-commit**: com o hook ativo (`git config core.hooksPath .githooks`), todo commit envia os `.md` para o endpoint de validação do apoia e falha se houver erro estrutural ou UUID duplicado.
2. **Validação local do parsing** (sem commit): crie um teste temporário no projeto irmão e rode-o:

```ts
// ../apoia/__tests__/validar-prompt.test.ts (apagar depois)
import { readFileSync } from 'fs'
import { parsePromptVariablesFromMarkdown } from '@/lib/ai/auto-json'

const md = readFileSync('../apoia-prompts/<arquivo>.md', 'utf-8')
test('bloco FIELDS parseia sem erros', () => {
  expect(parsePromptVariablesFromMarkdown(md)).toBeDefined()
})
```

```bash
cd ../apoia && npx jest --silent -- validar-prompt.test.ts
```
