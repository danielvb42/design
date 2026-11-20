**Papel** é uma linguagem de design editorial e calma para painéis: fundo creme, tinta quase preta e quente, títulos em peso regular e um único laranja reservado à ação principal.

## Princípios

1. **Creme, não branco.** A página é `bg` (creme); os cards são `surface` (branco), destacados só por esse leve contraste e por uma linha fina.
2. **Tinta quente.** Texto e títulos em `ink`, um quase-preto quente; nunca preto puro.
3. **Um laranja, raramente.** `primary` só no botão principal e na marca. Não existe segunda cor de ação; para uma ação forte neutra use o botão em tinta (`pp-btn-ink`).
4. **Títulos em peso 400.** Voz de revista: tamanho e tracking negativo fazem a hierarquia, nunca o negrito.
5. **Linhas finas, zero sombra.** A profundidade vem de `line` de 1px e do branco sobre creme.
6. **Pastéis só para etapas e dados.** Pêssego, menta, azul, lavanda e ouro marcam etapas de um fluxo (`Stages`) e séries de gráfico — nunca botões.
7. **Monoespaçada em todo dado técnico.** Números de processo, identificadores e consultas em `code`.

## Cores

| Papel | Token | Claro |
|---|---|---|
| Ação principal | `primary` | `#f54e00` |
| Texto sobre a ação | `on-primary` | `#ffffff` |
| Seleção suave | `primary-soft` | `#e6e5e0` |
| Link e foco | `accent` | `#26251e` |
| Fundo | `bg` | `#f7f7f4` |
| Painéis | `surface` | `#ffffff` |
| Divisórias | `line` | `#e6e5e0` |
| Texto | `ink` | `#26251e` |
| Texto de apoio | `ink-muted` | `#5a5852` |
| Positivo | `success` | `#1f8a65` |
| Negativo | `danger` | `#cf2d56` |

**Paleta de dados** (nesta ordem): `data-1` pêssego, `data-2` menta, `data-3` azul, `data-4` lavanda, `data-5` ouro, `data-6` tinta. Os quatro pastéis ficam abaixo de 3:1 sobre branco: só em áreas grandes, com rótulo de texto.

**Contraste.** Estes pares ficam abaixo do piso (4,5:1 para texto, 3:1 para marcas de gráfico) e foram mantidos com o valor de origem: `on-primary` sobre `primary` (3,5:1); `ink-subtle` sobre `bg` (3,8:1); `ink-subtle` sobre `surface` (4,1:1); `success` sobre `surface` (4,3:1); `data-1` sobre `surface` (2,1:1); `data-2` sobre `surface` (1,9:1); `data-3` sobre `surface` (2,0:1); `data-4` sobre `surface` (2,1:1). Use-os só em texto grande, decoração ou áreas amplas com rótulo ao lado. Os demais pares de texto passam 4,5:1.

**Proporção:** ~92% creme, branco e tinta, ~5% pastéis de dados, ~3% laranja. O texto branco sobre o laranja fica em 3,5:1 — par de origem mantido; por isso o rótulo do botão é sempre curto.

## Tipografia

**Inter** em 400 (títulos e corpo), 500 (botões e navegação) e 600 (títulos de componente), com tracking negativo só nos títulos. **JetBrains Mono** para código. Rótulos de seção em `caption-uppercase` (11px, 600).

```html
<link href="https://fonts.googleapis.com/css2?family=Inter:wght@400;500;600&family=JetBrains+Mono:wght@400&display=swap" rel="stylesheet">
```

## Formas e espaçamento

Botões e campos `radius-md` (8px), cards `radius-lg` (12px), pílula em etiquetas e etapas. Base de 4px; padding de card 24px; ritmo generoso entre blocos (80px entre seções de página). Sem sombras.

## Dados e gráficos

Séries em pastel na ordem `data-1…5`, com `data-6` (tinta) para a série de referência. Trilhos em `primary-soft`, grade em `line`, eixos em `ink-subtle` 13px. Cada cor acompanha rótulo e valor em texto.

## Iconografia

Ícones-linha de 20–24px, traço 1,5px, cantos arredondados, na cor do texto (`ink-muted`; `ink` no item ativo). Sem emoji e sem ícones preenchidos coloridos. O sistema não traz logotipo: onde couber marca, escreva o nome em texto.

## Voz

Neutra e informativa. Títulos curtos ("Conclusos por unidade"), números seguidos de rótulo minúsculo ("312 conclusos"), datas e números no formato brasileiro (`1.248`, `87%`, `Março`).

## Usando este sistema

Tokens viram variáveis CSS (`var(--primary)`, `var(--space-4)`…). Tema único: `data-theme="light"`. Componentes são só CSS (`components/bundle.css`, prefixo `pp-`), sem JavaScript. Comece pelo exemplo `Dashboard` e troque títulos, números e tabelas. As etapas em pastel são o componente `Stages` (`pp-stg`); use `pp-mono` para valores técnicos.
