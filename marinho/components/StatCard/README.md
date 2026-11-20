# StatCard

Card de KPI do topo do painel: rótulo pequeno acima, valor grande abaixo, e um gráfico mínimo à direita.

- **Padrão** (`vn-stat`): fundo `surface`, rótulo `ink-muted`, valor estilo `stat` em `ink`. À direita: mini-barras (`vn-bars`) ou uma bolha de ícone.
- **Destaque** (`vn-stat vn-stat-hero`): degradê 135° `gradient-start` → `gradient-end`, todo texto `on-primary`, linha decorativa branca a 60%. No máximo dois por linha de KPIs, nas pontas.
- Raio `radius-lg`, padding `space-5`/`space-6`, largura mínima 300px.
- O consumidor fornece o rótulo, o valor já formatado (R$ 1.234,56) e o mini-gráfico.
