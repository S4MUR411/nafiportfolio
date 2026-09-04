# Nafiur Ahmed — Portfolio

A static, typography-led portfolio site built for GitHub Pages. No backend, no build step — just HTML, CSS, and vanilla JavaScript.

## File structure

```
/
├── index.html          Home
├── about.html           About + Skills
├── experience.html      Professional & academic experience timeline
├── education.html       Degrees
├── work.html            Selected work / highlights
├── contact.html         Contact links + CV download
├── css/
│   └── style.css
├── js/
│   └── script.js
├── assets/
│   ├── images/          (empty — see note inside)
│   ├── favicon/         favicon.png, favicon-192.png, favicon-512.png
│   └── resume.pdf       ← add your CV here (see below)
├── robots.txt
└── sitemap.xml
```

## 1. Add your résumé PDF

The "Download CV" links on the home and contact pages point to `assets/resume.pdf`. Export your résumé as a PDF and place it at that exact path (same filename) — no code changes needed.

## 2. Update the placeholder URL

Every page has two placeholder URLs to update once you know your final GitHub Pages address (`og:url` and the `<link rel="canonical">` tag), plus one in `robots.txt` and six in `sitemap.xml`. They're currently set to `https://nafiurahmed.github.io/`. If you publish from a project repo instead of a `username.github.io` repo, your real URL will look like `https://nafiurahmed.github.io/repo-name/` — update all of the above accordingly (a find-and-replace across the project works well here).

## 3. Put this on GitHub

```bash
git init
git add .
git commit -m "Initial portfolio"
git branch -M main
git remote add origin https://github.com/<your-username>/<your-repo>.git
git push -u origin main
```

## 4. Enable GitHub Pages

1. On GitHub, open your repository → **Settings** → **Pages**.
2. Under **Build and deployment**, set **Source** to `Deploy from a branch`.
3. Choose the `main` branch and the `/ (root)` folder, then **Save**.
4. GitHub will publish the site at `https://<your-username>.github.io/<your-repo>/` (or `https://<your-username>.github.io/` if the repo is named `<your-username>.github.io`). It can take a minute or two to go live.

## 5. Optional: replace the favicon

`assets/favicon/` currently contains a simple generated "NA" monogram in the site's accent green. Swap in your own square image at the same three sizes (32, 192, 512px) if you'd like something different — no HTML changes required as long as the filenames match.

## 6. Optional: add photography or a portrait

The design deliberately doesn't require any images — it leans on type and whitespace instead. If you want to add a portrait or project imagery later, drop files into `assets/images/` and reference them with a relative path.

---

## Design decisions

- **Typography as the hero.** With no visual portfolio pieces to lead with (this is a coordination/communications background, not a photography one), the display serif (Fraunces) paired with a clean sans (Inter) carries the personality of the site instead of imagery or color.
- **Editorial layout, not cards.** Experience, education, and selected work all use hairline-rule dividers and a consistent two-column (date/detail) grid rather than boxed, shadowed cards — closer to a printed editorial spread than a SaaS dashboard.
- **Restrained palette.** A warm paper background, near-black ink, and a single deep green accent (chosen with XPRIZE's climate/energy/health focus in mind, without being literal about it) — no gradients, no multi-color system.
- **One motion moment.** Content on each page fades and lifts gently into place on load; everything else (nav underlines, button states) only responds to direct interaction. `prefers-reduced-motion` disables all of it.
- **Content fidelity.** Every fact, figure, date, and title on the site is taken directly from the supplied résumé. Where the résumé didn't include something (a project gallery, social profiles beyond the personal site), the site simply omits it rather than inventing it.
