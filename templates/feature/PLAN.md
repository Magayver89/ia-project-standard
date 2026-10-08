# PLAN — [NOME DA FEATURE]

**Feature:** `specs/[NNN-feature]/SPEC.md`  
**Status:** Draft | Ready | In Progress | Implemented  
**Data:** `[AAAA-MM-DD]`

> Este documento define **COMO** a especificação será implementada.

## 1. Resumo técnico

`[Abordagem técnica em poucas linhas.]`

## 2. Requisitos atendidos

- `[FR-001]`
- `[FR-002]`

## 3. Contexto técnico

- **Linguagem/versão:** `[valor]`
- **Framework:** `[valor]`
- **Dependências principais:** `[valor]`
- **Banco/storage:** `[valor]`
- **Plataforma alvo:** `[valor]`
- **Ferramentas de teste:** `[valor]`

## 4. Impacto na arquitetura

### Componentes afetados

- `[módulo/serviço]`

### Novos componentes

- `[componente]`

### Fluxo proposto

```text
Entrada → Validação → Serviço de domínio → Persistência/Integração → Resposta
```

## 5. Arquivos / pastas previstos

```text
[caminhos reais ou planejados]
```

## 6. Modelo de dados

Resumo: `[resumo]`

Detalhamento: `DATA-MODEL.md`

### Migrações

- `[migration necessária]`
- Estratégia de rollback: `[estratégia]`

## 7. Contratos

- `[API/evento/fila/arquivo]` → `contracts/[arquivo]`

## 8. Validação e regras de negócio

- `[regra]`

## 9. Tratamento de erros

| Cenário | Tratamento | Retorno/efeito |
|---|---|---|
| `[erro]` | `[tratamento]` | `[resultado]` |

## 10. Segurança

- Autorização: `[regra]`
- Dados sensíveis: `[regra]`
- Proteções específicas: `[regra]`

## 11. Idempotência / concorrência

`[Não aplicável ou estratégia.]`

## 12. Observabilidade

- Logs: `[o que registrar]`
- Métricas: `[o que medir]`
- Alertas: `[se aplicável]`

## 13. Estratégia de testes

| Tipo | O que validar |
|---|---|
| Unitário | `[itens]` |
| Integração | `[itens]` |
| Contrato | `[itens]` |
| E2E/manual | `[itens]` |

## 14. Sequência de implementação

1. `[passo]`
2. `[passo]`
3. `[passo]`

## 15. RULES CHECK

- [ ] Respeita `docs/PRD.md`.
- [ ] Respeita `docs/ARCHITECTURE.md`.
- [ ] Respeita `docs/RULES.md`.
- [ ] Respeita `docs/DESIGN.md`, se aplicável.
- [ ] Consultou decisões relevantes em `docs/MEMORY.md`.
- [ ] Não amplia escopo sem justificativa.
- [ ] Critérios de aceitação são verificáveis.
- [ ] Dependências novas estão justificadas.
- [ ] Riscos de segurança e migração foram considerados.

## 16. Riscos

| Risco | Impacto | Mitigação |
|---|---|---|
| `[risco]` | `[impacto]` | `[ação]` |

## 17. Rollback

`[Como desfazer implantação/migração caso necessário.]`

## 18. Decisões a promover para documentação global

- `[Nenhuma / decisão que deve atualizar ARCHITECTURE.md, RULES.md ou DESIGN.md]`
