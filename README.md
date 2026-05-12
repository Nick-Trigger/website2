# nicholastrigger.com

Personal portfolio site for Nicholas Trigger — Duke BME Alum '26.

Live at [nicholastrigger.com](https://nicholastrigger.com).

---

## Stack

- **[Astro](https://astro.build)** — static site framework
- **[Tailwind CSS v4](https://tailwindcss.com)** + **[DaisyUI v5](https://daisyui.com)** — styling and components
- **[MDX](https://mdxjs.com)** — markdown + JSX for project pages
- **[@tailwindcss/typography](https://tailwindcss.com/docs/typography-plugin)** — prose rendering

---

## Project Structure

```text
/
├── public/                  # Static assets (images, PDFs, ibom.html)
├── src/
│   ├── components/          # HorizontalCard, Header, SideBar, Footer, etc.
│   ├── layouts/
│   │   ├── BaseLayout.astro     # Root shell (sidebar, header, footer)
│   │   ├── ProjectLayout.astro  # Reusable project detail page template
│   │   └── PostLayout.astro     # Blog post layout
│   ├── pages/
│   │   ├── index.astro          # Home / landing page
│   │   ├── projects.astro       # Projects listing
│   │   ├── cv.astro             # CV page
│   │   └── projects/
│   │       ├── arm.astro            # Arterial Line Training Device
│   │       ├── clabsi/
│   │       │   ├── index.mdx        # CLABSI project detail page
│   │       │   └── poster.astro     # Capstone poster viewer
│   │       └── dog/
│   │           ├── index.mdx        # Dog activity tracker detail page
│   │           └── posters.astro    # Tabbed poster viewer (2 teams)
│   └── styles/
│       └── global.css
└── package.json
```

---

## Pages

| Route | Description |
| ----- | ----------- |
| `/` | Home — bio, featured projects, experience |
| `/projects` | Full projects listing |
| `/projects/arm` | Arterial Line Placement Training Device |
| `/projects/clabsi` | CLABSI UV-C Disinfection Device |
| `/projects/clabsi/poster` | CLABSI capstone poster viewer |
| `/projects/dog` | Dog Activity Tracker (TA/consulting role) |
| `/projects/dog/posters` | Tabbed poster viewer for both Foundry teams |
| `/cv` | CV / resume |
| `/clabsi-ibom.html` | Interactive KiCad BOM (served as static HTML) |

---

## ProjectLayout Template

`ProjectLayout.astro` is a reusable layout for project detail pages. Use it from an `.mdx` file via frontmatter:

```yaml
---
layout: ../../layouts/ProjectLayout.astro
title: "My Project"
description: "One-line description."
heroImage: "/image.png"
badge: "Category"
tags:
  - Tag1
  - Tag2
githubUrl: "https://github.com/Nick-Trigger/repo"
docs:
  - title: "Document Name"
    url: "/path/or/url"
    description: "Short description"
---
```

The slot content (markdown body) is rendered with `prose` typography styles.

---

## Commands

| Command | Action |
| ------- | ------ |
| `npm install` | Install dependencies |
| `npm run dev` | Start dev server at `localhost:4321` |
| `npm run build` | Build to `./dist/` |
| `npm run preview` | Preview production build locally |
