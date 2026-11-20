**Voltagem** é uma linguagem de design de alto contraste para painéis: fundo quase preto, tipografia branca em peso forte e um único amarelo elétrico que marca ação e números.

## Princípios

1. **Preto e amarelo, mais nada.** `bg` quase preto, texto branco e UM acento: `primary` (amarelo elétrico). Não introduza segunda cor de marca.
2. **Amarelo raro no elemento, generoso na faixa.** Em elementos, só botão primário, link e número de destaque; em área grande, só a faixa `Band` — uma por página.
3. **Os números são amarelos.** Todo KPI usa `stat-display` em `primary`: o número é o momento de credibilidade.
4. **Peso 700 com tracking negativo.** Títulos sempre em 700 e espaçamento de -1 a -2,5px; hierarquia por tamanho, não por gradação de peso.
5. **Cards quase da cor do fundo.** `surface` fica só um degrau acima de `bg`; a separação vem da borda `line` de 1px. Sem sombras.
6. **Mostre o dado técnico como ele é.** Identificadores, consultas e números de processo em `code` (JetBrains Mono).

## Cores

| Papel | Token | Escuro |
|---|---|---|
| Ação principal | `primary` | `#faff69` |
| Texto sobre a ação | `on-primary` | `#0a0a0a` |
| Seleção suave | `primary-soft` | `#242424` |
| Link e foco | `accent` | `#faff69` |
| Fundo | `bg` | `#0a0a0a` |
| Painéis | `surface` | `#1a1a1a` |
| Divisórias | `line` | `#2a2a2a` |
| Texto | `ink` | `#ffffff` |
| Texto de apoio | `ink-muted` | `#888888` |
| Positivo | `success` | `#22c55e` |
| Atenção | `warning` | `#f59e0b` |
| Negativo | `danger` | `#ef4444` |

**Paleta de dados** (nesta ordem): `data-1` amarelo, `data-2` azul, `data-3` branco, `data-4` cinza, `data-5` cinza-claro, `data-6` cinza-escuro. Fora o amarelo e o azul informativo, as séries se diferenciam por luminosidade, não por matiz.

**Contraste.** Estes pares ficam abaixo do piso (4,5:1 para texto, 3:1 para marcas de gráfico) e foram mantidos com o valor de origem: `ink-subtle` sobre `bg` (2,9:1); `ink-subtle` sobre `surface` (2,5:1); `data-6` sobre `surface` (2,5:1). Use-os só em texto grande, decoração ou áreas amplas com rótulo ao lado. Os demais pares de texto passam 4,5:1.

**Proporção:** ~90% preto e cinzas, ~7% branco, ~3% amarelo — mais uma faixa amarela por página, no máximo.

## Tipografia

**Inter** (700 títulos, 600 subtítulos e botões, 400 corpo) e **JetBrains Mono** para código. Rótulos de seção em `caption-uppercase` (12px, 600, espaçamento 1,5px).

```html
<link href="https://fonts.googleapis.com/css2?family=Inter:wght@400;500;600;700&family=JetBrains+Mono:wght@400&display=swap" rel="stylesheet">
```

## Formas e espaçamento

Botões, abas e campos com `radius-md` (8px); cards com `radius-lg` (12px); pílula só em etiquetas. Base de 4px; padding de card 24–32px. Sem sombras: a profundidade vem do degrau `bg` → `surface` → `surface-raised`.

## Dados e gráficos

A série principal é amarela (`data-1`); comparações entram em azul, branco e cinzas. Trilhos em `surface-raised`, grade em `line`, eixos em `ink-muted`. O cinza-escuro `data-6` é só para áreas grandes.

## Iconografia

Ícones-linha de 20–24px, traço 1,5px, cantos arredondados, na cor do texto (`ink-muted`; `ink` no item ativo). Sem emoji e sem ícones preenchidos coloridos. O sistema não traz logotipo: onde couber marca, escreva o nome em texto.

## Voz

Neutra e informativa. Títulos curtos ("Conclusos por unidade"), números seguidos de rótulo minúsculo ("312 conclusos"), datas e números no formato brasileiro (`1.248`, `87%`, `Março`).

## Usando este sistema

Tokens viram variáveis CSS (`var(--primary)`, `var(--space-4)`…). Tema único: `data-theme="dark"`. Componentes são só CSS (`components/bundle.css`, prefixo `vt-`), sem JavaScript. Comece pelo exemplo `Dashboard` e troque títulos, números e tabelas. A faixa amarela é o componente `Band` (`vt-band`); use `vt-mono` para valores técnicos.
