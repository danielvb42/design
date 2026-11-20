# Marinho

Marinho é a variação do Violeta em que o violeta e todos os seus tons são substituídos pelo azul-marinho **#03156F** e sua escala. É uma linguagem de design para painéis e dashboards, derivada da paleta do mockup financeiro "Venus": um azul-marinho profundo como única cor de marca, um azul-marinho no lugar do preto e um fundo branco-lavanda frio onde cards brancos flutuam. É uma linguagem calma, numérica e direta — o número é o herói de cada card.

## Princípios

1. **Uma cor manda.** `primary` (azul-marinho `#03156F`) é a única cor de marca. Ela aparece em poucos lugares, mas sempre nos mais importantes: a ação principal, o card de destaque, a linha do gráfico.
2. **Marinho, nunca preto.** Todo texto forte é `ink` (`#1F2459`). Preto puro quebra a temperatura fria da paleta.
3. **O número primeiro.** Em cada card, o valor (`stat`, `stat-lg`) é o maior elemento; o rótulo vem acima, pequeno e em `ink-muted`.
4. **Separar com espaço, não com linhas.** Cards brancos sobre `bg` com `shadow-card` quase invisível. `line` só onde for indispensável (campos, tabelas densas).
5. **Cor de status é significado.** Verde = positivo/no ritmo, vermelho = negativo. Nunca decorativos. Sempre acompanhados de sinal (+/−) ou ícone, nunca só pela cor.
6. **Cantos generosos.** Raios grandes (`radius-lg` 24px, `radius-xl` 32px) e botões em pílula dão o tom amigável.

## Cores

**Escala marinho** (claro): `navy-50` #EEF1FB · `navy-100` #DCE2F6 · `navy-300` #8E9DD9 · `navy-500` #2A3FA0 · `navy-600` **#03156F** · `navy-700` #020E4F. No noturno a marca clareia para #2F47C2 — o #03156F puro teria 1,2:1 contra o fundo escuro e sumiria; texto de marca no noturno usa `navy-300` #8FA2F0.

| Papel | Token | Claro | Noturno |
|---|---|---|---|
| Marca | `primary` | `#03156F` | `#2F47C2` |
| Degradê de destaque | `gradient-start` → `gradient-end` | `#2A3FA0` → `#03156F` | `#3D57D6` → `#2F47C2` |
| Fundo da página | `bg` | `#F4F6FD` | `#0E1030` |
| Cards | `surface` | `#FFFFFF` | `#171A42` |
| Texto forte | `ink` | `#1F2459` | `#EEF0FF` |
| Texto de apoio | `ink-muted` | `#626891` | `#A6ABD3` |
| Positivo | `success` / `success-soft` / `success-ink` | `#1FCB8A` / `#E2F8EF` / `#07774F` | — |
| Negativo | `danger` / `danger-soft` / `danger-ink` | `#FF5266` / `#FFE9EC` / `#D21F3C` | — |
| Categorias | `info`, `warning` (+ `-soft`, `-ink`) | azul `#2F6BE8`, âmbar `#F7B500` | — |

**Proporção sugerida:** ~70% `bg` + `surface`, ~20% `ink`/`ink-muted`, ~8% azul-marinho, ~2% status.

**Contraste.** Todo par de texto descrito nos tokens passa 4,5:1 nos dois temas. Duas cores do mockup original não passam e foram mantidas só para usos não textuais: o cinza-lavanda `ink-subtle` (`#A3A8C7`, 2,3:1 — ícones inativos e decoração; placeholder usa `ink-muted`) e o verde `success` (`#1FCB8A`, 2,1:1 — ícones e marcadores). Para texto, use sempre `ink-muted` e `success-ink`.

**Degradê.** Só existe um: 135°, de `gradient-start` para `gradient-end`, usado em no máximo dois cards de destaque por tela (KPI principal, cartão de crédito). Texto sobre ele é sempre `on-primary` (branco), e os ícones-linha decorativos ficam em branco com 60% de opacidade.

## Tipografia

Uma família: **Plus Jakarta Sans** (Google Fonts, pesos 400–700), geométrica e com números largos, próxima à do mockup. Fallback `Segoe UI`, `system-ui`.

- Títulos e números em **700**, com tracking levemente negativo (−0,01 a −0,02em) a partir de 28px.
- Valores monetários sempre com `font-variant-numeric: tabular-nums` para alinhar colunas.
- Texto de lista em **600** (`body`), metadados em **500** (`body-sm`) e `ink-muted`.
- Escala: `display` 48 · `heading-1` 40 · `stat-lg` 40 · `stat` 30 · `heading-2` 28 · `heading-3` 22 · `body-lg` 18 · `amount` 18 · `body` 16 · `body-sm` 14 · `caption` 12.

Carregue a fonte com:

```html
<link href="https://fonts.googleapis.com/css2?family=Plus+Jakarta+Sans:wght@400;500;600;700&display=swap" rel="stylesheet">
```

## Espaço, forma e profundidade

- **Grade:** base de 4px; gutter entre cards `space-6` (32px); padding de cards `space-5` (24px, KPIs) a `space-7` (48px, promo).
- **Raios:** `radius-sm` 8 (badges) · `radius-md` 14 (busca, mini-cards) · `radius-lg` 24 (KPIs) · `radius-xl` 32 (cards grandes) · `radius-pill` (botões, bolhas de ícone, barras).
- **Sombras:** `shadow-card` em todo card; `shadow-float` para mini-cards sobre outro card; `shadow-glow` (azul-marinho) só sob o botão primário e os cards em degradê.

## Dados e gráficos

- Série principal: linha de 3px em `primary`, área preenchida com `navy-50` → transparente. Curvas suaves (spline), sem pontos marcados.
- Barras: pílulas finas (8–10px) em `primary` sobre trilho `navy-100`; a barra do período atual pode ser mais curta e as demais completas, como no mockup.
- Séries adicionais: `navy-300`, depois `info`, depois `warning`. Evite verde e vermelho para séries — eles significam variação.
- Variação percentual sempre como badge (`Badge`) ao lado do número: `success-soft`/`success-ink` ou `danger-soft`/`danger-ink`, com sinal explícito.

## Iconografia

Ícones-linha de 24px, traço 1,75–2px, cantos arredondados (estilo Lucide/Tabler). Em listas, o ícone fica numa **bolha circular** de 48px com fundo `-soft` da categoria e o traço na cor cheia da categoria (`info`, `success`, `warning`, `primary`). Nada de emoji.

## Voz

Curta, amigável e numérica. Saudação pelo nome ("Olá, Daniel"), títulos com verbo ou substantivo direto ("Saldo", "Suas transferências"), ações com verbo no infinitivo ("Ver tudo", "Experimentar grátis"). Valores em formato brasileiro: `R$ 1.234,56`, `+2,45%`, `Hoje, 16:36`.

## Usando este sistema

Os tokens viram variáveis CSS (`var(--primary)`, `var(--space-5)` …) com o tema em `data-theme="light"` ou `data-theme="dark"`. Os componentes são só CSS (`components/bundle.css`, prefixo `vn-`) — basta o markup mostrado em cada preview. Para Power BI, use a mesma paleta: `primary` como cor de dados principal, `bg` no fundo da página, `surface` nos visuais com cantos de 24px.
