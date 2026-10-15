# Ramiro Herrera — Portfolio

Personal portfolio for Ramiro Herrera, IT Systems Administrator and Network Support based in Stockton, CA.

**Live site:** https://xotwod197.github.io/Ramiros_Portfolio/

The site covers endpoint deployment, PowerShell automation, engineering test-lab support and networking work at a two-site manufacturer, plus personal builds and certification progress (CompTIA A+; Network+ and CCNA in progress).

## What's on the page

| Section | Contents |
| --- | --- |
| Intro | PowerShell-console style summary (`Get-Technician \| Format-List`) |
| About | Background, current role, focus areas |
| Skills | Automation & deployment, systems & support, network & infrastructure, lab/data/web, plus a tools list |
| Experience | Current and past roles |
| Projects | Work projects and personal builds, some with screenshots |
| Certifications & education | Earned and in-progress certs, degree |
| Résumé | Printable résumé (print layout hides everything else) and PDF download |
| Links / Contact | GitHub, LinkedIn, email |

## Files

```
index.html                  The whole site: HTML, CSS and JS in one file
ramiro-herrera-resume.pdf   Downloadable résumé
og-image.png                1200×630 share preview for LinkedIn, Slack, iMessage, X
images/                     Project screenshots
```

There are no frameworks, dependencies or build step. Fonts (Geist, JetBrains Mono) load from Google Fonts.

## Editing

- **Preview locally:** open `index.html` in a browser, or run `python3 -m http.server` in this folder and visit http://localhost:8000.
- **Add a project:** copy the commented card template in the Projects section of `index.html`. Put any screenshot in `images/`.
- **Update the résumé:** edit the Résumé section in `index.html`, then replace `ramiro-herrera-resume.pdf` with a fresh export so the two match.
- **Change the site address:** update `og:url`, `canonical`, and both `og-image.png` URLs in the `<head>`.

## Deployment

GitHub Pages builds from the `main` branch root. Every push to `main` redeploys the site, usually within a minute. The deploy status is shown on the repository's **Actions** tab under "pages build and deployment".
