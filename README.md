# Ramiro Herrera — Portfolio

Personal portfolio for Ramiro Herrera, IT Systems Administrator and Network Support based in Stockton, CA.

**Live site:** https://xotwod197.github.io/Ramiros_Portfolio/

The site covers endpoint deployment, PowerShell automation, engineering test-lab support and networking work at a two-site manufacturer, plus personal builds and certification progress (CompTIA A+; Network+ and CCNA in progress).

## Pages

| Page | Contents |
| --- | --- |
| `index.html` | PowerShell-console intro, About, Skills, Experience, a few featured projects, Certifications & education, printable Résumé with PDF download, Links, Contact |
| `projects.html` | All projects with screenshots — filter by *At WCMagnetics* / *Personal builds* (the filter is kept in the URL hash, so `projects.html#work` links straight to the work list) |

## Files

```
index.html                  Home page
projects.html               Projects page
site.css                    Shared stylesheet for both pages (design tokens, layout, print rules)
ramiro-herrera-resume.pdf   Downloadable résumé
og-image.png                1200×630 share preview for LinkedIn, Slack, iMessage, X
images/                     Profile photo and project screenshots
```

There are no frameworks, dependencies or build step. Fonts (Geist, JetBrains Mono) load from Google Fonts.

## Editing

- **Preview locally:** open `index.html` in a browser, or run `python3 -m http.server` in this folder and visit http://localhost:8000.
- **Add a project:** copy a `<article class="card">` block in `projects.html`. Set `data-group` to `work` or `personal`, update the count on the matching filter button, and drop any screenshot in `images/`. A card whose image file is missing simply shows without the picture.
- **Project screenshots:** 16:10 works best (e.g. 1600×1000); PNG or WebP. Cards crop from the top-left, so keep the important part of the UI there.
- **Update the résumé:** edit the Résumé section in `index.html`, then replace `ramiro-herrera-resume.pdf` with a fresh export so the two match.
- **Change the site address:** update `og:url`, `canonical`, and both `og-image.png` URLs in the `<head>` of each page.
- **Styling:** everything visual lives in `site.css`; both pages share it, so a change there applies to both.

## Deployment

GitHub Pages builds from the `main` branch root. Every push to `main` redeploys the site, usually within a minute. The deploy status is shown on the repository's **Actions** tab under "pages build and deployment".
