# ColorCard

Card inteiro em cor vibrante, que quebra o ritmo do preto.

- `<div class="cz-color" style="--c:var(--data-1)">` com título (`cz-color-title`, 24px/400) e número (`cz-color-num`, 62px).
- Quatro cores: `data-1` violeta (a mais usada), `data-2` magenta, `data-3` laranja, `data-4` coral; `radius-xxl` (30px).
- Um ou dois por página; três já viram mural. É card, nunca fundo de seção.
- Texto branco (`ink`) por padrão: no violeta passa com folga (5,3:1); no magenta (3,4:1) e no coral (3,1:1) use só texto de 24px ou mais; no laranja (2,6:1) não passa — troque para preto com `--c-ink:var(--on-primary)`.
- Você fornece o título e o número.
