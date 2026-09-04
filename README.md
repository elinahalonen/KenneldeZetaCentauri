# Kennel de Zeta Centauri — website

A static site (plain HTML + CSS, no build step) for **Zeta Centauri**, a Polish Hunting
Spaniel kennel in North Holland, the Netherlands. Sibling site to the
[BusyDoggie blog](https://busydoggie.com).

Live at **https://kenneldezetacentauri.com** (GitHub Pages, custom domain).

## Important: absolute paths

Every page uses **absolute paths** (`/styles.css`, `/assets/logo.png`, `/dogs/grace.html`,
etc.), not relative ones. This only works because the site is served from a domain root
(the custom domain) — see the `deploy-static-site-github-pages` skill's gotcha about this
if the site is ever moved to a GitHub Pages *project* subpath (`user.github.io/repo/`),
which would break every absolute link.

## Site structure

```
/                                Home
/about/                          About -> Our Story
/dogs/                           Our Dogs (landing: family across generations)
  grace-astra.html                 -> Grace & Astra (hub: profiles, gallery, video)
  grace.html                         -> Grace (full profile + show results)
  astra.html                         -> Astra (full profile + show results)
  litters/                          -> Our Litters (hub)
    a-litter/                          -> A Litter: Grace x Hunter (one long story page)
    planned/                           -> Planned: Astra x Bueno (one long page)
/breeding-philosophy/            Landing + 8 subpages (the-basics, why-this-breed-
                                  matters-to-us, what-we-are-trying-to-breed,
                                  choosing-a-mating, doing-right-by-the-dog,
                                  how-we-raise-puppies, matching-puppies-to-homes,
                                  following-the-dogs-we-breed)
/about-the-breed/                Landing + 6 subpages (about-the-polish-hunting-spaniel,
                                  what-are-psms-actually-like, is-a-psm-right-for-you,
                                  breed-history, breed-standard, videos)
/puppy-families/                 Landing + 7 subpages (bringing-your-puppy-home,
                                  the-first-year, confidence-and-trust, health,
                                  training-and-activities, recommended-resources,
                                  when-you-need-us)
/resources/                      Landing + 5 category pages (breeding-and-genetics,
                                  puppy-development, behaviour-and-training,
                                  health-structure-movement, books-and-further-reading)
/contact.html                    Contact
```

Every subpage is `<folder>/index.html` so its URL has no `.html` (e.g.
`/breeding-philosophy/the-basics/`). `Litters` is intentionally **not** in the main
nav — it's reached via the Our Dogs page — while it's still being built out.

## Content status

Most of the above are **scaffolds**, not finished pages: real "keep" intro copy (from
the agreed content map) plus a clearly-labelled "Planned coverage (draft notes)" list
and a "Source material to mine when writing" line, ready for content to be dropped in.
Pages with real, finished content: Home, About (partial), Our Dogs overview, Grace,
Astra, Litters overview, Planned Litter (partial — real Astra/Bueno data, new sections
scaffolded), A Litter (partial — real puppy names, individual stories still to write),
Contact.

**A Litter privacy note:** the content map that drove this site flags some family/puppy
details as private (e.g. specific placement circumstances). Those were deliberately
**left out** of the public scaffold — check the content map before adding puppy stories,
and keep anything marked private out of the live site.

## Adding your photos

1. Put images in `assets/photos/` (compressed: heroes/backgrounds < ~400 KB, portraits < ~250 KB).
2. Find the matching **photo slot** in the HTML — a `<div class="photo-slot">…</div>`.
   Replace it with a real image, e.g.:
   ```html
   <img src="/assets/photos/astra.jpg" alt="Astra in the dunes" class="ratio-portrait">
   ```
3. **Hero image** is set in `styles.css` (`.hero` background).

## Logo assets (`assets/`)
- `logo.png` — black + gold, for light backgrounds (header)
- `logo-cream.png` — cream monotone, for dark backgrounds (footer)
- `logo-gold.png` — rose-gold monotone, alternative for dark backgrounds
- `logo-master.pdf` — original vector master from the designer

## Publishing / DNS

Already live. DNS is on Namecheap; see the `deploy-static-site-github-pages` skill for
the exact records and troubleshooting steps if the domain ever needs re-pointing.

## Cross-linking with BusyDoggie
- This site links to `https://busydoggie.com` in the nav and footer.
- On BusyDoggie, "Kennel de Zeta Centauri" should point at `https://kenneldezetacentauri.com`.
