# IA Project Standard

Padrão de desenvolvimento orientado por especificações para projetos construídos com auxílio de IA.

O objetivo deste repositório é manter **produto, arquitetura, regras, design, execução e memória técnica** explícitos e versionados junto com o código. O chat é um ambiente de trabalho; os arquivos do projeto são a fonte permanente de verdade.

## Princípio central

> Especifique antes de implementar. O código deve servir à especificação, não substituir a especificação.

O padrão separa dois níveis de documentação:

- `docs/` governa o **projeto inteiro**.
- `specs/` governa **cada funcionalidade**.

A implementação fica em `src/` (ou na estrutura definida em `docs/ARCHITECTURE.md`) e os testes validam o comportamento especificado.

## Estrutura

```text
.
├── README.md
├── docs/
│   ├── PRD.md
│   ├── ARCHITECTURE.md
│   ├── RULES.md
│   ├── DESIGN.md
│   ├── TASKS.md
│   └── MEMORY.md
├── templates/
│   └── feature/
│       ├── SPEC.md
│       ├── PLAN.md
│       ├── TASKS.md
│       ├── RESEARCH.md
│       ├── DATA-MODEL.md
│       └── contracts/
│           └── README.md
└── specs/
    └── 000-example-feature/
        ├── SPEC.md
        ├── PLAN.md
        ├── TASKS.md
        ├── RESEARCH.md
        ├── DATA-MODEL.md
        └── contracts/
            └── README.md
```

> `src/`, `tests/`, `frontend/`, `backend/`, `api/` ou qualquer outra pasta de código só deve ser definida depois da arquitetura do projeto. Este padrão não força uma stack.

## O papel de cada documento global

| Arquivo | Responsabilidade |
|---|---|
| `docs/PRD.md` | Define **o que** será construído, **por quê**, para quem, escopo, requisitos e resultados esperados. |
| `docs/ARCHITECTURE.md` | Define **como** o sistema será organizado tecnicamente: stack, módulos, dados, integrações, fluxos e infraestrutura. |
| `docs/RULES.md` | Define as regras obrigatórias para pessoas e IAs que alteram o projeto. |
| `docs/DESIGN.md` | Define o design system e os padrões visuais para manter consistência de interface. |
| `docs/TASKS.md` | Mantém o roadmap e as tarefas de nível global do projeto. Tarefas detalhadas de uma feature ficam dentro da própria feature. |
| `docs/MEMORY.md` | Mantém decisões, mudanças, erros relevantes, soluções e contexto histórico necessário para continuidade. |

## O papel de cada documento de feature

Cada funcionalidade deve possuir sua própria pasta em `specs/NNN-nome-da-feature/`.

| Arquivo | Responsabilidade |
|---|---|
| `SPEC.md` | Define **o que e por quê**. Deve ser independente de tecnologia sempre que possível. |
| `PLAN.md` | Define **como** a feature será implementada tecnicamente. |
| `TASKS.md` | Divide o plano em tarefas pequenas, rastreáveis e executáveis. |
| `RESEARCH.md` | Registra pesquisas, alternativas consideradas e motivos das decisões técnicas. |
| `DATA-MODEL.md` | Define entidades, relacionamentos, regras de integridade e mudanças de dados. |
| `contracts/` | Define contratos de API, eventos, filas, arquivos ou integrações externas. |

Nem toda feature precisa usar todos os artefatos. Se um documento não se aplica, mantenha-o curto e registre `Não aplicável` com o motivo. Não invente complexidade só para preencher template.

## Fluxo padrão

```text
IDEIA
  ↓
PRD
  ↓
SPEC
  ↓
CLARIFICAÇÃO
  ↓
PLAN
  ↓
TASKS
  ↓
RULES CHECK
  ↓
IMPLEMENTAÇÃO
  ↓
TESTES
  ↓
VALIDAÇÃO
  ↓
MEMORY
```

### RULES CHECK

Antes de implementar, confirme:

- [ ] A mudança respeita `docs/PRD.md`.
- [ ] A solução respeita `docs/ARCHITECTURE.md`.
- [ ] A execução respeita `docs/RULES.md`.
- [ ] Alterações de interface respeitam `docs/DESIGN.md`.
- [ ] `docs/MEMORY.md` foi consultado.
- [ ] A feature possui critérios de aceitação verificáveis.
- [ ] As tarefas estão pequenas o suficiente.
- [ ] Não há alteração fora do escopo sem justificativa explícita.

## Como iniciar um novo projeto

1. Crie um repositório a partir deste padrão.
2. Preencha `docs/PRD.md`.
3. Defina `docs/ARCHITECTURE.md`.
4. Ajuste `docs/RULES.md`.
5. Defina `docs/DESIGN.md` se houver interface.
6. Crie as primeiras fases em `docs/TASKS.md`.
7. Registre decisões iniciais em `docs/MEMORY.md`.
8. Copie `templates/feature/` para `specs/001-nome-da-feature/`.
9. Preencha `SPEC.md` antes de `PLAN.md`.
10. Escreva `TASKS.md` somente depois do plano.

## Convenção de nomes

```text
specs/001-authentication/
specs/002-customer-registration/
specs/003-billing/
specs/004-reporting/
```

## Regra para uso com IA

Ao pedir uma implementação:

> Leia `docs/PRD.md`, `docs/ARCHITECTURE.md`, `docs/RULES.md`, `docs/DESIGN.md` quando aplicável, `docs/MEMORY.md` e todos os documentos da feature atual. Execute somente as tarefas solicitadas em `TASKS.md`. Antes de alterar código, faça o RULES CHECK. Não invente requisitos ausentes e não amplie o escopo sem registrar a necessidade.

## Definition of Done

Uma feature só deve ser considerada concluída quando:

- [ ] Critérios de aceitação relevantes foram atendidos.
- [ ] Tarefas previstas foram concluídas ou reclassificadas com justificativa.
- [ ] Testes previstos foram executados.
- [ ] Erros e caminhos de falha foram tratados.
- [ ] Contratos e modelo de dados estão atualizados.
- [ ] Documentação global afetada foi sincronizada.
- [ ] `MEMORY.md` recebeu decisões e aprendizados relevantes.
- [ ] Não existem `[NEEDS CLARIFICATION]` bloqueadores.

## Filosofia

Documentação aqui não é enfeite e não deve virar burocracia. Ela existe para reduzir ambiguidade, manter continuidade entre pessoas e IAs e permitir que decisões sobrevivam ao chat em que foram tomadas.

Se o documento não ajuda a implementar, validar ou manter o sistema, simplifique-o.
