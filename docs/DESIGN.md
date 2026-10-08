# DESIGN — Design System do Projeto

> Fonte de verdade para decisões visuais e de interação. Se o projeto não possui interface, registre `Não aplicável` e mantenha este arquivo curto.

## 1. Princípios visuais

- `[Princípio 1 — ex.: clareza antes de decoração]`
- `[Princípio 2]`
- `[Princípio 3]`

## 2. Identidade

**Personalidade visual:** `[ex.: sóbria, operacional, moderna, minimalista]`

**Referências:** `[links/nome de sistemas se aplicável]`

## 3. Cores

### Primárias

| Token | Valor | Uso |
|---|---|---|
| `--color-primary` | `[hex/rgb]` | Ação principal |
| `--color-primary-hover` | `[hex/rgb]` | Hover |

### Secundárias

| Token | Valor | Uso |
|---|---|---|
| `--color-secondary` | `[valor]` | `[uso]` |

### Semânticas

| Token | Valor | Uso |
|---|---|---|
| `--color-success` | `[valor]` | Sucesso |
| `--color-warning` | `[valor]` | Atenção |
| `--color-danger` | `[valor]` | Erro/perigo |
| `--color-info` | `[valor]` | Informação |

### Neutras e superfície

| Token | Valor | Uso |
|---|---|---|
| `--color-background` | `[valor]` | Fundo geral |
| `--color-surface` | `[valor]` | Cards/modais |
| `--color-border` | `[valor]` | Bordas |
| `--color-text` | `[valor]` | Texto principal |
| `--color-text-muted` | `[valor]` | Texto secundário |

## 4. Tipografia

- Família principal: `[fonte]`
- Família mono: `[fonte]`
- Peso padrão: `[valor]`
- Peso de destaque: `[valor]`

| Estilo | Tamanho | Peso | Line-height |
|---|---:|---:|---:|
| H1 | `[valor]` | `[valor]` | `[valor]` |
| H2 | `[valor]` | `[valor]` | `[valor]` |
| Body | `[valor]` | `[valor]` | `[valor]` |
| Small | `[valor]` | `[valor]` | `[valor]` |

## 5. Espaçamento

Adote uma escala consistente. Exemplo:

```text
4, 8, 12, 16, 24, 32, 48, 64
```

| Token | Valor |
|---|---:|
| `--space-1` | `[valor]` |
| `--space-2` | `[valor]` |

## 6. Bordas, raio e sombra

- Border radius padrão: `[valor]`
- Border radius de controles: `[valor]`
- Sombra de cards: `[valor]`
- Sombra de modais: `[valor]`

## 7. Layout

- Largura máxima: `[valor]`
- Grid: `[regra]`
- Sidebar: `[regra]`
- Header: `[regra]`
- Densidade de informação: `[regra]`

## 8. Breakpoints

| Nome | Largura | Comportamento esperado |
|---|---:|---|
| Mobile | `[valor]` | `[regra]` |
| Tablet | `[valor]` | `[regra]` |
| Desktop | `[valor]` | `[regra]` |

## 9. Componentes

Para cada componente, defina aparência, estados e regras de uso.

### Button

- Variantes: `[primary, secondary, danger, ghost...]`
- Tamanhos: `[sm, md, lg...]`
- Estados: normal, hover, focus, disabled, loading
- Regra: `[quando usar cada variante]`

### Input / Select / Textarea

- Altura: `[valor]`
- Label: `[regra]`
- Erro: `[regra]`
- Hint: `[regra]`
- Disabled/read-only: `[regra]`

### Table

- Densidade: `[regra]`
- Ordenação: `[regra]`
- Paginação: `[regra]`
- Estado vazio: `[regra]`
- Responsividade: `[regra]`

### Modal / Drawer

- Quando usar: `[regra]`
- Fechamento: `[regra]`
- Ação principal: `[posição/regra]`

### Feedback

- Toast: `[regra]`
- Alert: `[regra]`
- Loading: `[regra]`
- Empty state: `[regra]`
- Skeleton: `[regra]`

## 10. Ícones e imagens

- Biblioteca: `[biblioteca]`
- Tamanho padrão: `[valor]`
- Regra de uso: `[regra]`

## 11. Acessibilidade

- Contraste mínimo: `[regra]`
- Navegação por teclado: `[regra]`
- Focus visible: obrigatório
- Labels acessíveis: obrigatório para controles
- Não depender somente de cor para transmitir estado

## 12. Conteúdo e microcopy

- Tom: `[direto, formal, amigável...]`
- Verbos em botões: `[regra]`
- Mensagens de erro: `[regra]`
- Confirmações destrutivas: `[regra]`

## 13. Padrões proibidos

- Não criar cor fora dos tokens sem registrar aqui.
- Não duplicar componente já existente apenas por diferença cosmética pequena.
- Não usar ícone sem significado compreensível.
- Não esconder erro importante apenas em toast quando o contexto exige mensagem persistente.
- `[outras proibições do projeto]`

## 14. Histórico de mudanças visuais

| Data | Mudança | Motivo |
|---|---|---|
| `[AAAA-MM-DD]` | Design inicial | Início do projeto |
