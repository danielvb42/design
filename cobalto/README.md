**Cobalto** é uma linguagem de design técnica para painéis: fundo quase preto, cards em degraus de cinza e um único azul elétrico profundo, que aparece em botões e num brilho de holofote.

## Princípios

1. **Um azul, usado com parcimônia.** `primary` só no botão primário, na marca e no brilho; ciano e violeta existem apenas em gráficos.
2. **Holofote atrás do que importa.** O destaque da página leva um brilho radial `primary-glow` por trás (componente `Spotlight`); um por tela.
3. **Elevação por luminosidade.** `bg` → `surface` → `surface-raised` → `surface-strong`; `bg-deep` (preto puro) só para blocos de código. Sem sombras.
4. **Títulos em peso 500.** Confiante sem gritar: nunca 400 e nunca 700 em títulos. Corpo em cinza suave (`ink-muted`), títulos em branco.
5. **Raios compactos.** Botões e campos com 8px, cards com 12–16px; pílula só em etiquetas.
6. **Código em monoespaçada.** Todo valor técnico em `code` (JetBrains Mono).

## Cores

| Papel | Token | Escuro |
|---|---|---|
| Ação principal | `primary` | `#0007cd` |
| Texto sobre a ação | `on-primary` | `#ffffff` |
| Seleção suave | `primary-soft` | `#222222` |
| Link e foco | `accent` | `#ffffff` |
| Fundo | `bg` | `#0f0f0f` |
| Painéis | `surface` | `#181818` |
| Divisórias | `line` | `#222222` |
| Texto | `ink` | `#ffffff` |
| Texto de apoio | `ink-muted` | `#a8a8a8` |
| Positivo | `success` | `#33d17a` |
| Negativo | `danger` | `#ff4d4d` |

**Paleta de dados** (nesta ordem): `data-1` azul-brilho, `data-2` ciano, `data-3` violeta, `data-4` branco, `data-5` cinza, `data-6` cinza-escuro. O azul-brilho fica abaixo de 3:1 sobre `surface`: use-o em áreas grandes com o valor ao lado; para linhas finas prefira ciano ou branco.

**Contraste.** Estes pares ficam abaixo do piso (4,5:1 para texto, 3:1 para marcas de gráfico) e foram mantidos com o valor de origem: `primary` sobre `bg` (1,7:1); `data-1` sobre `surface` (2,3:1). Use-os só em texto grande, decoração ou áreas amplas com rótulo ao lado. Os demais pares de texto passam 4,5:1.

**Proporção:** ~90% preto e cinzas, ~7% branco, ~3% azul. O azul é escuro demais para texto ou para marcar seleção; por isso links, foco e aba ativa usam branco. A origem não define cor de atenção: o sistema só tem `success` e `danger`.

## Tipografia

Uma família para tudo: **Inter** em 500 (títulos), 600 (títulos de componente) e 400 (corpo), com tracking negativo proporcional nos títulos. **JetBrains Mono** em código. Rótulos de seção em `caption-uppercase` (11px, 600).

```html
<link href="https://fonts.googleapis.com/css2?family=Inter:wght@400;500;600&family=JetBrains+Mono:wght@400&display=swap" rel="stylesheet">
```

## Formas e espaçamento

Botões e campos `radius-md` (8px), cards `radius-lg`/`radius-xl` (12–16px), etiquetas `radius-pill`. Base de 4px; padding de card 20–28px; 96px só entre grandes seções.

## Dados e gráficos

Séries na ordem `data-1…6`; trilhos em `surface-raised`, grade em `line`, eixos em `ink-subtle` 13px. Ciano e violeta são exclusivos de gráfico — nunca em botões ou texto.

## Iconografia

Ícones-linha de 20–24px, traço 1,5px, cantos arredondados, na cor do texto (`ink-muted`; `ink` no item ativo). Sem emoji e sem ícones preenchidos coloridos. O sistema não traz logotipo: onde couber marca, escreva o nome em texto.

## Voz

Neutra e informativa. Títulos curtos ("Conclusos por unidade"), números seguidos de rótulo minúsculo ("312 conclusos"), datas e números no formato brasileiro (`1.248`, `87%`, `Março`).

## Usando este sistema

Tokens viram variáveis CSS (`var(--primary)`, `var(--space-4)`…). Tema único: `data-theme="dark"`. Componentes são só CSS (`components/bundle.css`, prefixo `cb-`), sem JavaScript. Comece pelo exemplo `Dashboard` e troque títulos, números e tabelas. O destaque com brilho é o componente `Spotlight` (`cb-spot`); use `cb-mono` para valores técnicos.
