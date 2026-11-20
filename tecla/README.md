**Tecla** é uma linguagem de design escura e compacta para painéis, com cara de ferramenta: fundo quase preto, cards em degraus sutis, bordas finas, botão branco e atalhos de teclado à vista.

## Princípios

1. **Um único modo, escuro.** `bg` quase preto de ponta a ponta; não existe versão clara.
2. **O botão é branco.** `primary` é a única ação cheia da tela — no máximo um por dobra. Todo o resto é monocromático.
3. **Degraus de superfície, não sombra.** `bg` → `surface` → `surface-raised` → `surface-card`, cada um um passo mais claro, com borda `line` de 1px.
4. **A interface é o produto.** Mostre listas de comandos, linhas selecionáveis e teclas (`Keycap`) em vez de ilustração.
5. **Cor só dentro do dado.** Azul, amarelo, verde e vermelho aparecem em gráficos, etiquetas de situação e ícones de categoria — nunca em botões, texto corrido ou molduras.
6. **Tipografia aberta.** Inter com o conjunto estilístico `ss03` e espaçamento levemente positivo (0,1–0,4px); entrelinha 1,6 no corpo.
7. **Listras vermelhas, uma vez.** O degradê `stripe-start` → `stripe-end` em listras diagonais só abre a página inicial; nunca se repete abaixo.

## Cores

| Papel | Token | Escuro |
|---|---|---|
| Ação principal | `primary` | `#ffffff` |
| Texto sobre a ação | `on-primary` | `#000000` |
| Seleção suave | `primary-soft` | `#242728` |
| Link e foco | `accent` | `#f4f4f6` |
| Fundo | `bg` | `#07080a` |
| Painéis | `surface` | `#0d0d0d` |
| Divisórias | `line` | `#242728` |
| Texto | `ink` | `#f4f4f6` |
| Texto de apoio | `ink-muted` | `#9c9c9d` |
| Positivo | `success` | `#59d499` |
| Atenção | `warning` | `#ffc533` |
| Negativo | `danger` | `#ff6161` |

**Paleta de dados** (nesta ordem): `data-1` azul, `data-2` amarelo, `data-3` verde, `data-4` vermelho, `data-5` branco, `data-6` cinza. As quatro cores também significam informação, atenção, sucesso e erro: em status, acompanhe sempre de texto.

**Contraste.** Estes pares ficam abaixo do piso (4,5:1 para texto, 3:1 para marcas de gráfico) e foram mantidos com o valor de origem: `ink-subtle` sobre `bg` (3,8:1); `ink-subtle` sobre `surface` (3,6:1). Use-os só em texto grande, decoração ou áreas amplas com rótulo ao lado. Os demais pares de texto passam 4,5:1.

**Proporção:** ~92% preto e cinzas, ~6% branco, ~2% cor de dado.

## Tipografia

Uma família: **Inter** (400, 500, 600) com `font-feature-settings: "calt", "kern", "liga", "ss03"` — sem o `ss03` o texto vira Inter comum. Títulos em 500, corpo em 400 com entrelinha 1,6.

```html
<link href="https://fonts.googleapis.com/css2?family=Inter:wght@400;500;600&display=swap" rel="stylesheet">
```

## Formas e espaçamento

Teclas e etiquetas `radius-xs` (4px), linhas de comando `radius-sm` (6px), botões e campos `radius-md` (8px), cards `radius-lg` (10px), contêineres grandes `radius-xl` (16px), abas `radius-pill`. Compacto: botões e campos com 36px de altura, padding de card 16–24px.

## Dados e gráficos

Séries na ordem `data-1…6`. Trilhos em `line`, grade em `line-soft`, eixos em `ink-muted` 13px. Fundos suaves (`*-soft`, 15% de opacidade) para etiquetas.

## Iconografia

Ícones-linha de 20–24px, traço 1,5px, cantos arredondados, na cor do texto (`ink-muted`; `ink` no item ativo). Sem emoji e sem ícones preenchidos coloridos. O sistema não traz logotipo: onde couber marca, escreva o nome em texto.

## Voz

Neutra e informativa. Títulos curtos ("Conclusos por unidade"), números seguidos de rótulo minúsculo ("312 conclusos"), datas e números no formato brasileiro (`1.248`, `87%`, `Março`).

## Usando este sistema

Tokens viram variáveis CSS (`var(--primary)`, `var(--space-4)`…). Tema único: `data-theme="dark"`. Componentes são só CSS (`components/bundle.css`, prefixo `tc-`), sem JavaScript. Comece pelo exemplo `Dashboard` e troque títulos, números e tabelas. Teclas e linhas de comando são o componente `Keycap` (`tc-key`, `tc-cmd`).
