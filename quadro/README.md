**Quadro** é uma linguagem de design clara e bem-humorada para painéis: tela branca, botões em pílula preta, tipografia geométrica e cards em tons de bloco de notas — amarelo, coral, verde-água e rosa.

## Princípios

1. **Branco com notas coloridas.** A base é `bg` branco; a cor entra em cards inteiros de tom pastel (`Note`), como papéis colados num quadro, lado a lado com cards brancos.
2. **O botão é preto.** Ação principal em pílula `primary`; secundária em pílula de contorno. O amarelo nunca é botão comum.
3. **Amarelo é assinatura, não superfície de trabalho.** `yellow` em uma nota de destaque, em selos e avisos — nunca em grandes fundos de página.
4. **Azul para o que é clicável em linha.** `accent` em links, foco e na borda do card em destaque.
5. **Pílula em tudo que se aperta.** Botões, abas, filtros e etiquetas com `radius-pill`; cards com 16px e notas com 28px.
6. **Um peso de título.** Títulos sempre em 500; corpo 400; etiquetas 600. Nada de 700.
7. **Quase plano.** Borda `line-soft` em cards; sombra só para elevar uma moldura de destaque ou um menu.

## Cores

| Papel | Token | Claro |
|---|---|---|
| Ação principal | `primary` | `#1c1c1e` |
| Texto sobre a ação | `on-primary` | `#ffffff` |
| Seleção suave | `primary-soft` | `#eef0f3` |
| Link e foco | `accent` | `#4262ff` |
| Fundo | `bg` | `#ffffff` |
| Painéis | `surface` | `#ffffff` |
| Divisórias | `line` | `#e0e2e8` |
| Texto | `ink` | `#1c1c1e` |
| Texto de apoio | `ink-muted` | `#555a6a` |
| Positivo | `success` | `#00b473` |
| Atenção | `warning` | `#ffd02f` |
| Negativo | `danger` | `#600000` |

**Paleta de dados** (nesta ordem): `data-1` azul, `data-2` amarelo, `data-3` verde-água, `data-4` coral, `data-5` preto, `data-6` musgo. O amarelo e o coral ficam abaixo de 3:1 sobre branco: áreas grandes com rótulo; para linhas finas use azul, preto ou musgo.

**Contraste.** Estes pares ficam abaixo do piso (4,5:1 para texto, 3:1 para marcas de gráfico) e foram mantidos com o valor de origem: `ink-subtle` sobre `bg` (3,1:1); `success` sobre `surface` (2,7:1); `warning` sobre `surface` (1,5:1); `data-2` sobre `surface` (1,5:1); `data-3` sobre `surface` (2,4:1); `data-4` sobre `surface` (2,0:1). Use-os só em texto grande, decoração ou áreas amplas com rótulo ao lado. Os demais pares de texto passam 4,5:1.

**Proporção:** ~80% branco e cinzas, ~10% preto, ~10% pastéis. Etiquetas usam pares prontos: fundo `warning-soft` com texto `warning-ink`, `success-soft` com `success-ink`, `danger-soft` com `danger`. O verde `success` sozinho não sustenta texto: use-o só como ponto ou ícone.

## Tipografia

Uma família: **Noto Sans** (400, 500, 600). Títulos em 500 com tracking negativo nos tamanhos grandes; números de destaque em `stat-display` (64px/500).

```html
<link href="https://fonts.googleapis.com/css2?family=Noto+Sans:wght@400;500;600&display=swap" rel="stylesheet">
```

## Formas e espaçamento

Botões, abas e etiquetas `radius-pill`; campos `radius-md` (8px); cards `radius-xl` (16px); notas `radius-xxxl` (28px); faixa de chamada `radius-feature` (32px). Base de 4px; padding de card 24–32px; 64–96px entre seções.

## Dados e gráficos

Séries na ordem `data-1…6`: azul primeiro, amarelo e verde-água para comparação. Trilhos em `primary-soft`, grade em `line-soft`, eixos em `ink-steel` 13px.

## Iconografia

Ícones-linha de 20–24px, traço 1,5px, cantos arredondados, na cor do texto (`ink-muted`; `ink` no item ativo). Sem emoji e sem ícones preenchidos coloridos. O sistema não traz logotipo: onde couber marca, escreva o nome em texto.

## Voz

Neutra e informativa. Títulos curtos ("Conclusos por unidade"), números seguidos de rótulo minúsculo ("312 conclusos"), datas e números no formato brasileiro (`1.248`, `87%`, `Março`).

## Usando este sistema

Tokens viram variáveis CSS (`var(--primary)`, `var(--space-4)`…). Tema único: `data-theme="light"`. Componentes são só CSS (`components/bundle.css`, prefixo `qd-`), sem JavaScript. Comece pelo exemplo `Dashboard` e troque títulos, números e tabelas. A nota pastel é o componente `Note` (`qd-note`), com a cor passada em `--note`.
