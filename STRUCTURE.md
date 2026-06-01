# Project Structure Documentation

## High-End Web Structure Overview

This document describes the refactored directory layout and organization of the Simple Games web project.

## Directory Tree

```
simple-games-web/
│
├── 📁 public/                       ✨ SERVED FILES (root for web server)
│   ├── index.html                   → Landing page (entry point)
│   ├── 📁 pages/
│   │   └── 📁 privacy/
│   │       ├── sudoku.html          → Sudoku privacy policy
│   │       └── spider.html          → Spider privacy policy
│   │
│   └── 📁 assets/
│       └── 📁 images/
│           └── 📁 games/
│               ├── 📁 spider/       → Spider game assets
│               │   ├── icon.png
│               │   ├── screenshot-1.png
│               │   ├── screenshot-2.png
│               │   └── screenshot-3.png
│               │
│               └── 📁 sudoku/       → Sudoku game assets
│                   ├── icon.jpeg
│                   ├── screenshot-1.png
│                   ├── screenshot-2.png
│                   ├── screenshot-3.png
│                   ├── screenshot-4.png
│                   └── screenshot-5.png
│
├── 📁 src/                          ✨ SOURCE FILES (not served directly)
│   ├── 📁 styles/
│   │   ├── main.css                 → Landing page + main components
│   │   ├── privacy.css              → Privacy policy pages
│   │   └── globals.css              → Global utilities & resets
│   │
│   └── 📁 components/
│       └── TEMPLATE.html            → Component template for new pages
│
├── 📄 Configuration Files
│   ├── package.json                 → Project metadata & npm scripts
│   ├── README.md                    → Project documentation
│   ├── .gitignore                   → Git exclude patterns
│   └── STRUCTURE.md                 → This file
│
└── 📁 .git/                         → Git repository
```

## Rationale

### `/public` — Web Server Root
- **Purpose:** Contains all files served to users
- **Why:** Clean separation; web server points here
- **Benefits:** Prevents accidental exposure of source files

### `/src` — Source Files
- **Purpose:** Development files (stylesheets, templates)
- **Why:** Keeps source organized and separate from served content
- **Benefits:** Room for future build tools, preprocessors

### `/src/styles` — Stylesheet Organization
- **`main.css`** — Landing page, game cards, navigation, footer
- **`privacy.css`** — Privacy policy pages styling
- **`globals.css`** — Utilities, resets, accessibility helpers

**Note:** Stylesheets are linked from HTML with relative paths:
```html
<link rel="stylesheet" href="../src/styles/main.css">
```

### `/public/assets/images/games` — Asset Organization
- **By game:** Easy to find and manage assets per game
- **Scalable:** Easy to add new games
- **Clean:** All images grouped by type

### `/public/pages` — Page Organization
- **By category:** Privacy, blog, docs, etc.
- **Logical:** Mirrors site information architecture
- **Maintainable:** Easy to add new sections

## File Paths

### From Landing Page (`/public/index.html`)
```html
<!-- Relative paths within public/ -->
<img src="../public/assets/images/games/sudoku/icon.jpeg">
<a href="./pages/privacy/sudoku.html">Privacy Policy</a>
```

### From Privacy Page (`/public/pages/privacy/sudoku.html`)
```html
<!-- Navigate back two levels to public/, then to assets/ -->
<img src="../../assets/images/games/sudoku/icon.jpeg">

<!-- Navigate back to root for stylesheet -->
<link rel="stylesheet" href="../../../src/styles/privacy.css">

<!-- Navigate back two levels to public/ for home link -->
<a href="../../index.html">← Back to Simple Games</a>
```

## Best Practices

### Adding a New Page
1. Create HTML file in appropriate `/public/pages/[category]/` folder
2. Link stylesheets from `/src/styles`
3. Use semantic HTML5
4. Test responsive design

### Adding New Assets
1. Place in `/public/assets/images/games/[game-name]/`
2. Update image paths in HTML
3. Optimize images before commit
4. Use descriptive filenames

### Styling New Components
1. Add to existing stylesheet or create game-specific CSS
2. Use CSS custom properties (variables)
3. Follow mobile-first approach
4. Test across breakpoints

### Adding a New Game
1. Create game folder: `/public/assets/images/games/[name]/`
2. Add icon and screenshots
3. Create privacy policy: `/public/pages/privacy/[name].html`
4. Update landing page with game card
5. Update navigation/footer links

## Deployment

### For Static Hosting (GitHub Pages, Netlify, Vercel)
1. Set public root to `/public`
2. No build step needed
3. Deploy and visit: `your-domain.com`

### Local Testing
```bash
cd public
python3 -m http.server 8000
# Visit http://localhost:8000
```

## Future Enhancements

Possible additions to this structure:
- `/docs` — Blog posts, guides, changelogs
- `/api` — Mock API responses (if adding interactivity)
- `/scripts` — Utility JavaScript functions
- `build/` — Build output from potential preprocessors
- `.github/workflows/` — CI/CD automation

## Maintenance Checklist

- [ ] Update links when adding/removing pages
- [ ] Test responsive design after layout changes
- [ ] Optimize images before pushing
- [ ] Keep README.md current with new features
- [ ] Use semantic HTML for accessibility
- [ ] Test on actual mobile devices regularly
