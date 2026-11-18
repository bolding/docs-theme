# docs-theme

The shared Bolding & Bruggeman layout of the documentation sites, taken from the B&B presentation
template (neutral white/grey, the logo colours as accents, Calibri):

- https://bolding.github.io/nesting-docs/ (pyGETM nesting)
- https://bolding.github.io/config-docs/ (pygetm-config)
- https://bolding.github.io/ocean-docs/ (the ocean-* packages)

Each docs repository has this repository as a submodule at `theme/`:

```bash
git submodule add https://github.com/bolding/docs-theme.git theme      # once
git submodule update --remote theme && git commit -am "Theme" && git push   # after a theme change
```

| File | |
|---|---|
| `style.css` | colours, fonts, top bar, title band, side menu, text, cards, footer |
| `code.css` | code highlighting (pygments `friendly`) |
| `logo_wide.png`, `logo_stacked.png` | the logos (top bar, footer, icon) |
| `related.js` | the related-sites line in every footer -- the one list of sites |
| `bbdocs.py` | the page frame and helpers the site builders import from `theme/` |

A change to `style.css`, the logos or `related.js` shows on all three sites after the submodule
update, without rebuilding them; a change to `bbdocs.py` needs the builders rerun.
