# Grafite

Grafite é uma linguagem de design para painéis analíticos, derivada do mockup de dashboard de leads: superfícies brancas divididas por linhas finas, números grandes em peso leve e uma paleta categórica viva para os dados. A cor de destaque principal é o **grafite** (`#2B2E33`) — ações, aba ativa, navegação e tooltips —, deixando que só os dados tenham cor. Funciona em dois temas, **Claro** e **Escuro**, com os mesmos tokens.

## Princípios

1. **O grafite conduz, os dados colorem.** Toda a interface (botões, abas, navegação, tooltips) é neutra em grafite; cores vivas existem só em gráficos e legendas.
2. **Números leves, rótulos ao lado.** KPIs em peso 300 e tamanho grande (`kpi-xl`), com o rótulo em `ink-muted` na mesma linha de base: "600 leads ativos".
3. **Linhas, não sombras.** Seções do painel são separadas por `line` de 1px; sombra só em menus e tooltips (`shadow-pop`).
4. **Cantos discretos.** `radius-sm` (4px) para controles, `radius-md` (6px) para painéis. Nada arredondado demais.
5. **Cor de status é significado.** `success` (petróleo) = ganho, `danger` (carmim) = perda. Nunca use as cores categóricas para status.
6. **Dois temas, um sistema.** No Escuro o grafite inverte: o botão primário fica grafite-claro com texto escuro; nada muda de lugar.

## Cores

| Papel | Token | Claro | Escuro |
|---|---|---|---|
| Destaque principal | `primary` | `#2B2E33` grafite | `#E4E6E9` grafite-claro |
| Texto sobre o destaque | `on-primary` | `#FFFFFF` | `#1E2024` |
| Seleção suave | `primary-soft` | `#E4E6E9` | `#2C2F35` |
| Link / foco / filtro ativo | `accent` | `#3B4FC4` | `#9AA8FF` |
| Fundo | `bg` | `#F7F7F8` | `#131417` |
| Painéis | `surface` | `#FFFFFF` | `#1B1D21` |
| Divisórias | `line` | `#E8E9EC` | `#2C2F35` |
| Texto | `ink` / `ink-muted` | `#1F2125` / `#6B6F77` | `#ECEDEF` / `#9A9EA6` |
| Ganho | `success` | `#0F5964` | `#3FB0BF` |
| Perda | `danger` | `#B0102A` | `#F0596E` |

**Paleta de dados** (nesta ordem): `data-1` coral, `data-2` âmbar, `data-3` índigo-noite, `data-4` sálvia, `data-5` ameixa, `data-6` oceano. No Escuro cada uma é clareada para manter contraste sobre `#1B1D21`.

**Contraste.** Todo texto passa 4,5:1 nos dois temas. Três cores categóricas do mockup ficam abaixo de 3:1 sobre branco no tema Claro — `data-1` coral (3,0:1), `data-2` âmbar (1,7:1) e `data-4` sálvia (2,3:1). Foram mantidas por fidelidade, com a regra: só em áreas grandes (fatias, barras grossas), sempre com legenda de texto ao lado, e com 2px de `surface` separando segmentos vizinhos.

**Proporção:** ~85% neutros (bg, surface, line, ink), ~10% grafite de destaque, ~5% cor de dados.

## Tipografia

Uma família: **Nunito Sans** (Google Fonts, 300–700) — humanista e arredondada como a do mockup. Fallback `Segoe UI`, `system-ui`.

- Título da página em peso **regular** (`page-title` 36px). Títulos de seção em **bold** (`section-title` 20px).
- KPIs em **300** (`kpi-xl` 44px, `kpi` 40px), com `font-variant-numeric: tabular-nums`.
- Texto corrido 16px regular; rótulos 15px em `ink-muted`; eixos e tooltips 12px.

```html
<link href="https://fonts.googleapis.com/css2?family=Nunito+Sans:wght@300;400;600;700&display=swap" rel="stylesheet">
```

## Layout

- Sidebar fixa de 280px em `surface`, separada do conteúdo por `bg`. Item ativo: fundo `primary-soft`, ícone e texto em `ink`, peso 600.
- Conteúdo: título da página + ação primária ("Criar ▾") à direita; abaixo, UM painel `surface` com borda `line` e `radius-md`, dividido internamente em blocos por linhas de 1px.
- Padding dos blocos `space-6`/`space-7`; grade de 12 colunas, blocos lado a lado em 7/5.

## Dados e gráficos

- **Funil:** barra empilhada de 8px (`radius-xs`), uma cor de dados por etapa, seguida da tabela: quadradinho de 14px, nome, quantidade, valor, tempo médio em `ink-muted`.
- **Donut:** espessura ~22% do raio, segmentos separados por 2px de `surface`, legenda à direita com valor e percentual em `ink-muted`.
- **Linhas:** 2px, curva suave, marcadores de 7px nos pontos de dados, área com degradê vertical `success-soft`/`danger-soft` → transparente. Grade horizontal em `line`, eixos em `ink-muted` 12px.
- **Tooltip:** fundo `primary` (grafite), texto `on-primary` 12–13px, `radius-sm`.
- **Legendas e filtros:** chips com borda `line-strong`, `radius-sm`; o selecionado ganha fundo `primary-soft`.

## Iconografia

Ícones-linha finos (1.5px) de 24px, cantos arredondados, cor `ink-muted` na navegação e `ink` no item ativo. Estilo Tabler/Lucide. Sem emoji, sem ícones preenchidos coloridos.

## Voz

Neutra e informativa. Títulos curtos ("Funil de leads", "Origens", "Motivos de perda"), números seguidos de rótulo minúsculo ("680 fechados"), datas e moeda no formato brasileiro (`R$ 3.000`, `Março`, `últimos 6 meses`).

## Usando este sistema

Tokens viram variáveis CSS (`var(--primary)`, `var(--space-6)`…); o tema é `data-theme="light"` ou `data-theme="dark"` no `<html>`. Componentes são só CSS (`components/bundle.css`, prefixo `gf-`). Para Power BI: página `#F7F7F8`, visuais `#FFFFFF` sem sombra e com borda `#E8E9EC`, cores de dados na ordem `data-1…6`, texto `#1F2125`/`#6B6F77`; versão escura com os valores da coluna Escuro.
