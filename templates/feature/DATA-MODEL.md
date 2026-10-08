# DATA-MODEL — [NOME DA FEATURE]

> Modelo técnico dos dados envolvidos na feature. Deve estar alinhado ao `SPEC.md` e às convenções globais de `ARCHITECTURE.md`.

## 1. Entidades

### `[Entidade]`

**Responsabilidade:** `[o que representa]`

| Campo | Tipo lógico | Obrigatório | Regra |
|---|---|---:|---|
| `id` | Identificador | Sim | `[regra]` |
| `[campo]` | `[tipo]` | Sim/Não | `[regra]` |

## 2. Relacionamentos

```text
[Entidade A] 1 ─── N [Entidade B]
```

- `[explicação]`

## 3. Constraints e integridade

- `[unique]`
- `[foreign key]`
- `[check/regra]`

## 4. Índices

| Índice | Campos | Motivo |
|---|---|---|
| `[nome]` | `[campos]` | `[consulta/constraint]` |

## 5. Estados e transições

```text
[Pendente] → [Ativo] → [Encerrado]
```

Regras:
- `[regra]`

## 6. Migração

### Criação/alteração

`[descrição]`

### Backfill

`[Não aplicável ou estratégia]`

### Compatibilidade durante deploy

`[estratégia]`

### Rollback

`[estratégia]`

## 7. Retenção / exclusão

`[política]`

## 8. Dados sensíveis

`[campos e proteção]`
