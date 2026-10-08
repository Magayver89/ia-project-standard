# Contracts — [NOME DA FEATURE]

Use esta pasta para contratos que precisam ser claros antes da implementação: APIs, eventos, filas, webhooks, formatos de arquivo, protocolos internos ou integrações externas.

## Regras

- Contrato deve ser explícito e versionável.
- Campos obrigatórios e opcionais devem estar identificados.
- Erros esperados devem estar descritos.
- Breaking changes exigem estratégia de compatibilidade/migração.
- Não inclua segredos reais em exemplos.

## Exemplos de arquivos

```text
contracts/
├── openapi.yaml
├── webhook-events.md
├── queue-messages.md
└── import-file.csv.md
```

## Exemplo de contrato HTTP

### `POST /example`

**Objetivo:** `[objetivo]`

**Autorização:** `[regra]`

**Request**

```json
{
  "example": "value"
}
```

**Resposta de sucesso — 201**

```json
{
  "id": "..."
}
```

**Erros esperados**

| Status | Código | Quando |
|---:|---|---|
| 400 | `VALIDATION_ERROR` | Entrada inválida |
| 409 | `CONFLICT` | Recurso já existente |
