# TASKS — Recuperação de Senha

> Exemplo de granularidade. Os caminhos devem ser substituídos pelos caminhos reais do projeto.

## Fundação

- [ ] T001 [US1] Definir contrato real da solicitação de recuperação em `contracts/`.
- [ ] T002 [US2] Definir contrato real da redefinição em `contracts/`.
- [ ] T003 [P] Criar migração/estrutura para credenciais temporárias conforme `DATA-MODEL.md`.

## US1 — Solicitar recuperação

- [ ] T010 [P] [US1] Criar teste que comprove resposta pública neutra para conta existente e inexistente.
- [ ] T011 [US1] Implementar geração segura e persistência protegida da credencial temporária.
- [ ] T012 [US1] Implementar expiração e limitação de solicitações.
- [ ] T013 [US1] Integrar o envio da instrução ao provedor definido pelo projeto.
- [ ] T014 [US1] Validar `AC-US1-01` e `AC-US1-02`.

## US2 — Definir nova senha

- [ ] T020 [P] [US2] Criar testes para token inválido, expirado e reutilizado.
- [ ] T021 [US2] Implementar validação da nova senha.
- [ ] T022 [US2] Implementar consumo atômico da credencial e alteração da senha.
- [ ] T023 [US2] Registrar evento de segurança sem dados sensíveis.
- [ ] T024 [US2] Validar `AC-US2-01`, `AC-US2-02` e `AC-US2-03`.

## Convergência

- [ ] T090 Executar testes relevantes.
- [ ] T091 Revisar logs para garantir ausência de tokens/segredos.
- [ ] T092 Atualizar `docs/MEMORY.md` com decisões do projeto real.
