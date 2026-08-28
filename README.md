# Aoxue XU: Academic Homepage

Personal academic homepage for **Aoxue XU**, Master of Environmental Policy (iMEP) candidate at Duke University · Duke Kunshan University. Built on top of [AcaNova-X](https://github.com/yihangtao/AcaNova-X) v1.1.0.

Live site: **https://academic-homepage.hazalxu.click/**

## Content sources

All biographical content, publications, news, and honors are sourced from the applicant fact sheet at
`/Users/mac/Documents/PhD申请材料/My_Case/01-cv/applicant_fact_sheet.md`.
When the fact sheet is updated, mirror changes into the corresponding file:

| Fact sheet section | File to edit |
|---|---|
| Profile, contact, about, research thrusts | `index.html` |
| Publications | `data/publications.json` |
| News | `data/news.json` |
| Honors & Awards | `data/honors.json` |

## Customizing the "Research Workbench" link

The top navigation links to `https://hazalxu.click/` as a placeholder for the
research workbench (see `research-workbench-online/`). To change this:

1. Open `index.html`.
2. Find both occurrences of `https://hazalxu.click/` (desktop nav, line ~55; mobile nav, line ~77).
3. Replace with the actual workbench URL.

## Local preview

```bash
cd "/Users/mac/Documents/个人网页搭建/academic-homepage"
python3 -m http.server 8090
# Open http://127.0.0.1:8090/ in a browser
```

## Deployment

This site is deployed via **Cloudflare Pages**, connected to a GitHub repository at
`https://github.com/hazelxu-2003/academic-homepage`. Each `git push` to the `main` branch triggers a fresh build and deploy.

Initial setup:

1. Create an empty GitHub repository named `academic-homepage` under the `hazelxu-2003` account.
2. In Cloudflare dashboard, create a Pages project, connect to the GitHub repo, leave build settings at default (Framework preset: None; build command: empty; output dir: `/`).
3. Add the custom domain `academic-homepage.hazalxu.click` in Cloudflare Pages → Custom domains.

## File layout

```
academic-homepage/
├── index.html                 # Main landing page (Aoxue XU bio + dynamic sections)
├── pages/
│   ├── all-publications.html  # Filterable publication list
│   ├── all-news.html          # Full news archive
│   └── all-honors.html        # All awards
├── data/
│   ├── publications.json      # 4 entries (working paper + 3 published)
│   ├── news.json              # 5 recent entries
│   └── honors.json            # 5 awards
├── assets/
│   ├── profile.jpg            # Portrait (2:3 portrait)
│   ├── profile.webp           # WebP version (smaller)
│   └── publications/          # Paper thumbnails (currently placeholder)
├── script.js                  # Loads JSON, renders sections
└── styles.css                 # Customizations on top of Tailwind CDN
```

## Acknowledgements

Built with [AcaNova-X](https://github.com/yihangtao/AcaNova-X): modern academic homepage template.
