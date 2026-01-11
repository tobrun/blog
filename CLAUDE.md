# CLAUDE.md

This file provides guidance to Claude Code (claude.ai/code) when working with code in this repository.

## Commands

```bash
npm run dev      # Start dev server at http://localhost:4321
npm run build    # Build static site to dist/
npm run preview  # Preview built site locally
```

## Architecture

This is an Astro 5 static blog deployed to GitHub Pages at `https://tobrun.github.io/blog`.

**Content System:**
- Blog posts are MDX files in `src/content/blog/`
- Content schema defined in `src/content.config.ts` with Zod validation
- Required frontmatter: `title`, `description`, `pubDate`
- Optional: `heroImage` (use relative path from post), `updatedDate`, `tags[]`

**Routing:**
- `src/pages/index.astro` - Homepage with featured post + card grid
- `src/pages/[...slug].astro` - Dynamic blog post pages
- `src/pages/articles.astro` - All posts listing
- `src/pages/articles/[tag].astro` - Posts filtered by tag
- `src/pages/rss.xml.js` - RSS feed

**Base URL Handling:**
Pages use a `withBase()` helper to prefix all internal links with `/blog` (the configured base path). When linking internally, use this pattern:
```typescript
const base = import.meta.env.BASE_URL;
const normalizedBase = base.endsWith('/') ? base.slice(0, -1) : base;
const withBase = (path = '') => `${normalizedBase}/${path.replace(/^\/+/, '')}`;
```

**Site Constants:**
Global configuration in `src/consts.ts` (site title, description, GA measurement ID).

**Deployment:**
Pushes to `main` trigger GitHub Actions workflow (`.github/workflows/main.yml`) that builds and deploys to GitHub Pages.
