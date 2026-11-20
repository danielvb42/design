# Keycap

Teclas de atalho e a lista de comandos em que elas aparecem.

- Tecla: `<kbd class="tc-key">Ctrl</kbd>` — 20px de altura, `radius-xs`, degradê sutil `key-start` → `key-end`, borda `line`.
- Lista: `<div class="tc-palette">` com linhas `tc-cmd` (rótulo à esquerda, teclas em `tc-keys` à direita); a linha em foco leva `aria-selected="true"`.
- Mostre o atalho ao lado de toda ação que tenha um; é a única "profundidade" decorativa do sistema.
- Você fornece o nome do comando e as teclas.
