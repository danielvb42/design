# BarChart

Barras horizontais e barra empilhada para composição.

- Barras: `eq-bars` com linhas `eq-bar-row` (rótulo, trilho, valor); o preenchimento usa `data-1`.
- Composição: `eq-stackbar` com um `<span>` por parte nas cores `data-1…`, seguida de tabela-legenda com `eq-swatch`.
- Use as cores `data-N` na ordem; cada parte tem rótulo e valor em texto.
- Você fornece categorias, valores e larguras em %.
