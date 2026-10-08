# RESEARCH — Recuperação de Senha

## R-001 — Formato da credencial temporária

### Contexto

A recuperação exige uma credencial imprevisível, temporária e de uso único.

### Opções consideradas

1. Token aleatório opaco armazenado de forma protegida.
2. Token auto-contido assinado.

### Decisão do exemplo

Usar token opaco aleatório com armazenamento somente de hash/representação protegida.

### Motivo

Facilita invalidação explícita, uso único e controle de expiração sem depender de blacklist adicional.

### Observação

A decisão deve ser reavaliada conforme a stack, infraestrutura e requisitos do projeto real.
