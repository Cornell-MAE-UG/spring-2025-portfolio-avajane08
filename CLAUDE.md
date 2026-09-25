# CLAUDE.md

Personal engineering portfolio for Ava Farkash (Cornell ME, class of May 2027). Jekyll site on GitHub Pages, started from the MAE course portfolio template.

## Working rules
- Do not change anything until Ava says what to work on. Inspect and report first when asked to "take a look".
- Do not commit or push unless asked.
- Ava's writing is first person. Keep new copy in her voice and don't invent facts, dates, metrics or roles. Ask when unsure.
- Fix typos only when asked or when already editing that line, and mention it.
- Never put private notes in published files (no HTML comments with to-dos).

## Stack
- Jekyll 3.x via the `github-pages` gem, `jekyll-theme-minimal`, kramdown (GFM), plugins: `jekyll-feed`, `jekyll-include-cache`, `jekyll-seo-tag`.
- Bootstrap 5 and Bootstrap Icons load from CDN in `_layouts/default.html`.
- `color_scheme: light` in `_config.yml` feeds `assets/css/main.scss`, which imports `_sass/custom.scss`. Fonts (imported in `main.scss`): Source Sans 3 (regular weight) for body text and nav links, Barlow Condensed for the name in the navbar and all headings.
- `baseurl` is `/spring-2025-portfolio-avajane08`. `url` is blank.
- Preview locally with `bundle exec jekyll serve` and open `http://localhost:4000/spring-2025-portfolio-avajane08/`. `_site/` is generated and gitignored.

## Structure
```
index.md                 Homepage (About Me), layout: default
_pages/cv.md             /cv/        CV page + resume PDF link
_pages/projects.md       /projects/  Gallery loop over site.projects (skips category: beyond)
_pages/beyond-engineering.md  /beyond-engineering/  Gallery of projects with category: beyond
_projects/*.md           One file per project -> /projects/<filename>/
_layouts/default.html    Bootstrap navbar (Home, Projects, Beyond Engineering, CV), footer
_layouts/project.html    Title, floated image, body, technologies, back link
_sass/custom.scss        Theme variables and shared styles
assets/css/main.scss     Entry point: font, gallery grid, image-row
assets/images/           Thumbnails and photos
assets/*.pdf             Resumes, reports, assignments (PDFs live here, not assets/files/)
```

## Project front matter
```yaml
---
layout: project
title: "Project title"
description: One or two sentences about the project.
technologies: [Solidworks, Ansys]   # rendered as "Technologies Used"; use [N/A] if none
image: /assets/images/thumbnail.jpg # gallery thumbnail only
show_hero: true                     # optional: also show the image floated at the top of the project page (off by default)
---
```
- Filename must end in `.md`.
- Add `category: beyond` to put a project on the Beyond Engineering tab (theater, volunteering, hobbies) instead of Projects; its back link then points there too.
- The gallery has no `date` sort and no `hidden` option, so order follows filenames. Every project needs an `image`, since there is no fallback thumbnail.

## Conventions
- Asset paths always go through `relative_url`: `{{ '/assets/images/x.jpg' | relative_url }}`. Never a bare `/assets/...` and never backslashes.
- Images in project bodies use `<img src="..." alt="..." width="600">`. Side-by-side photos use `<div class="image-row">`.
- PDFs embed with:
  ```html
  <div class="pdf-container">
    <iframe src="{{ '/assets/FILE.pdf' | relative_url }}" width="100%" height="800px"></iframe>
  </div>
  ```
- Two PDFs side by side: wrap two `<div class="pdf-col">` (each with an `<h3>` and the iframe) in `<div class="pdf-row">`. It widens past the 600px column and stacks on narrow screens.
- Side photos on a project page use `<figure class="side-image"><img src="{{ '/assets/images/x.jpg' | relative_url }}" alt="..."></figure>` placed right after a `###` heading. They float beside the text and alternate on their own (1st right, 2nd left, and so on), so just add figures in order.
- YouTube embeds use a standard `<iframe>` from the share dialog.
- Use plain hyphens in new filenames. Avoid spaces and parentheses in asset names.
- Math: MathJax is not loaded on this site. Use `<sup>`/`<sub>` and plain text unless MathJax is added.

## CV (`_pages/cv.md`)
- Markdown with `####` section headings: Objective, Education, Skills, Projects, Work Experience, Achievements & Certifications, Extracurricular Activities, References.
- Update the "Download my CV" link whenever a new resume PDF is added to `assets/`.
- Keep CV project entries consistent with the projects on the site, and dates consistent with the resume PDF.

## Known issues (not yet fixed)
- `_projects/DBF25-26.md` and `_projects/DBF26-27.md` have no body content yet.
- `_pages/projects.md` title is `<Ava Farkash> - Portfolio`, and the footer says "© 2024".
- `url` in `_config.yml` is blank and `README.md` is still the course instructions.
- Older resume PDFs and stray files (`3240pset4(1).pdf`) sit in `assets/`.
- The CV Projects section has no entries for DBF 26-27 or the Rigidized projects.
- `CLAUDE.md` is not in `exclude:` in `_config.yml`, so Jekyll publishes it at `/CLAUDE/`.
