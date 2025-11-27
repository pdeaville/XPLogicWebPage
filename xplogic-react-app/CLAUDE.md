# CLAUDE.md

This file provides guidance to Claude Code (claude.ai/code) when working with code in this repository.

## Project Overview

This is a React application built with Vite, targeting modern browsers with HMR (Hot Module Replacement) support. The project uses React 19 and follows a standard Vite + React setup with Babel for Fast Refresh.

## Development Commands

- **Start dev server**: `npm run dev` - Starts Vite dev server with HMR
- **Build for production**: `npm run build` - Creates optimized production build in `dist/`
- **Lint code**: `npm run lint` - Runs ESLint on all files
- **Preview production build**: `npm run preview` - Serves the production build locally

## Project Structure

```
src/
  assets/        # Static assets (images, etc.)
  App.jsx        # Main App component
  main.jsx       # React entry point, renders App into #root
  index.css      # Global styles
  App.css        # App component styles
public/          # Public static files served at root
index.html       # HTML entry point, loads /src/main.jsx
```

## Architecture Notes

- **Entry Point**: `index.html` loads `src/main.jsx` as a module, which renders the `App` component into the `#root` div using React 19's `createRoot`.
- **Build Tool**: Vite handles bundling, dev server, and HMR through `@vitejs/plugin-react` with Babel.
- **Styling**: Component-level CSS files imported directly into components.

## Code Standards

- **ESLint Configuration**: Uses flat config format (`eslint.config.js`) with:
  - Recommended JS rules
  - React Hooks plugin (recommended rules)
  - React Refresh plugin for Vite
  - Custom rule: Unused vars allowed if they start with uppercase or underscore (pattern: `^[A-Z_]`)
  - Target: ES2020, browser globals
- **File Extensions**: `.jsx` for React components
- **Module System**: ES modules (`type: "module"` in package.json)
