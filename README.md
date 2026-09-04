# Kennel de Zeta Centauri — website

A small static website (plain HTML + CSS, no build step) for **Zeta Centauri**,
a kennel of Polish Hunting Spaniels in the Kennemerland dunes, the Netherlands.
Sibling site to the [BusyDoggie blog](https://busydoggie.com).

## Pages
- `index.html` — home (hero + intro + doors + ethos + blog cross-link)
- `about.html` — the kennel story (Nell's legacy, nosework focus)
- `dogs.html` — Grace & Astra
- `litters.html` — planned/past litters + what to expect
- `contact.html` — enquiries

Shared look lives in `styles.css`. The header and footer are duplicated in each
page (intentionally — with five pages this is simpler than any tooling; if you add
a page, copy the `<header>` and `<footer>` blocks from an existing one).

## Adding your photos
1. Put images in `assets/photos/` (compressed: heroes/backgrounds < ~400 KB, portraits < ~250 KB).
2. Find the matching **photo slot** in the HTML — a `<div class="photo-slot">…</div>`.
   Replace it with a real image, e.g.:
   ```html
   <img src="assets/photos/astra.jpg" alt="Astra in the dunes" class="ratio-portrait">
   ```
3. **Hero image** is set in `styles.css` (`.hero` background). Replace the final
   gradient layer with `url('assets/photos/hero.jpg')`.

Suggested shots: `hero.jpg` (wide, Grace & Astra), `grace.jpg` / `astra.jpg`
(portrait), a wide dune landscape for the About/ethos bands, and your litter
announcement graphic for `litters.html`.

## Logo assets (`assets/`)
- `logo.png` — black + gold, for light backgrounds (header)
- `logo-cream.png` — cream monotone, for dark backgrounds (footer)
- `logo-gold.png` — rose-gold monotone, alternative for dark backgrounds
- `logo-master.pdf` — original vector master from the designer

## Publishing on GitHub Pages
1. Create a new repository, push these files to it.
2. Repo **Settings → Pages → Build and deployment → Deploy from a branch**,
   choose `main` / `root`. Your site goes live at `https://<username>.github.io/<repo>/`.
3. **Custom domain:** add a file named `CNAME` containing just your domain
   (e.g. `zetacentauri.com`), set it under Settings → Pages, and point your
   domain's DNS at GitHub Pages.

## Cross-linking with BusyDoggie
- This site links to `https://busydoggie.com` in the nav and footer.
- On BusyDoggie, point "Kennel de Zeta Centauri" at this site's domain.

## Still to do (placeholders marked in the pages)
- Final About copy (in your own words)
- Grace's details and both dogs' character lines
- Verify Astra & Bueno data against your records
- Real email / Instagram handle on Contact
- Photos throughout
