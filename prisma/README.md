**Prisma** é uma linguagem de design para painéis e mockups sobre fundo preto: superfícies em carvão, tipografia branca e uma cor de identidade por área do painel.

## Princípios

1. **Preto e carvão são o palco.** A página é `bg` (preto); tudo que é card sobe um degrau para `surface` e, em destaque, `surface-raised`. Não existe modo claro.
2. **Uma cor por área.** Cada área ou assunto do painel recebe UMA cor de identidade (`data-1`…`data-6`) e a usa na etiqueta da seção, no card de destaque e na série do gráfico. Não misture duas identidades no mesmo bloco.
3. **O botão é branco.** A ação primária é um retângulo branco de 8px (`primary`); cores de identidade não vão em botões gerais.
4. **Título apertado, texto arejado.** Títulos com entrelinha 1,17–1,21 e pesos 600/700; corpo em 500 com entrelinha 1,5–1,7.
5. **Elevação por degrau de cinza, não por sombra.** `bg` → `surface` → `surface-raised`, com borda `line-glass` de 1px.
6. **Rótulo em maiúsculas acima de cada bloco.** Todo bloco abre com `eyebrow` (12px, 600, espaçamento 0,6px).

## Cores

| Papel | Token | Escuro |
|---|---|---|
| Ação principal | `primary` | `#ffffff` |
| Texto sobre a ação | `on-primary` | `#000000` |
| Seleção suave | `primary-soft` | `#1f232b` |
| Link e foco | `accent` | `#2b89ff` |
| Fundo | `bg` | `#000000` |
| Painéis | `surface` | `#15181e` |
| Divisórias | `line` | `#252830` |
| Texto | `ink` | `#ffffff` |
| Texto de apoio | `ink-muted` | `#b2b6bd` |
| Positivo | `success` | `#00ca8e` |
| Atenção | `warning` | `#ffcf25` |
| Negativo | `danger` | `#e62b1e` |

**Paleta de dados** (nesta ordem): `data-1` violeta, `data-2` amarelo, `data-3` ciano, `data-4` azul, `data-5` verde, `data-6` coral. São as cores de identidade; `success`, `warning` e `danger` reutilizam verde, amarelo e vermelho, então em status use sempre etiqueta com texto.

**Contraste.** Estes pares ficam abaixo do piso (4,5:1 para texto, 3:1 para marcas de gráfico) e foram mantidos com o valor de origem: `ink-subtle` sobre `bg` (3,9:1); `ink-subtle` sobre `surface` (3,3:1); `danger` sobre `surface` (4,0:1); `data-1` sobre `surface` (2,8:1). Use-os só em texto grande, decoração ou áreas amplas com rótulo ao lado. Os demais pares de texto passam 4,5:1.

**Proporção:** ~85% preto e carvão, ~10% branco (texto e ação), ~5% cor de identidade.

## Tipografia

Uma família: **Inter** (500, 600, 700). Hierarquia por peso (500 corpo, 600 ênfase, 700 títulos grandes) e pelo contraste de entrelinha. Sem fonte monoespaçada. KPIs em `display-md` (40px/600) com algarismos tabulares.

```html
<link href="https://fonts.googleapis.com/css2?family=Inter:wght@500;600;700&display=swap" rel="stylesheet">
```

## Formas e espaçamento

Botões e campos com `radius-md` (8px) — nunca pílula; cards com `radius-lg` (12px); só etiquetas usam `radius-pill`. Base de 8px: padding de card 24px, gap entre cards 24–32px, 96px entre grandes seções. Sem sombras.

## Dados e gráficos

Barras e séries usam a cor de identidade da área (`data-N`); composições seguem a ordem `data-1…6`. Trilhos em `surface-raised`, grade em `line`, eixos em `ink-muted` 13px. Violeta e azul ficam perto de 3:1 sobre `surface`: sempre com o valor em texto ao lado.

## Iconografia

Ícones-linha de 20–24px, traço 1,5px, cantos arredondados, na cor do texto (`ink-muted`; `ink` no item ativo). Sem emoji e sem ícones preenchidos coloridos. O sistema não traz logotipo: onde couber marca, escreva o nome em texto.

## Voz

Neutra e informativa. Títulos curtos ("Conclusos por unidade"), números seguidos de rótulo minúsculo ("312 conclusos"), datas e números no formato brasileiro (`1.248`, `87%`, `Março`).

## Usando este sistema

Tokens viram variáveis CSS (`var(--primary)`, `var(--space-4)`…). Tema único: `data-theme="dark"`. Componentes são só CSS (`components/bundle.css`, prefixo `pr-`), sem JavaScript. Comece pelo exemplo `Dashboard` e troque títulos, números e tabelas. O card de identidade é o componente `AreaCard` (`pr-area`), com a cor passada em `--area`.
