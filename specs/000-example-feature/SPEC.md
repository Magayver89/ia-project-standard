# SPEC — Recuperação de Senha

**ID:** `000`  
**Status:** Example  
**Criada em:** `2026-10-06`

## 1. Problema / oportunidade

Usuários que esquecem a senha precisam recuperar o acesso sem depender de atendimento manual.

## 2. Objetivo

Permitir que um usuário elegível solicite recuperação de senha, receba uma instrução segura e defina uma nova senha dentro de um período limitado.

## 3. Valor para o usuário

Reduz bloqueio de acesso e dependência de suporte para uma operação rotineira.

## 4. Escopo

### Incluído

- Solicitar recuperação informando o identificador da conta.
- Receber instrução de recuperação por canal previamente validado.
- Definir nova senha usando credencial temporária válida.
- Invalidar a credencial temporária após uso ou expiração.

### Não incluído

- Troca de e-mail/telefone da conta.
- Recuperação de conta sem acesso ao canal previamente validado.

## 5. User Stories

### US1 — Solicitar recuperação — P1

**Como** usuário que esqueceu a senha  
**Quero** solicitar a recuperação da minha conta  
**Para** voltar a acessar o sistema sem suporte manual.

**Teste independente:** uma conta elegível consegue iniciar o fluxo e receber uma instrução válida sem revelar se um identificador inexistente pertence ou não ao sistema.

#### Critérios de aceitação

- **AC-US1-01:** Dado um identificador informado, quando o usuário solicitar recuperação, então o sistema deve responder de forma neutra sem revelar a existência da conta.
- **AC-US1-02:** Dado que a conta exista e seja elegível, quando a solicitação for processada, então uma credencial temporária de recuperação deve ser emitida para o canal previamente validado.

### US2 — Definir nova senha — P1

**Como** usuário com credencial temporária válida  
**Quero** definir uma nova senha  
**Para** recuperar o acesso à conta.

#### Critérios de aceitação

- **AC-US2-01:** Dada uma credencial válida e não expirada, quando uma nova senha válida for informada, então a senha da conta deve ser substituída.
- **AC-US2-02:** Depois do uso bem-sucedido, a mesma credencial temporária não pode ser usada novamente.
- **AC-US2-03:** Credencial expirada ou inválida não pode alterar a senha.

## 6. Requisitos funcionais

- **FR-001:** O sistema deve aceitar uma solicitação de recuperação por identificador suportado pelo produto.
- **FR-002:** O sistema não deve revelar publicamente se o identificador pertence a uma conta.
- **FR-003:** A credencial de recuperação deve ter validade limitada.
- **FR-004:** A credencial deve ser de uso único.
- **FR-005:** A nova senha deve respeitar a política global de credenciais do projeto.

## 7. Casos de borda

- Múltiplas solicitações em curto período.
- Usuário bloqueado ou inativo.
- Credencial temporária já utilizada.
- Credencial temporária expirada.
- Falha no provedor responsável pela entrega da instrução.

## 8. Critérios de sucesso

- Um usuário elegível consegue concluir a recuperação sem intervenção manual.
- O fluxo não revela a existência de contas por diferença de resposta pública.

## 9. Questões em aberto

- `[NEEDS CLARIFICATION: qual canal de entrega será usado pelo projeto real — e-mail, SMS ou outro?]`
