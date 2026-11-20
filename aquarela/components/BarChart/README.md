# BarChart

Barras horizontais e barra empilhada para composição.

- Barras: `aq-bars` com linhas `aq-bar-row` (rótulo, trilho, valor); o preenchimento usa `data-1`.
- Composição: `aq-stackbar` com um `<span>` por parte nas cores `data-1…`, seguida de tabela-legenda com `aq-swatch`.
- Use as cores `data-N` na ordem; cada parte tem rótulo e valor em texto.
- Você fornece categorias, valores e larguras em %.
