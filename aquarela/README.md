**Aquarela** é uma linguagem de design editorial para painéis, com cara de revista impressa: fundo off-white, tinta quase preta e quente, títulos em serifa leve e manchas de cor pastel como única atmosfera.

## Princípios

1. **A cor é atmosfera, não ação.** Menta, pêssego, lavanda, céu e rosa aparecem como manchas radiais suaves atrás do conteúdo (`Orb`) e em áreas de gráfico — nunca em botões nem em texto.
2. **O botão é tinta.** A ação principal é uma pílula quase preta (`primary`); a secundária, uma pílula de contorno. Não há cor de ação saturada.
3. **Serifa leve nos títulos.** Títulos e números em serifa de peso 300, nunca em negrito; o corpo em Inter 400/500.
4. **Corpo levemente aberto.** Inter com +0,15–0,18px de espaçamento; títulos com tracking negativo.
5. **Formas macias.** Pílula em todo botão e etiqueta, 16px nos cards, 24px nos cards de destaque.
6. **Linha fina e uma sombra quase invisível.** Cards com `line` de 1px; `shadow-soft` só no hover.

## Cores

| Papel | Token | Claro |
|---|---|---|
| Ação principal | `primary` | `#292524` |
| Texto sobre a ação | `on-primary` | `#ffffff` |
| Seleção suave | `primary-soft` | `#f0efed` |
| Link e foco | `accent` | `#0c0a09` |
| Fundo | `bg` | `#f5f5f5` |
| Painéis | `surface` | `#ffffff` |
| Divisórias | `line` | `#e7e5e4` |
| Texto | `ink` | `#0c0a09` |
| Texto de apoio | `ink-muted` | `#777169` |
| Positivo | `success` | `#16a34a` |
| Negativo | `danger` | `#dc2626` |

**Paleta de dados** (nesta ordem): `data-1` tinta, `data-2` menta, `data-3` pêssego, `data-4` lavanda, `data-5` céu, `data-6` rosa. Na origem os pastéis são só decoração; aqui também preenchem áreas de gráfico, sempre com rótulo e valor em texto, porque ficam abaixo de 3:1 sobre branco. Para linhas e marcas finas use `data-1` (tinta).

**Contraste.** Estes pares ficam abaixo do piso (4,5:1 para texto, 3:1 para marcas de gráfico) e foram mantidos com o valor de origem: `ink-muted` sobre `bg` (4,4:1); `success` sobre `surface` (3,3:1); `data-2` sobre `surface` (1,4:1); `data-3` sobre `surface` (1,6:1); `data-4` sobre `surface` (1,8:1); `data-5` sobre `surface` (1,7:1); `data-6` sobre `surface` (1,7:1). Use-os só em texto grande, decoração ou áreas amplas com rótulo ao lado. Os demais pares de texto passam 4,5:1.

**Proporção:** ~90% off-white, branco e tinta, ~10% pastéis. O verde `success` não chega a 4,5:1 sobre branco: situação positiva vai em etiqueta com texto em `ink`. Para um bloco invertido (card em destaque), use `inverse-bg` com `inverse-ink`.

## Tipografia

Duas famílias: **Newsreader** (serifa, peso 300) para títulos e números; **Inter** (400, 500, 600) para corpo, navegação, botões e rótulos. Rótulos de seção em `caption-uppercase` (12px, 600, espaçamento 0,96px).

```html
<link href="https://fonts.googleapis.com/css2?family=Newsreader:opsz,wght@6..72,300&family=Inter:wght@400;500;600&display=swap" rel="stylesheet">
```

## Formas e espaçamento

Botões, abas e etiquetas `radius-pill`; campos `radius-md` (8px); cards `radius-xl` (16px); cards com mancha `radius-xxl` (24px). Base de 4px; padding de card 24–32px; respiro largo entre blocos.

## Dados e gráficos

Série principal em `data-1` (tinta); os pastéis entram como áreas de comparação na ordem `data-2…6`. Trilhos em `primary-soft`, grade em `line`, eixos em `ink-muted` 14px.

## Iconografia

Ícones-linha de 20–24px, traço 1,5px, cantos arredondados, na cor do texto (`ink-muted`; `ink` no item ativo). Sem emoji e sem ícones preenchidos coloridos. O sistema não traz logotipo: onde couber marca, escreva o nome em texto.

## Voz

Neutra e informativa. Títulos curtos ("Conclusos por unidade"), números seguidos de rótulo minúsculo ("312 conclusos"), datas e números no formato brasileiro (`1.248`, `87%`, `Março`).

## Usando este sistema

Tokens viram variáveis CSS (`var(--primary)`, `var(--space-4)`…). Tema único: `data-theme="light"`. Componentes são só CSS (`components/bundle.css`, prefixo `aq-`), sem JavaScript. Comece pelo exemplo `Dashboard` e troque títulos, números e tabelas. O card com mancha é o componente `Orb` (`aq-orb`), com a cor passada em `--orb`.
