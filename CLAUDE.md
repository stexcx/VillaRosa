# CLAUDE.md

## Project Overview

Villa Rosa is a static HTML/CSS website showcasing a luxury vacation villa in Sardinia, Italy. It serves as a promotional/marketing site for tourism and vacation rental purposes. The content is primarily in Italian.

## Tech Stack

- **HTML5** - Semantic markup, no JavaScript
- **CSS3** - Modern features (flexbox, transitions, filters, media queries)
- **External CDNs** - Google Fonts (Montserrat, Playfair Display), Font Awesome icons
- **Package manager** - pnpm
- **Dev server** - `serve` (static HTTP server)

## Project Structure

```
VillaRosa/
├── index.html           # Landing page with hero image and welcome message
├── galleria.html        # Photo gallery with 14-slide CSS-only image slider
├── style.css            # All styles for both pages (responsive, mobile breakpoint at 768px)
├── img/                 # Image assets (foto1.jpg through foto14.jpg)
├── package.json         # Project manifest (only dev dependency: serve)
├── pnpm-lock.yaml       # Dependency lockfile
├── .eslintrc.json       # ESLint config (browser env, ES2021, eslint:recommended)
├── .codesandbox/        # CodeSandbox configuration (static runtime, port 5000)
├── .devcontainer/       # Dev Container config (TypeScript/Node image)
└── google*.html         # Google Search Console verification file
```

## Development Commands

```bash
# Install dependencies
pnpm install

# Start local dev server (serves static files)
pnpm start
```

The dev server runs via the `serve` package. Default port is 3000 locally, 5000 in CodeSandbox.

## Architecture Notes

- **No build step** - Files are served directly to the browser with no compilation or bundling.
- **No JavaScript** - The gallery slider is implemented entirely with CSS using hidden radio inputs and `:checked` selectors.
- **Two-page site** - `index.html` (landing) links to `galleria.html` (gallery). Navigation is one-directional.
- **Responsive design** - CSS media query breakpoint at 768px for mobile layout adjustments.
- **Color scheme** - Warm tones with `#d35400` accent color, dark overlays, white text over images.

## Key Conventions

- Images follow the naming pattern `img/foto{N}.jpg` (N = 1-14).
- Gallery slides are structured as radio-input-based carousel items in `galleria.html`.
- All styling lives in a single `style.css` file shared by both pages.
- External resources (fonts, icons) are loaded via CDN links in the HTML `<head>`.
- The project uses MIT license.

## Testing

No automated testing framework is configured. This is a static site with no application logic. Changes should be verified visually in the browser.

## Linting

ESLint is configured (`.eslintrc.json`) with `eslint:recommended` rules targeting a browser/ES2021 environment with Babel parser, though there are currently no JavaScript files in the project.
