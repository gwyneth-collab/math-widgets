# Math Widgets

Interactive classroom widgets for teaching number classification. Each is a single
self-contained HTML file — no build step, no dependencies, no server code. Open one
directly in a browser, or embed it in a site with an iframe.

## Widgets

- **number-set-nester.html** — drag numbers into the smallest set that holds them.
  Generates a fresh set of twelve numbers each round.
- **number-set-venn.html** — the nesting diagram alone, with overlays for
  prime/composite, even/odd, and positive/negative.

## Embedding

```html
<iframe src="https://USERNAME.github.io/REPO/number-set-nester.html?title=0"
        style="width:100%;height:1500px;border:0;" scrolling="no"></iframe>
```

## URL options

| Parameter | Effect |
|---|---|
| `?title=0` | Hide the widget's own heading |
| `?reveal=0` | Show all set definitions from the start (nester only) |
| `?advanced=1` | Allow `e` and `2π` in generated rounds (nester only) |
