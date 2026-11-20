**Crepúsculo** é uma linguagem de design editorial para painéis, em três telas de cor: índigo profundo na navegação e nos destaques, branco no corpo e uma faixa verde-petróleo que fecha a página.

## Princípios

1. **Três telas, nenhuma a mais.** Índigo (`primary`, `nav-bg`) para navegação e destaque, branco (`bg`) para o conteúdo, verde-petróleo (`teal-deep`) para a faixa de fechamento. Uma quarta cor de fundo quebra o sistema.
2. **Uma ação por bloco.** Cada bloco tem no máximo um botão principal; nunca dois primários lado a lado.
3. **Pesos intermediários.** Títulos em 460 e 540, não 400/500/700: o meio-termo dá calor à tipografia. O 700 fica só no rótulo de botão.
4. **Entrelinha comprimida nos títulos.** 0,96 em 48–64px, com tracking negativo; corpo em 1,5.
5. **Texto nunca é preto puro.** `ink` é um cinza-escuro quente; divisórias em `line`, também quente.
6. **Toda página fecha na faixa.** O último bloco é a `Band` verde-petróleo, com um título e um botão branco.
7. **Pílula só sobre o índigo.** Sobre fundo escuro o botão é pílula `violet`; no corpo branco, retângulo de 8px.

## Cores

| Papel | Token | Claro |
|---|---|---|
| Ação principal | `primary` | `#1b1938` |
| Texto sobre a ação | `on-primary` | `#ffffff` |
| Seleção suave | `primary-soft` | `#e8e4dd` |
| Link e foco | `accent` | `#1b1938` |
| Fundo | `bg` | `#ffffff` |
| Painéis | `surface` | `#ffffff` |
| Divisórias | `line` | `#e8e4dd` |
| Texto | `ink` | `#292827` |
| Texto de apoio | `ink-muted` | `#73706d` |
| Positivo | `success` | `#155555` |
| Negativo | `danger` | `#b3261e` |

**Paleta de dados** (nesta ordem): `data-1` índigo, `data-2` violeta, `data-3` verde-petróleo, `data-4` cinza, `data-5` ardósia, `data-6` areia. O violeta e a areia têm pouco contraste sobre branco: só em áreas grandes, com rótulo.

**Contraste.** Estes pares ficam abaixo do piso (4,5:1 para texto, 3:1 para marcas de gráfico) e foram mantidos com o valor de origem: `ink-subtle` sobre `bg` (2,9:1); `data-2` sobre `surface` (1,8:1); `data-4` sobre `surface` (2,9:1); `data-6` sobre `surface` (1,3:1). Use-os só em texto grande, decoração ou áreas amplas com rótulo ao lado. Os demais pares de texto passam 4,5:1.

**Proporção:** ~75% branco, ~15% índigo, ~5% verde-petróleo, ~5% violeta e cinzas. A origem não define verde nem vermelho de status: o positivo usa o verde-petróleo (`success`) e o `danger` foi derivado — confirme antes de adotar.

## Tipografia

Uma família variável: **Inter** nos pesos 460, 540 e 600 (700 em botões). Carregue o eixo de peso inteiro; os pesos fixos 400/500 descaracterizam o sistema. KPIs em `display-xl` (48px/460, entrelinha 0,96).

```html
<link href="https://fonts.googleapis.com/css2?family=Inter:wght@100..900&display=swap" rel="stylesheet">
```

## Formas e espaçamento

Botões `radius-md` (8px), campos `radius-sm` (6px), cards `radius-lg` (12px), abas e a pílula sobre índigo `radius-pill`. Base de 8px; cards com 32px de padding. Sombra mínima: `shadow-card` em cards, `shadow-float` em menus.

## Dados e gráficos

Séries na ordem `data-1…6`: índigo primeiro, violeta para comparação, verde-petróleo para o positivo. Trilhos em `primary-soft`, grade em `line`, eixos em `ink-muted` 14px.

## Iconografia

Ícones-linha de 20–24px, traço 1,5px, cantos arredondados, na cor do texto (`ink-muted`; `ink` no item ativo). Sem emoji e sem ícones preenchidos coloridos. O sistema não traz logotipo: onde couber marca, escreva o nome em texto.

## Voz

Neutra e informativa. Títulos curtos ("Conclusos por unidade"), números seguidos de rótulo minúsculo ("312 conclusos"), datas e números no formato brasileiro (`1.248`, `87%`, `Março`).

## Usando este sistema

Tokens viram variáveis CSS (`var(--primary)`, `var(--space-4)`…). Tema único: `data-theme="light"`. Componentes são só CSS (`components/bundle.css`, prefixo `cr-`), sem JavaScript. Comece pelo exemplo `Dashboard` e troque títulos, números e tabelas. A faixa de fechamento é o componente `Band` (`cr-band`); a navegação usa os tokens `nav-*`.
