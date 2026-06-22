# Uptime Kuma — Compact Theme

A sleek, low-contrast **dark theme** for [Uptime Kuma](https://github.com/louislam/uptime-kuma) status pages, tuned for **dense dashboards on big screens / TVs**. It packs many monitors into a compact, full-width grid with status-coloured uptime pills and tidy heartbeat bars.

## Features

- **Compact full-width grid** — cards stretch to fill the row (`auto-fit` + `1fr`), so there's no empty gap on the right edge.
- **Status-coloured uptime pills** — green for healthy, red for down, amber for warnings, with high-contrast text (no washed-out grey).
- **Bottom-aligned heartbeat bars** — bars line up along the bottom of every card in a row, regardless of name length or cert-expiry pills.
- **Inline layout** — the uptime percentage sits inline next to the name and cert-expiry badge instead of overlapping it.
- **Rounded cards** with subtle depth and a hover lift.
- **Responsive scaling** — wider, more readable cards on ≥2560px displays and larger text on 4K (≥3840px) for at-a-distance viewing.
- **Theming via CSS variables** — colours, radius, spacing, and card width are all defined in `:root`.

## Installation

1. Open Uptime Kuma and go to your **Status Page**.
2. Click **Edit**.
3. Paste the contents of [`kuma.css`](./kuma.css) into the **Custom CSS** field.
4. **Save**.

> The theme is applied entirely through the status page's Custom CSS field — no rebuild or server changes required.

## Customization

All key values live in the `:root` block at the top of `kuma.css`:

```css
:root {
    --background-color: #1b1b29;   /* page background          */
    --elevated-bg-color: #2b2b3b;  /* monitor card background  */
    --accent-color: #5b8def;       /* interactive accent       */
    --ok-color: #3bd671;           /* "healthy" green          */

    --compact-min-width: 22ch;     /* min card width (density) */
    --compact-gap: 0.35rem;        /* space between cards      */
    --compact-padding: 0.4rem 0.55rem;
}
```

- **More / fewer cards per row:** lower or raise `--compact-min-width` (e.g. `18ch` = denser, `26ch` = larger cards).
- **Brand colour:** change `--accent-color` (and `--highlight-color` for buttons / heartbeat bar).
- **Tighter / looser:** adjust `--compact-gap` and `--compact-padding`.

## Compatibility

Built against Uptime Kuma's status-page DOM. Selectors target the standard status-page classes (`.item`, `.item-name`, `.badge`, `.beat-bar`, etc.), so it should work across recent Uptime Kuma versions. If a future release changes the markup, open an issue.

## License

[MIT](./LICENSE)
