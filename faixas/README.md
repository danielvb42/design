**Faixas** é uma linguagem de design em capítulos para painéis: faixas inteiras em preto, branco ou azul, títulos em peso leve, botões em pílula azul e o conteúdo ocupando quase todo o espaço.

## Princípios

1. **A página é feita de faixas.** Cada bloco ocupa a largura toda em uma de três telas: clara, escura (os dois temas) ou azul (`primary`). A troca de fundo é o divisor; não há linhas decorativas entre faixas.
2. **Azul é ação.** `primary` em todo botão principal, no chip de filtro ativo e na faixa `Band`; no máximo uma faixa azul por página.
3. **Laranja só para a ação quente.** `action-warm` fica reservado a UMA categoria de ação que precise se distinguir do azul; nunca em destaque geral.
4. **Títulos leves, botões pesados.** Títulos em peso 300; rótulos de botão em 700. O contraste entre os dois é a voz.
5. **Duas formas: pílula e 8px.** Todo botão e chip é pílula; todo card tem 8px; campos têm 4px; faixas não têm raio.
6. **Plano.** Cards sem sombra em repouso; `shadow-press` só no estado pressionado. Nenhum degradê, salvo o dourado (`gold-*`) em um único selo de destaque.
7. **Dois temas, o mesmo desenho.** Claro e Escuro trocam só superfícies e tintas; pílulas, raios e a faixa azul não mudam.

## Cores

| Papel | Token | Claro | Escuro |
|---|---|---|---|
| Ação principal | `primary` | `#0070d1` | `#0070d1` |
| Texto sobre a ação | `on-primary` | `#ffffff` | `#ffffff` |
| Seleção suave | `primary-soft` | `#f3f3f3` | `#181818` |
| Link e foco | `accent` | `#0064b7` | `#53b1ff` |
| Fundo | `bg` | `#ffffff` | `#000000` |
| Painéis | `surface` | `#f5f7fa` | `#181818` |
| Divisórias | `line` | `#f3f3f3` | `rgba(229,229,229,0.2)` |
| Texto | `ink` | `#000000` | `#ffffff` |
| Texto de apoio | `ink-muted` | `rgba(0,0,0,0.6)` | `rgba(255,255,255,0.7)` |
| Positivo | `success` | `#0064b7` | `#53b1ff` |
| Atenção | `warning` | `#f5a623` | `#f5a623` |
| Negativo | `danger` | `#c81b3a` | `#c81b3a` |

**Paleta de dados** (nesta ordem): `data-1` azul, `data-2` laranja, `data-3` dourado, `data-4` azul-escuro (azul-claro no Escuro), `data-5` azul-claro (amarelo no Escuro), `data-6` cinza. Azul e laranja formam um par seguro para daltônicos; `data-4` a `data-6` mudam de valor entre os temas para manter contraste.

**Contraste.** Estes pares ficam abaixo do piso (4,5:1 para texto, 3:1 para marcas de gráfico) e foram mantidos com o valor de origem: `warning` sobre `surface` (1,9:1, claro); `danger` sobre `surface` (3,1:1, escuro); `data-3` sobre `surface` (1,9:1, claro); `data-5` sobre `surface` (2,2:1, claro). Use-os só em texto grande, decoração ou áreas amplas com rótulo ao lado. Os demais pares de texto passam 4,5:1.

**Proporção:** ~80% branco ou preto, ~12% azul, ~8% cinzas e laranja. A origem não define verde: variação positiva (`success`) usa o azul de link e o negativo usa `danger` (carmim) — sempre com seta e texto. No tema Claro o contorno `line-strong` tem pouco contraste; o rótulo garante a leitura.

## Tipografia

Uma família: **Source Sans 3** (300, 400, 500, 600, 700). Títulos em 300 com entrelinha 1,25; corpo de 16–18px com 1,5; botões em 700 com espaçamento de +0,3 a +0,45px. KPIs em `display-lg` (44px/300).

```html
<link href="https://fonts.googleapis.com/css2?family=Source+Sans+3:wght@300;400;500;600;700&display=swap" rel="stylesheet">
```

## Formas e espaçamento

Botões e chips `radius-pill`; cards `radius-md` (8px); campos `radius-sm` (4px); faixas `radius-none`. Base de 8px; padding de card 24–32px; 96px entre faixas de página. Botão de chamada com 48px de altura (`button-lg`); nos painéis, a versão compacta de 40px (`button-md`).

## Dados e gráficos

Série principal em `data-1` (azul), comparação em `data-2` (laranja). Trilhos em `bg`, linhas de tabela em `line-strong`, eixos em `ink-subtle` 14px. O dourado (`gold-start` → `gold-end`) é só para um selo de destaque, nunca série comum.

## Iconografia

Ícones-linha de 20–24px, traço 1,5px, cantos arredondados, na cor do texto (`ink-muted`; `ink` no item ativo). Sem emoji e sem ícones preenchidos coloridos. O sistema não traz logotipo: onde couber marca, escreva o nome em texto.

## Voz

Neutra e informativa. Títulos curtos ("Conclusos por unidade"), números seguidos de rótulo minúsculo ("312 conclusos"), datas e números no formato brasileiro (`1.248`, `87%`, `Março`).

## Usando este sistema

Tokens viram variáveis CSS (`var(--primary)`, `var(--space-4)`…). Temas: `data-theme="light"` e `data-theme="dark"` no `<html>`. Componentes são só CSS (`components/bundle.css`, prefixo `fx-`), sem JavaScript. Comece pelo exemplo `Dashboard` e troque títulos, números e tabelas. A faixa azul é o componente `Band` (`fx-band`).
