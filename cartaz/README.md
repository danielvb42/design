**Cartaz** é uma linguagem de design de pôster para painéis: fundo quase preto, títulos brancos grandes com tracking muito negativo, botões em pílula branca e, de vez em quando, um card de cor vibrante que quebra o ritmo.

## Princípios

1. **Preto é o espaço em branco.** `bg` de ponta a ponta; os blocos se separam pela troca `bg` → `surface` → `surface-raised`, não por vazios claros. Sem modo claro.
2. **Título de pôster.** Tamanhos grandes com tracking de cerca de -5% (-3,1px em 62px, -1px em 32px) e entrelinha perto de 1,0. Se precisar caber, reduza o tamanho — nunca o aperto.
3. **Tudo que é ação é pílula.** Botão primário branco, secundário carvão; nada de botão com borda.
4. **Azul é sinal, não superfície.** `accent` só em links, foco e seleção.
5. **Um ou dois cards de cor por página.** Violeta, magenta, laranja ou coral em um card inteiro (`ColorCard`), nunca em uma seção; três já viram mural.
6. **Hierarquia binária de texto.** `ink` ou `ink-muted`; nenhum outro cinza.

## Cores

| Papel | Token | Escuro |
|---|---|---|
| Ação principal | `primary` | `#ffffff` |
| Texto sobre a ação | `on-primary` | `#000000` |
| Seleção suave | `primary-soft` | `#1c1c1c` |
| Link e foco | `accent` | `#0099ff` |
| Fundo | `bg` | `#090909` |
| Painéis | `surface` | `#141414` |
| Divisórias | `line` | `#262626` |
| Texto | `ink` | `#ffffff` |
| Texto de apoio | `ink-muted` | `#999999` |
| Positivo | `success` | `#22c55e` |
| Negativo | `danger` | `#ff5577` |

**Paleta de dados** (nesta ordem): `data-1` violeta, `data-2` magenta, `data-3` laranja, `data-4` coral, `data-5` azul, `data-6` cinza. São as mesmas cores dos cards de destaque; em gráficos, use no máximo quatro por visual.

**Contraste.** Todos os pares de texto documentados passam 4,5:1.

**Proporção:** ~88% preto e carvão, ~8% branco, ~4% cor vibrante. A origem não define cor de erro nem de atenção: `danger` reaproveita o coral e não existe cor de atenção.

## Tipografia

Títulos em **Geist** peso 500, com tracking muito negativo; corpo em **Inter** (400, 500, 700) com as variantes `cv01`, `cv05`, `cv09`, `cv11`, `ss03`, `ss07`. Entrelinha curta em tudo (1,3 no corpo). KPIs em `display-lg` (62px).

```html
<link href="https://fonts.googleapis.com/css2?family=Geist:wght@500&family=Inter:wght@400;500;700&display=swap" rel="stylesheet">
```

## Formas e espaçamento

Botões e abas `radius-pill`; campos `radius-md` (10px); miniaturas `radius-lg` (15px); cards `radius-xl` (20px); cards de cor `radius-xxl` (30px). Espaçamento em passos de 5 (15, 20, 30, 40px). Sombra só em elementos flutuantes (`shadow-float`); foco e seleção com `shadow-ring`.

## Dados e gráficos

Séries na ordem `data-1…6`. Trilhos em `surface-raised`, grade em `line`, eixos em `ink-muted` 13px. Números de eixo e de tabela com algarismos tabulares.

## Iconografia

Ícones-linha de 20–24px, traço 1,5px, cantos arredondados, na cor do texto (`ink-muted`; `ink` no item ativo). Sem emoji e sem ícones preenchidos coloridos. O sistema não traz logotipo: onde couber marca, escreva o nome em texto.

## Voz

Neutra e informativa. Títulos curtos ("Conclusos por unidade"), números seguidos de rótulo minúsculo ("312 conclusos"), datas e números no formato brasileiro (`1.248`, `87%`, `Março`).

## Usando este sistema

Tokens viram variáveis CSS (`var(--primary)`, `var(--space-4)`…). Tema único: `data-theme="dark"`. Componentes são só CSS (`components/bundle.css`, prefixo `cz-`), sem JavaScript. Comece pelo exemplo `Dashboard` e troque títulos, números e tabelas. O card vibrante é o componente `ColorCard` (`cz-color`), com a cor passada em `--c`.
