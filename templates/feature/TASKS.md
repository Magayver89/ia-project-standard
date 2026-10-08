# TASKS — [NOME DA FEATURE]

**Spec:** `SPEC.md`  
**Plan:** `PLAN.md`

## Convenção

```text
T001 [P] [US1] Descrição objetiva com caminho do arquivo
```

- `[P]`: pode executar em paralelo sem conflito conhecido.
- `[USx]`: User Story relacionada.
- Cada tarefa deve produzir resultado verificável.
- Prefira tarefas pequenas que possam ser implementadas e revisadas isoladamente.

## Fase 1 — Preparação

- [ ] T001 `[criar/ajustar estrutura necessária]`
- [ ] T002 [P] `[configuração independente]`

## Fase 2 — Fundação

- [ ] T010 `[infraestrutura compartilhada que bloqueia stories]`

**Checkpoint:** fundação pronta para iniciar as User Stories.

## Fase 3 — US1 `[TÍTULO]` — P1

**Objetivo:** `[resultado da story]`

**Teste independente:** `[como validar]`

### Testes

- [ ] T020 [P] [US1] `[teste de contrato/integração/unitário]`

### Implementação

- [ ] T021 [P] [US1] `[modelo/componente]` em `[caminho]`
- [ ] T022 [US1] `[serviço/regra]` em `[caminho]`
- [ ] T023 [US1] `[endpoint/tela/integração]` em `[caminho]`
- [ ] T024 [US1] Validar critérios `AC-US1-*`

**Checkpoint:** US1 funcional e validada de forma independente.

## Fase 4 — US2 `[TÍTULO]` — P2

- [ ] T030 [US2] `[tarefa]`

## Fase final — Convergência

- [ ] T090 Executar testes relevantes da feature
- [ ] T091 Validar critérios de aceitação da `SPEC.md`
- [ ] T092 Revisar tratamento de erro, segurança e logs
- [ ] T093 Atualizar documentação afetada
- [ ] T094 Registrar decisões/aprendizados relevantes em `docs/MEMORY.md`

## Dependências

| Tarefa | Depende de |
|---|---|
| T022 | T021 |

## Definition of Done

- [ ] Todos os critérios de aceitação entregues estão validados.
- [ ] Testes previstos passam.
- [ ] Não há tarefa marcada como concluída sem verificação.
- [ ] Documentação impactada está sincronizada.
- [ ] Não há mudança fora do escopo sem registro explícito.
