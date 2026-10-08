# PLAN — Recuperação de Senha

**Feature:** `SPEC.md`  
**Status:** Example  
**Data:** `2026-10-06`

> Exemplo propositalmente genérico. Adapte à stack definida no projeto real.

## 1. Resumo técnico

Criar um serviço de recuperação que gere token criptograficamente seguro, armazene somente representação protegida, aplique validade e uso único, envie instrução por um provedor abstraído já adotado pelo projeto e permita substituição da senha em transação segura.

## 2. Impacto na arquitetura

- Autenticação: novo fluxo de recuperação.
- Persistência: armazenamento temporário de solicitação/token.
- Integração: provedor de entrega de mensagem.
- Segurança: rate limit, resposta neutra e invalidação de token.

## 3. Fluxo proposto

```text
Solicitação
  → validar formato
  → responder de forma neutra
  → localizar conta internamente
  → verificar elegibilidade/rate limit
  → gerar token seguro
  → persistir hash + expiração
  → enviar instrução

Redefinição
  → validar token
  → validar expiração/uso
  → validar nova senha
  → alterar senha em transação
  → invalidar token
  → registrar evento de segurança
```

## 4. Modelo de dados

Ver `DATA-MODEL.md`.

## 5. Contratos

Ver `contracts/README.md`.

## 6. Tratamento de erros

- Falha do provedor de entrega deve ser registrada e tratada sem expor existência da conta ao solicitante.
- Token inválido/expirado retorna mensagem funcional equivalente.
- Alteração de senha deve ser atômica com a invalidação do token sempre que a tecnologia permitir.

## 7. Segurança

- Token aleatório de alta entropia.
- Não armazenar token puro.
- Uso único e expiração.
- Rate limit por identificador e origem conforme política do projeto.
- Resposta pública neutra na solicitação.
- Não registrar token em logs.

## 8. Estratégia de testes

- Unitário: validade, uso único e política de senha.
- Integração: persistência + consumo do token.
- Contrato: respostas públicas equivalentes para conta existente/inexistente.
- Segurança: token expirado, reutilização e excesso de solicitações.

## 9. RULES CHECK

- [x] Especificação separa comportamento de implementação.
- [x] Segurança e tratamento de erro considerados.
- [x] Não há alteração de escopo além da recuperação de senha.
- [ ] Stack e caminhos reais devem ser preenchidos no projeto que usar este exemplo.
