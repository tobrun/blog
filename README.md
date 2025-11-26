# Blog Project

This is a my personal blog website built with Astro, TypeScript, and MDX. It serves as a  blog to share technical articles and tutorials.

## Project Structure

```
/blog
├── src/
│   ├── content/blog/        # Blog posts (MDX files)
│   ├── components/          # Reusable React/Astro components
│   ├── layouts/             # Page layouts
│   ├── pages/               # Page routes
│   ├── styles/              # Global styles
│   └── assets/              # Static assets (images, fonts)
├── public/                  # Public assets (favicons, etc.)
├── astro.config.mjs         # Astro configuration
├── package.json             # Project dependencies and scripts
└── tsconfig.json            # TypeScript configuration
```

## Getting Started

### Prerequisites

- Node.js (v18 or later)
- npm (v8 or later)

### Installation

1. Clone the repository
2. Install dependencies:
   ```bash
   npm install
   ```

### Development

To start the development server:
```bash
npm run dev
```

This will start the Astro development server at http://localhost:4321

### Building

To build the static site:
```bash
npm run build
```

The generated static files will be in the `dist` directory.

### Preview

To preview the built site locally:
```bash
npm run preview
```

## Writing Posts

Blog posts are written in MDX format and placed in `src/content/blog/`. Each post should include frontmatter with:
- `title`: Post title
- `description`: Short description
- `pubDate`: Publication date
- `heroImage`: Path to featured image
- `tags`: Array of tags

Example frontmatter:
```yaml
---
title: "My Blog Post"
description: "A brief description of the post"
pubDate: "2025-01-01"
heroImage: "../../assets/my-image.png"
tags:
  - JavaScript
  - Web Development
---
```

## Deployment

The site is configured to deploy to GitHub Pages at `/blog` base path. See `.github/workflows/main.yml` for deployment configuration.

## Contributing

1. Fork the repository
2. Create a feature branch
3. Commit your changes
4. Push to the branch
5. Create a pull request

## License

This project is licensed under the MIT License - see the LICENSE file for details.
