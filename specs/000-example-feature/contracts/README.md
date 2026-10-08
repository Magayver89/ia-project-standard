# Contracts — Recuperação de Senha

> Exemplo conceitual. Nomes de rotas e formato final devem seguir a arquitetura do projeto real.

## Solicitar recuperação

### Entrada conceitual

```json
{
  "identifier": "usuario@exemplo.com"
}
```

### Resposta pública

A resposta deve ser semanticamente neutra, por exemplo:

```json
{
  "message": "Se a conta for elegível, as instruções de recuperação serão enviadas."
}
```

O comportamento público não deve permitir enumeração de contas.

## Definir nova senha

### Entrada conceitual

```json
{
  "token": "credencial-temporaria",
  "new_password": "nova-senha"
}
```

### Resultado esperado

- Token válido: senha alterada e token invalidado.
- Token inválido, expirado ou já usado: alteração rejeitada sem expor informação sensível.
