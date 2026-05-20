# Entrata Time Zones

A clean, single-file time zone widget for embedding in a Guru card via iframe. Shows the current local time for **Utah**, **India**, **Israel**, and **Amsterdam**.

- Zero dependencies, zero build step — just one `index.html`.
- Auto-updates every second using the browser's `Intl.DateTimeFormat` (DST handled automatically).
- Light & dark mode via `prefers-color-scheme`.
- Responsive: 4 columns on desktop, 2 on tablet, 1 on mobile.

## Local preview

```bash
python3 -m http.server 8080
# then open http://localhost:8080
```

## Hosting options (pick one)

All are free for static sites.

### 1. GitHub Pages (simplest)

```bash
git add .
git commit -m "Initial commit"
git branch -M main
git remote add origin git@github.com:<your-user>/guru-time-zone-widget.git
git push -u origin main
```

Then in the repo on GitHub: **Settings → Pages → Source: `main` / `(root)` → Save**.

Your widget will be live at `https://<your-user>.github.io/guru-time-zone-widget/`.

### 2. Vercel

```bash
npx vercel --prod
```

### 3. Netlify

Drag-and-drop the project folder into [app.netlify.com/drop](https://app.netlify.com/drop).

## Embedding in Guru

Guru supports embedded content in cards. Once hosted, paste the URL into a Guru card using the embed/iframe block:

```html
<iframe
  src="https://<your-host>/"
  width="100%"
  height="320"
  style="border:0;"
  title="Entrata Time Zones"
></iframe>
```

If Guru asks for just a URL, give it the hosted URL directly.

## Customizing

All locations live in the `LOCATIONS` array near the top of the `<script>` tag in `index.html`. Each entry takes:

```js
{
  name: "Utah",          // big label
  region: "Lehi, USA",   // small label underneath
  flag: "🇺🇸",            // emoji shown to the left
  timeZone: "America/Denver", // any valid IANA time zone
}
```

To change colors, edit the CSS variables in `:root` at the top of the `<style>` block.
