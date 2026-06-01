# Simple Games Web

A high-end, modern static website for Simple Games indie mobile applications. Built with clean HTML, organized CSS, and a professional folder structure.

## 📂 Project Structure

```
simple-games-web/
├── public/                          # Served files
│   ├── index.html                   # Landing page
│   ├── pages/
│   │   └── privacy/
│   │       ├── sudoku.html
│   │       └── spider.html
│   └── assets/
│       └── images/
│           └── games/
│               ├── spider/          # Spider game assets
│               └── sudoku/          # Sudoku game assets
├── src/
│   ├── styles/
│   │   ├── main.css                 # Main landing page styles
│   │   ├── privacy.css              # Privacy page styles
│   │   └── globals.css              # Global utilities
│   └── components/                  # Shared component templates
├── package.json                     # Project metadata
├── README.md                        # This file
└── .gitignore
```

## 🎯 Key Features

- **Mobile-first design** — Responsive, works on all devices
- **Fast load times** — Pure HTML/CSS, no unnecessary frameworks
- **Organized structure** — Clean separation of concerns
- **Accessibility** — Semantic HTML, proper contrast
- **Asset management** — Organized game image directories
- **Privacy-first** — Transparent privacy policies

## 🚀 Getting Started

### Local Development

Serve the website locally with a simple HTTP server:

```bash
npm start
```

Or open with a specific port:

```bash
npx http-server public -p 8000
```

Then visit: `http://localhost:8000`

### Manual Setup

If you prefer to serve without npm:

**macOS/Linux:**
```bash
cd public
python3 -m http.server 8000
```

**Windows (Python):**
```bash
cd public
python -m http.server 8000
```

**macOS (Ruby):**
```bash
cd public
ruby -run -ehttpd . -p8000
```

## 📝 File Conventions

### HTML Files
- All served HTML is in `/public`
- Use semantic HTML5
- Include meta tags for SEO and social sharing
- Link to external stylesheets in `/src/styles`

### CSS Files
- `/src/styles/main.css` — Landing page + all main components
- `/src/styles/privacy.css` — Privacy policy pages
- `/src/styles/globals.css` — Global utilities and resets

### Assets
- Game images in `/public/assets/images/games/[game-name]/`
- Use descriptive filenames
- Optimize images for web (compress PNGs, use WebP where applicable)

## 🔗 Navigation

| Page | Path | Purpose |
|------|------|---------|
| Landing | `/index.html` | Main website homepage |
| Sudoku Privacy | `/pages/privacy/sudoku.html` | Sudoku privacy policy |
| Spider Privacy | `/pages/privacy/spider.html` | Spider privacy policy |

## ✏️ Maintenance

### Adding a New Page

1. Create HTML file in appropriate directory under `/public`
2. Link stylesheet from `/src/styles`
3. Update navigation links across all pages
4. Test links locally

### Updating Styles

- Global styles: Edit `/src/styles/globals.css`
- Page-specific: Edit relevant stylesheet
- Always test responsive design on mobile

### Adding Game Assets

1. Place images in `/public/assets/images/games/[game-name]/`
2. Update `src` attributes in HTML
3. Optimize images before committing

## 🎨 Design System

### Color Palette (Landing)
- Primary: `#1a73e8` (Blue)
- Background: `#ffffff` → `#f1f3f4` (Gradient)
- Text: `#202124` (Dark Gray)
- Borders: `#dadce0` (Light Gray)

### Color Palette (Privacy)
- Primary: `#7c5cfc` (Purple)
- Background: `#0f0f13` (Dark)
- Text: `#e8e8f0` (Light Gray)
- Borders: `#2e2e3e` (Dark Gray)

### Typography
- Headers: Google Sans / Inter
- Body: Inter
- Fallback: System fonts

### Spacing
- Border radius: `12px` (main), `8px` (buttons)
- Gaps: `0.5rem` to `2rem` (incremental)

## 📱 Responsive Breakpoints

- Mobile: < 640px (single column, stacked layout)
- Tablet: 640px - 1024px
- Desktop: > 1024px (full multi-column)

## 🔍 Performance Tips

- Use `preconnect` for Google Fonts
- Lazy-load game screenshots if many
- Compress images (ImageOptim, TinyPNG)
- Test Core Web Vitals

## 📄 License

MIT — See LICENSE file

## ✉️ Contact

Support: [simplegames.dev@gmail.com](mailto:simplegames.dev@gmail.com)
