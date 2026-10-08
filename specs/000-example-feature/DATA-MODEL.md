# DATA-MODEL — Recuperação de Senha

## Entidade: PasswordResetRequest

**Responsabilidade:** representar uma solicitação temporária de recuperação sem armazenar a credencial em texto puro.

| Campo lógico | Obrigatório | Regra |
|---|---:|---|
| `id` | Sim | Identificador único |
| `user_id` | Sim | Referência da conta |
| `token_hash` | Sim | Nunca armazenar token puro |
| `expires_at` | Sim | Deve estar no futuro na criação |
| `used_at` | Não | Preenchido após consumo |
| `created_at` | Sim | Auditoria |

## Constraints

- `token_hash` deve ser único.
- Solicitação usada não pode voltar ao estado disponível.
- Solicitação expirada não pode ser consumida.

## Índices

- Índice em `token_hash` para validação.
- Índice em `user_id, created_at` para rate limit/limpeza.

## Estados

```text
AVAILABLE → USED
AVAILABLE → EXPIRED
```

## Retenção

Solicitações usadas ou expiradas devem seguir a política de retenção definida no projeto real e podem ser removidas por rotina de limpeza.
