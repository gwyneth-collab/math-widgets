# EDRM Widgets

Interactive classroom widgets for environmental science. Each is a single self-contained
HTML file — no build step, no dependencies, no server code. Open one directly in a browser,
or embed it in a site with an iframe.

Kept separate from the math widgets one level up; the two groups publish side by side but
do not share an index.

## Widgets

- **quadrat-practice.html** — estimate percent cover in four 1 m × 1 m quadrats along a
  schoolyard tape. Seeded, so every student sees the same four quadrats and the work is
  gradeable; the answer key is counted off the generated vegetation rather than authored,
  so it is exact by construction. Students enter a name and hand in the summary line.

  Companion teaching material lives in `flagler-env-science/quadrat-sampling/` — a projected
  five-section version for class discussion (`widget.html`), and the script for it
  (`class-script.md`).

## Embedding

```html
<iframe id="quadrat-practice"
        src="https://USERNAME.github.io/REPO/edrm/quadrat-practice.html?title=0"
        height="1400" scrolling="no" style="width:100%;border:0;"
        title="Quadrat practice — estimate percent cover" loading="lazy"></iframe>

<script>
  addEventListener('message', function (e) {
    var frame = document.getElementById('quadrat-practice');
    if (!frame || e.source !== frame.contentWindow) return;
    if (e.data && e.data.type === 'quadrat-practice:height') frame.height = e.data.height;
  });
</script>
```

The widget detects that it is in an iframe, drops its card chrome so it sits flush in the
host page, and posts its content height out so the frame can size itself. The `height`
attribute above is only the value used before the first message arrives.

## URL options

| Parameter | Effect |
|---|---|
| `?title=0` | Hide the widget's own heading, for a page that supplies its own |

## Privacy

Quadrat Practice keeps a student's name and entries in `localStorage` under
`quadrat-practice-v1`, so a closed tab does not lose the period's work. Nothing is
transmitted anywhere — the page makes no network calls at all, and the only thing that
crosses the iframe boundary is a height integer.
