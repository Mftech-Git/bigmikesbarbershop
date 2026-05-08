# Big Mike's Barbershop

Static website for Big Mike's Barbershop, located at 4325 E Broadway Blvd, Ste A, Tucson, AZ 85711.

A single-file, dependency-free site. Just `index.html` and a couple of Google Fonts. Drop it on any static host.

## Live

Production domain: [bigmikesbarbershop.com](https://bigmikesbarbershop.com) (currently a GoDaddy placeholder, pending repoint).

## Local Preview

```bash
# any static server works, pick your poison
python3 -m http.server 8080
# then open http://localhost:8080
```

Or just double-click `index.html`.

## Deploy

### Azure Static Web Apps (recommended)

1. In the Azure portal, create a new Static Web App.
2. Source: GitHub. Repo: `Mftech-Git/bigmikesbarbershop`. Branch: `main`.
3. Build presets: **Custom**.
4. App location: `/`
5. Output location: leave blank (or `/`).
6. Azure auto-PRs the workflow file into `.github/workflows/`. Merge it.
7. Once provisioned, point `bigmikesbarbershop.com` (and `www`) at the Azure SWA hostname via GoDaddy DNS.

### GitHub Pages

1. Repo Settings, Pages, Source: `Deploy from a branch`, branch `main`, folder `/ (root)`. Save.
2. Add a `CNAME` file with `bigmikesbarbershop.com` if you want a custom domain.

### Anything else

Upload `index.html` to whatever you've got. Netlify, Cloudflare Pages, an S3 bucket, an old laptop running nginx in a closet. It's one file.

## Replacing the Logo

The site currently uses a placeholder SVG emblem in two places:

1. **Topbar** (small round badge, approx 36x36): the `<svg class="logo-mini">` block inside `.brandmark`.
2. **Hero** (large emblem above the title): the `<svg class="emblem">` block inside `.emblem-wrap`.

When the real logo file is ready (PNG with transparent background, or SVG):

```html
<!-- topbar -->
<img src="/logo.png" alt="Big Mike's Barbershop" class="logo-mini" />

<!-- hero -->
<img src="/logo.png" alt="Big Mike's Barbershop" class="emblem" />
```

Drop the file as `logo.png` (or whatever) at the repo root and update both src attributes.

## Editing Content

Everything lives in `index.html`. Common edits:

| What | Where |
|---|---|
| Price for men's cut | Search for `$25` |
| Hours | Search for `<ul class="hours-list"` |
| Phone number | Search for `4802711942` and `(480) 271-1942` |
| Address | Search for `4325 E Broadway` |
| Reviews | Search for `<article class="review"` |
| Brand colors | Top of `<style>`, the `:root` CSS variables |

## Stack

- Pure HTML, CSS, and a few lines of vanilla JS (today highlighter, scroll reveal, current-year footer).
- Google Fonts: Anton, Alfa Slab One, Crimson Pro, Special Elite.
- JSON-LD `BarberShop` schema for SEO.
- Mobile responsive, no framework, no build step.

## Credits

Site by [Mainframe Tech](https://mainframetech.us), Tucson, AZ.

## License

See `LICENSE`. Code is MIT. Brand, name, logo, and all content belong to Big Mike's Barber Shop LLC.
