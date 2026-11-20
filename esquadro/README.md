**Esquadro** é uma linguagem de design sóbria e plana para painéis: superfícies brancas, texto carvão, cantos retos e um único azul firme para ação.

## Princípios

1. **Tudo em ângulo reto.** Botões, cards, campos e contêineres têm raio 0. Nem 4px: o canto reto é a identidade.
2. **Um só azul.** `primary` marca links, ação primária, foco e a faixa de chamada. Não vira fundo de card nem cor de rótulo.
3. **Títulos leves.** Tamanhos grandes (42px+) em peso 300; corpo em 400; ênfase em 600. Não coloque título em negrito.
4. **Linhas e degraus de cinza, sem sombra.** Hierarquia por borda `line` de 1px e pela troca `surface` → `layer`.
5. **Densidade é virtude.** Grade de 4px, seções separadas por faixas `layer`, não por grandes vazios.
6. **Rótulos em caixa normal.** Nada de maiúsculas espaçadas: rótulos de seção em 14px, frase normal.

## Cores

| Papel | Token | Claro |
|---|---|---|
| Ação principal | `primary` | `#0f62fe` |
| Texto sobre a ação | `on-primary` | `#ffffff` |
| Seleção suave | `primary-soft` | `#e0e0e0` |
| Link e foco | `accent` | `#0f62fe` |
| Fundo | `bg` | `#ffffff` |
| Painéis | `surface` | `#ffffff` |
| Divisórias | `line` | `#e0e0e0` |
| Texto | `ink` | `#161616` |
| Texto de apoio | `ink-muted` | `#525252` |
| Positivo | `success` | `#24a148` |
| Atenção | `warning` | `#f1c21b` |
| Negativo | `danger` | `#da1e28` |

**Paleta de dados** (nesta ordem): `data-1` azul, `data-2` azul-escuro, `data-3` carvão, `data-4` cinza-escuro, `data-5` cinza, `data-6` cinza-claro. Como só existe um matiz, as séries se distinguem por luminosidade; o cinza-claro é só para áreas grandes.

**Contraste.** Estes pares ficam abaixo do piso (4,5:1 para texto, 3:1 para marcas de gráfico) e foram mantidos com o valor de origem: `ink-subtle` sobre `bg` (3,4:1); `ink-subtle` sobre `layer` (3,1:1); `success` sobre `surface` (3,4:1); `warning` sobre `surface` (1,7:1); `data-6` sobre `surface` (1,7:1). Use-os só em texto grande, decoração ou áreas amplas com rótulo ao lado. Os demais pares de texto passam 4,5:1.

**Proporção:** ~90% branco e cinzas, ~7% carvão, ~3% azul. O verde `success` não chega a 4,5:1 sobre branco: situação positiva vai em etiqueta, com texto em `ink`.

## Tipografia

Uma família: **IBM Plex Sans** (300, 400, 600), de licença aberta. Corpo com `letter-spacing: 0.16px` — detalhe de precisão que faz parte da voz. KPIs em `display-md` (42px/300).

```html
<link href="https://fonts.googleapis.com/css2?family=IBM+Plex+Sans:wght@300;400;600&display=swap" rel="stylesheet">
```

## Formas e espaçamento

Raio padrão `radius-none` (0); `radius-xs`/`radius-sm` só em dicas e menus; `radius-pill` só em etiquetas de situação. Botões com 12×16px de padding; campos sobre `layer` com linha inferior, que vira 2px em `primary` no foco. Padding de card 24–32px.

## Dados e gráficos

Série principal em `data-1` (azul); comparações em azul-escuro e escala de cinza. Trilhos em `layer-strong`, grade em `line`, eixos em `ink-muted` 12px. Barras de cantos retos.

## Iconografia

Ícones-linha de 20–24px, traço 1,5px, cantos arredondados, na cor do texto (`ink-muted`; `ink` no item ativo). Sem emoji e sem ícones preenchidos coloridos. O sistema não traz logotipo: onde couber marca, escreva o nome em texto.

## Voz

Neutra e informativa. Títulos curtos ("Conclusos por unidade"), números seguidos de rótulo minúsculo ("312 conclusos"), datas e números no formato brasileiro (`1.248`, `87%`, `Março`).

## Usando este sistema

Tokens viram variáveis CSS (`var(--primary)`, `var(--space-4)`…). Tema único: `data-theme="light"`. Componentes são só CSS (`components/bundle.css`, prefixo `eq-`), sem JavaScript. Comece pelo exemplo `Dashboard` e troque títulos, números e tabelas. A faixa de chamada é o componente `Band` (`eq-band`).
