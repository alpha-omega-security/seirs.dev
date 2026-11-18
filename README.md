# SEIRs — Security Engineers in Residence

Landing page for the Security Engineers in Residence (SEIRs) initiative, run by [Alpha-Omega](https://alpha-omega.dev).

Plain static HTML and CSS, no build step. Hosted on GitHub Pages from the root of the `main` branch.

## Editing

- `index.html` — landing page
- `role.html` — SEIR role description
- `style.css` — shared styles

Push to `main` and GitHub Pages redeploys automatically.

## Images

`og-card.png` (social share card, 1200×630), `favicon-32.png` and
`apple-touch-icon.png` (180×180) are rendered from `og-card.svg`,
`favicon.svg` and `apple-touch-icon.svg`. Edit the SVG, then re-render the
PNG at the same size with headless Chrome or Chromium (the binary may be
`google-chrome`, `chromium` or `chrome-headless-shell`). Run from the repo
root so `og-card.svg` can load `alpha-omega-logo.png`:

```sh
CHROME="google-chrome --headless --hide-scrollbars --force-device-scale-factor=1"
$CHROME --window-size=1200,630 --screenshot=og-card.png og-card.svg
$CHROME --default-background-color=00000000 --window-size=32,32 \
  --screenshot=favicon-32.png favicon.svg
$CHROME --window-size=180,180 --screenshot=apple-touch-icon.png apple-touch-icon.svg
```

Check each output with `file *.png`. The card text uses
Helvetica/Arial, falling back to Liberation Sans (used for the committed PNG),
so renders differ slightly between machines.

The `og:image` URLs must stay absolute (`https://www.seirs.dev/...`).
