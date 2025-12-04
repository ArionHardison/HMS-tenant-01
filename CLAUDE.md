# CLAUDE.md

This file provides guidance to Claude Code (claude.ai/code) when working with code in this repository.

## Build Commands

```bash
npm run serve    # Start dev server with hot reload
npm run build    # Production build to dist/
```

## Architecture

**Vue 2.6** application using Vue CLI 4 with:
- **Vuex 3** for state management (modal visibility states in `src/store.js`)
- **Vue Router 3** with history mode (`src/router.js`)
- **Bootstrap Vue** + custom SCSS for UI
- **vue-meta** for page meta tags

### Entry Flow
`src/index.js` → imports styles and `main.js` → initializes Vue with plugins → mounts `App.vue` → renders `<router-view>`

### Directory Structure
- `src/views/` - Page components (8 pages: index, about-us, service-inside, news, news-single-post, search-results, ui, 404)
- `src/blocks/` - Page-specific section components composed into views
- `src/components/` - Reusable UI components (Button, Forms, Modal, Loading)
- `src/assets/sass/` - SCSS stylesheets with `style.scss` as entry point
- `src/data/` - Static JSON data files

### Vue Config (`vue.config.js`)
- Entry: `src/index.js`
- CopyWebpackPlugin copies fonts, icons, images from `src/assets/` to `dist/assets/`
- Production source maps disabled
- History mode routing (requires server-side fallback to index.html)

## Deployment

**Heroku**: Uses express static server (`server.js`) to serve the built Vue SPA with history mode routing support.

```bash
git push heroku main    # Deploy to Heroku
```

- `heroku-postbuild` script runs `npm run build` automatically
- `start` script runs `node server.js` to serve `dist/`
- Ensure `package.json` does not contain `extract-text-webpack-plugin` (conflicts with webpack 5)
- Node.js 18.x LTS required (specified in `engines`)
