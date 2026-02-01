# CodeChanges6 - Project Guidelines

## Project Description

A fun "Mars Attacks!" themed React web application featuring interactive particle systems, multi-language support (English/Russian), multiple pages (Home, HTML Elements Demo, Interactive Components), and SCSS styling with a Martian theme.

## Technology Stack

- **Frontend Framework**: React 19.x with JSX
- **Build Tool**: Vite 7.x
- **Styling**: SCSS (Sass) with CSS
- **Languages**: JavaScript (ESM modules)

## Main Application Services

| Service | Description | Port |
|---------|-------------|------|
| Vite Dev Server | Development server serving the React application | 3000 |

## Key Dependencies

### Runtime Dependencies
- `react` & `react-dom` - React framework (v19.x)
- `axios` - HTTP client
- `clsx` - CSS class utility for conditional classes
- `date-fns` - Date formatting library
- `lodash` - Utility library

### Development Dependencies
- `vite` - Build tool and dev server
- `sass` - SCSS preprocessor
- `vite-plugin-inspect` - Vite development plugin
- `@vitejs/plugin-react` - React plugin for Vite

## Build and Run Instructions

**Important**: This project MUST use `npm ci` instead of `npm install` for reproducible builds.

```bash
# Install dependencies (REQUIRED: use npm ci)
npm ci

# Start development server
npm run dev
```

## Key Configuration Files

| File | Purpose |
|------|---------|
| `vite.config.js` | Vite configuration with React plugin and inspect plugin, dev server on port 3000 |
| `package.json` | Project dependencies and scripts |
| `src/styles.scss` | SCSS variables and mixins for Martian theme |

## Project Structure

```
src/
├── App.jsx          # Main application component with all pages
├── App.css          # Application styles
├── styles.scss      # SCSS variables and theme styles
├── main.jsx         # React entry point
├── index.css        # Global styles
└── assets/          # Static assets (images, SVGs)
```

## UI Components and Patterns

### Theme Variables (SCSS)
```scss
$mars-red: #ff0000;
$mars-green: #00ff00;
$dark-bg: #1a1a1a;
$border-radius: 8px;
```

### Glow Mixin
```scss
@mixin glow($color) {
  box-shadow: 0 0 10px $color, 0 0 20px $color;
}
```

### Key CSS Classes
- `.mars-glow` - Red glow effect with green hover
- `.feature-card` - Dark background card with icon, title, description
- `.hero` - Hero section with animated background
- `.particle-system` - Animated floating particles
- `.floating-shapes` - Geometric shape animations

### Multi-language Support
The app uses a `translations` object with `EN` and `RU` keys. Access translations via:
```jsx
const t = translations[lang];
// Use: t.heroTitle, t.heroSubtitle, etc.
```

### Navigation Pattern
Uses React state for page routing:
```jsx
const [currentPage, setCurrentPage] = useState('home');
// Pages: 'home', 'html-elements', 'interactive-components'
```

### Button Styles
- `.btn.btn-primary` - Primary action button
- `.btn.btn-secondary` - Secondary action button
- `.hero-cta` - Call-to-action button
- `.nav-btn` - Navigation button

## Available Scripts

- `npm run dev` - Start development server (port 3000)
- `npm run build` - Build for production
- `npm run preview` - Preview production build
- `npm run lint` - Run ESLint