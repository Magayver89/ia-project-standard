# ARCHITECTURE — Arquitetura do Projeto

> Documento global técnico. Define **como as partes do projeto se organizam e se conectam**. Decisões específicas de uma única feature podem começar em `specs/.../PLAN.md`; quando se tornam padrão do sistema, devem ser refletidas aqui.

## 1. Visão arquitetural

`[Resumo da arquitetura em 1–3 parágrafos.]`

## 2. Contexto do sistema

### Atores externos

- `[Usuário/Sistema 1]`
- `[Sistema externo 2]`

### Fronteiras

`[O que pertence ao sistema e o que fica fora dele.]`

## 3. Stack tecnológica

| Camada | Tecnologia | Versão | Motivo |
|---|---|---|---|
| Backend | `[tecnologia]` | `[versão]` | `[motivo]` |
| Frontend | `[tecnologia]` | `[versão]` | `[motivo]` |
| Banco | `[tecnologia]` | `[versão]` | `[motivo]` |
| Cache/Fila | `[tecnologia]` | `[versão]` | `[motivo]` |
| Infra | `[tecnologia]` | `[versão]` | `[motivo]` |

## 4. Estrutura do repositório

```text
[Descreva a estrutura real escolhida]
```

### Regras de organização

- `[regra 1]`
- `[regra 2]`

## 5. Módulos / bounded contexts

| Módulo | Responsabilidade | Depende de |
|---|---|---|
| `[módulo]` | `[responsabilidade]` | `[dependências]` |

## 6. Fluxos principais

### Fluxo: `[nome]`

```text
Entrada → Validação → Regra de negócio → Persistência → Resposta
```

**Descrição:** `[detalhes importantes]`

## 7. Arquitetura de dados

### Banco(s)

`[bancos utilizados e responsabilidade de cada um]`

### Estratégia de persistência

- `[ORM/query builder/SQL direto/etc.]`
- `[migrações]`
- `[transações]`
- `[concorrência]`

### Convenções de dados

- `[IDs, datas, timezone, soft delete, auditoria, etc.]`

## 8. APIs e contratos

- Padrão: `[REST/GraphQL/RPC/eventos/etc.]`
- Versionamento: `[regra]`
- Autenticação: `[regra]`
- Idempotência: `[regra]`
- Paginação: `[regra]`
- Erros: `[formato]`

Detalhes específicos ficam em `specs/<feature>/contracts/`.

## 9. Integrações externas

| Integração | Direção | Protocolo | Autenticação | Tratamento de falha |
|---|---|---|---|---|
| `[serviço]` | Entrada/Saída | `[HTTP/etc.]` | `[método]` | `[estratégia]` |

## 10. Autenticação e autorização

- Método de autenticação: `[método]`
- Modelo de autorização: `[RBAC/ABAC/etc.]`
- Sessão/token: `[regra]`
- Dados sensíveis: `[regra]`

## 11. Tratamento de erros

- `[como erros de domínio são representados]`
- `[como exceções inesperadas são tratadas]`
- `[o que pode ou não aparecer ao usuário]`
- `[retry/circuit breaker quando aplicável]`

## 12. Observabilidade

### Logs

`[estrutura, níveis, correlação, dados proibidos]`

### Métricas

`[métricas mínimas]`

### Tracing

`[se aplicável]`

## 13. Segurança

- `[gestão de segredo]`
- `[validação de entrada]`
- `[criptografia]`
- `[proteção de endpoints]`
- `[auditoria]`
- `[dependências e atualizações]`

## 14. Performance e escala

- Meta de latência: `[meta]`
- Volume esperado: `[volume]`
- Concorrência esperada: `[volume]`
- Estratégia de cache: `[estratégia]`
- Gargalos conhecidos: `[itens]`

## 15. Ambientes e deploy

| Ambiente | Objetivo | Dados | Deploy |
|---|---|---|---|
| Dev | Desenvolvimento | `[tipo]` | `[forma]` |
| Staging | Homologação | `[tipo]` | `[forma]` |
| Produção | Operação | `[tipo]` | `[forma]` |

## 16. Estratégia de testes

- Unitários: `[escopo]`
- Integração: `[escopo]`
- Contrato: `[escopo]`
- E2E: `[escopo]`
- Manual: `[quando necessário]`

## 17. Decisões arquiteturais consolidadas

| ID | Decisão | Motivo | Data |
|---|---|---|---|
| ADR-001 | `[decisão]` | `[motivo]` | `[AAAA-MM-DD]` |

> O histórico detalhado e incidentes ficam em `MEMORY.md`.

## 18. Restrições conhecidas

- `[restrição 1]`

## 19. Questões em aberto

- `[NEEDS CLARIFICATION: questão técnica]`
