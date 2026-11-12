---
name: dark-mode
description: "Use when implementing or fixing dark mode — semantic CSS variables, prefers-color-scheme defaults, light/dark/system toggles with persistence, preventing the flash of incorrect theme (inline head script, SSR cookies), color-scheme and light-dark(), form controls and scrollbars, images/SVG/shadows in dark themes, and contrast testing."
license: MIT
---

# Dark Mode

## When to Use This Skill
- Adding a dark theme to an existing site or app
- White flash before the dark theme applies
- Dark theme looks harsh or low-contrast

## Tokens
```css
:root {
  color-scheme: light;
  --bg: #ffffff; --surface: #f6f7f9; --text: #15171a; --text-muted: #5b6270;
  --border: #e3e6ea; --accent: #2457d6;
}
:root[data-theme="dark"] {
  color-scheme: dark;
  --bg: #0f1115; --surface: #171a20; --text: #e7e9ee; --text-muted: #a2a9b6;
  --border: #2a2f38; --accent: #7aa2ff;
}
@media (prefers-color-scheme: dark) {
  :root:not([data-theme="light"]) { color-scheme: dark; /* same dark values */ }
}
body { background: var(--bg); color: var(--text); }
```
- Components use only semantic tokens.
- `color-scheme` makes native controls, scrollbars, and form fields match.
- `light-dark(#fff, #0f1115)` is a concise alternative where browser support fits.

## Toggle: light / dark / system
```html
<script>
  // inline in <head>, before CSS paints
  try {
    const t = localStorage.getItem('theme');
    if (t === 'light' || t === 'dark') document.documentElement.dataset.theme = t;
  } catch {}
</script>
```
```js
function setTheme(t) {               // 'light' | 'dark' | 'system'
  if (t === 'system') { delete document.documentElement.dataset.theme; localStorage.removeItem('theme'); }
  else { document.documentElement.dataset.theme = t; localStorage.setItem('theme', t); }
}
```
- Default to **system**.
- SSR apps can store the choice in a cookie and render `data-theme` on the server.
- Update `<meta name="theme-color">` for mobile browser chrome.

## Design guidance
- Background: dark grey, not `#000`; express elevation with lighter surfaces instead of shadows.
- Desaturate and lighten accents; reduce pure white text slightly (`#e7e9ee`).
- Borders matter more in dark mode where shadows vanish.
- Images: avoid pure white backgrounds in illustrations; provide dark variants with `<picture><source media="(prefers-color-scheme: dark)">` or `currentColor` SVGs.
- Code blocks and charts need their own dark palettes.

## Testing
- Check every semantic text/background pair for contrast in both themes.
- Emulate in DevTools (Rendering → prefers-color-scheme).
- Test the toggle, system change while open, and first load with no stored preference.

## Rules
- Never hard-code colours in components.
- Transitions on theme switch should be instant or very short; avoid animating every element's colour.
