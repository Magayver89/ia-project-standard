# RULES — Regras do Projeto e da IA

> Este arquivo é obrigatório. Ele define regras que devem ser respeitadas por qualquer pessoa ou IA que altere o projeto. Regras específicas da stack devem ser adicionadas aqui assim que a arquitetura for definida.

## 1. Ordem de leitura obrigatória

Antes de alterar código, leia nesta ordem:

1. `docs/PRD.md`
2. `docs/ARCHITECTURE.md`
3. `docs/RULES.md`
4. `docs/DESIGN.md` quando houver impacto visual
5. `docs/MEMORY.md`
6. `SPEC.md`, `PLAN.md`, `TASKS.md` e demais documentos da feature atual

Não implemente uma feature apenas com base no texto do chat se existir documentação versionada correspondente.

## 2. Regras de escopo

- Execute somente a tarefa ou conjunto de tarefas solicitado.
- Não refatore código não relacionado “aproveitando a oportunidade”.
- Não adicione funcionalidades não especificadas.
- Não remova comportamento existente sem requisito explícito.
- Se uma mudança necessária ultrapassar o escopo, registre o impacto antes de executá-la.
- Prefira mudanças pequenas, revisáveis e reversíveis.

## 3. Regras contra suposições

- Não invente requisitos ausentes.
- Não transforme preferência pessoal em regra do sistema.
- Quando uma decisão bloquear a implementação, use `[NEEDS CLARIFICATION: ...]` na especificação.
- Quando a decisão não bloquear e houver default seguro e convencional, registre a premissa utilizada no `PLAN.md`.

## 4. Arquitetura

- Respeite as fronteiras e responsabilidades definidas em `ARCHITECTURE.md`.
- Não introduza nova dependência estrutural sem justificativa.
- Não crie abstrações antecipadas sem necessidade concreta.
- Reutilize padrões existentes antes de criar um padrão novo.
- Mudanças arquiteturais permanentes exigem atualização de `ARCHITECTURE.md` e registro em `MEMORY.md`.

## 5. Dependências e bibliotecas

### Permitidas / preferenciais

`[Liste bibliotecas obrigatórias ou preferenciais por categoria.]`

### Proibidas / restritas

`[Liste bibliotecas proibidas ou que exigem aprovação.]`

### Regras gerais

- Antes de adicionar uma dependência, verifique se a stack já resolve o problema.
- Fixe versões conforme a política do projeto.
- Não adicione biblioteca apenas para resolver funcionalidade trivial.
- Dependências com impacto de segurança, licença ou infraestrutura devem ser registradas no `PLAN.md`.

## 6. Código

- Siga as convenções nativas da linguagem/framework salvo regra específica deste projeto.
- Nomes devem expressar intenção de domínio.
- Evite funções/classes que acumulem responsabilidades desconexas.
- Evite duplicação relevante, mas não crie abstração prematura para eliminar duas linhas parecidas.
- Comentários devem explicar **por quê**, não repetir **o que** o código já mostra.
- Código morto deve ser removido quando estiver claramente fora de uso e dentro do escopo da tarefa.

## 7. Banco de dados

- Mudanças de schema devem usar o mecanismo de migração definido pela arquitetura.
- Não altere produção manualmente como substituto de migration/script versionado.
- Considere rollback e compatibilidade durante deploy.
- Proteja integridade com constraints quando fizer sentido no banco, não apenas na aplicação.
- Queries devem evitar leitura/escrita desnecessária e problemas óbvios de N+1.
- Alterações destrutivas exigem plano explícito de migração de dados.

## 8. APIs e integrações

- Respeite contratos existentes.
- Breaking changes exigem versionamento ou plano de migração.
- Valide entrada na borda do sistema.
- Integrações externas devem ter timeout definido.
- Retry só deve ser usado para operações seguras/idempotentes ou explicitamente protegidas contra duplicidade.
- Quando houver risco de entrega duplicada, implemente idempotência.
- Não registre tokens, senhas, segredos ou payloads sensíveis em logs.

## 9. Tratamento de erros

- Não silencie exceções sem uma decisão explícita.
- Erro esperado de negócio deve ser tratado como erro de domínio, não como falha interna genérica.
- Falha inesperada deve gerar informação suficiente para diagnóstico sem expor detalhes sensíveis ao usuário.
- Mensagens ao usuário devem ser compreensíveis e orientadas à ação quando possível.
- Logs devem registrar contexto técnico e identificador de correlação quando aplicável.

## 10. Segurança

- Nunca grave segredos no repositório.
- Nunca exponha credenciais em exemplos, logs ou documentação.
- Valide e normalize entradas externas.
- Use queries parametrizadas ou mecanismos equivalentes contra injeção.
- Faça autorização no servidor, não apenas na interface.
- Aplique menor privilégio a credenciais e permissões.
- Dados sensíveis devem seguir as regras de proteção e retenção do projeto.

## 11. Interface e design

Quando houver interface:

- `docs/DESIGN.md` é a fonte de verdade visual.
- Não invente novas cores, espaçamentos ou componentes se já houver padrão definido.
- Reutilize componentes existentes antes de criar duplicatas.
- Estados de loading, vazio, erro, sucesso e desabilitado devem ser considerados.
- Acessibilidade não é opcional quando aplicável ao componente.

## 12. Testes

- Testes devem validar comportamento e contrato, não detalhes acidentais de implementação.
- Critérios de aceitação da `SPEC.md` devem ser verificáveis.
- Correção de bug deve incluir uma forma de reproduzir e validar o problema corrigido.
- Não marque tarefa como concluída se os testes relevantes falharem.
- Se um teste previsto não puder ser executado, registre o motivo e o risco restante.

## 13. Git e mudanças

- Commits devem ser pequenos e coerentes quando o fluxo de trabalho permitir.
- Não misture mudanças sem relação na mesma tarefa.
- Não reescreva histórico compartilhado sem autorização explícita.
- Arquivos gerados automaticamente devem seguir a política do projeto.

## 14. Documentação viva

Ao concluir mudanças:

- Atualize a feature se o comportamento entregue divergir da especificação anterior.
- Atualize `ARCHITECTURE.md` para decisões técnicas que viraram padrão global.
- Atualize `RULES.md` para novas regras permanentes.
- Atualize `DESIGN.md` para novos padrões visuais permanentes.
- Atualize `MEMORY.md` para decisões, incidentes, erros relevantes e aprendizados.
- Atualize tarefas concluídas com status real.

## 15. RULES CHECK obrigatório

Antes de escrever código, responda internamente:

- [ ] Estou atendendo a um requisito existente?
- [ ] A solução respeita a arquitetura atual?
- [ ] Estou usando as bibliotecas e padrões permitidos?
- [ ] A mudança respeita o design system, quando aplicável?
- [ ] Consultei decisões anteriores relevantes em `MEMORY.md`?
- [ ] Os critérios de aceitação estão claros?
- [ ] A tarefa está pequena e delimitada?
- [ ] Estou evitando mudanças fora do escopo?

Se a resposta for “não” em um item obrigatório, pare a implementação e ajuste a documentação/plano primeiro.

## 16. Regras específicas do projeto

> Preencher ao inicializar o projeto.

- `[regra específica 1]`
- `[regra específica 2]`
