# CLAUDE.md

This file provides guidance to Claude Code (claude.ai/code) when working with code in this repository.

## Project Overview

This is a modern Svelte 5 + TypeScript + Tailwind CSS template built with SvelteKit. It includes a complete, production-ready UI with four pages (Home, About, Services, Contact), responsive navigation, footer, and a blue-purple gradient design theme.

## Essential Commands

```bash
# Development
npm run dev                  # Start dev server (default: http://localhost:5173)

# Type Checking
npm run check                # Run svelte-check for type checking
npm run check:watch          # Run svelte-check in watch mode

# Build
npm run build                # Create production build in build/ folder
npm run preview              # Preview production build locally
```

## Architecture

### Tech Stack
- **Svelte 5.15** - Truly reactive framework with runes
- **SvelteKit 2.14** - Web development framework for building Svelte apps
- **TypeScript 5.7** - Static type checking with strict mode
- **Tailwind CSS 3.4** - Utility-first CSS framework
- **Vite 6** - Next-generation frontend build tool with HMR

### Application Structure
- Entry point: `src/app.html` → `src/routes/+layout.svelte` → page routes
- `+layout.svelte` contains the main layout structure with Header, Footer, and slot
- All routes defined using file-based routing in `src/routes/`
- Layout wraps all pages (Header + Footer remain across navigation)

### Routing Structure
SvelteKit uses file-based routing. Routes are defined by the directory structure:
- `/` - `src/routes/+page.svelte` (Home page)
- `/about` - `src/routes/about/+page.svelte` (About page)
- `/services` - `src/routes/services/+page.svelte` (Services page)
- `/contact` - `src/routes/contact/+page.svelte` (Contact page)

Each `+page.svelte` file represents a route. The `+layout.svelte` file wraps all routes.

### Component Organization
All components are Svelte Single File Components (.svelte):
- **Components**: `src/lib/components/` (Header.svelte, Footer.svelte)
- **Pages**: `src/routes/` (file-based routing)
- Each component uses `<script lang="ts">` for TypeScript support
- Template, script, and styles are co-located in .svelte files

**Layout Components:**
- `Header.svelte`: Sticky navigation with logo, nav links, mobile menu, active route highlighting
- `Footer.svelte`: Multi-column footer with brand info, quick links, resources, social icons

**Page Components:**
- `+page.svelte` (Home): Multi-section landing with hero, features, stats, CTAs
- `about/+page.svelte`: Mission statement, tech stack grid, values cards, team profiles
- `services/+page.svelte`: 6 service cards with icons, features, color-coded themes
- `contact/+page.svelte`: Two-column layout with contact info and functional form

### Design System
**Color Theme**: Blue-purple gradient (`from-blue-500/600 to-purple-600`)
- Primary gradient used in: buttons, logos, hero text, stats section
- Color-coded service cards: blue, purple, pink, green, indigo, yellow

**Dark Mode**: Tailwind dark mode classes throughout
- Uses `dark:` prefix for dark mode variants
- Applied to text, backgrounds, borders

**Responsive Design**: Mobile-first breakpoints
- Mobile menu toggle in Header for small screens
- Grid layouts adjust: `grid-cols-1 md:grid-cols-2 lg:grid-cols-3`
- Responsive spacing and typography

### TypeScript Configuration
- `tsconfig.json` - Extends `.svelte-kit/tsconfig.json` with strict mode
- TypeScript is fully integrated with Svelte components

### Styling Architecture
- `src/app.css` - Tailwind directives (@tailwind base/components/utilities) + global styles
- `tailwind.config.js` - Content paths for all source files
- `postcss.config.js` - Tailwind + Autoprefixer
- Component styles can be added in `<style>` blocks in .svelte files

### Adding New Routes
1. Create directory: `src/routes/[route-name]/`
2. Create page file: `src/routes/[route-name]/+page.svelte`
3. Add navigation link in `Header.svelte` navLinks array
4. Add footer link in `Footer.svelte` if needed

Example:
```bash
mkdir src/routes/pricing
touch src/routes/pricing/+page.svelte
```

### State Management
Svelte 5 uses runes for reactivity:
- `$state()` - Create reactive state
- `$derived()` - Create derived values
- `$effect()` - Run side effects
- `$props()` - Define component props

Example from Header:
```typescript
let isMenuOpen = $state(false);
```

Example from Contact form:
```typescript
let formData = $state({
  name: '',
  email: '',
  subject: '',
  message: ''
});
```

### Form Handling
Contact form (src/routes/contact/+page.svelte):
- Uses `bind:value` for two-way binding with reactive formData
- Form validation via HTML5 required attributes
- `onsubmit` handler prevents default, logs data, shows alert, resets form
- No backend integration - implement API call in handleSubmit as needed

### File Extensions
- `.svelte` - Svelte Single File Components
- `.ts` - TypeScript files
- `.js` - JavaScript config files (svelte.config.js, tailwind.config.js, etc.)
- `.css` - Stylesheets (app.css)
- `.json` - Package configuration (package.json, tsconfig.json)

## Svelte 5 Runes

Svelte 5 introduces runes for reactivity:

### $state
Creates reactive state:
```typescript
let count = $state(0);
let user = $state({ name: 'John', age: 30 });
```

### $derived
Creates derived reactive values:
```typescript
let doubled = $derived(count * 2);
```

### $effect
Runs side effects when dependencies change:
```typescript
$effect(() => {
  console.log('Count changed:', count);
});
```

### $props
Defines component props:
```typescript
let { title, description } = $props<{ title: string; description: string }>();
```

## SvelteKit Features

### Page Store
Access current page information:
```typescript
import { page } from '$app/stores';
// Use with $ prefix in script: $page.url.pathname
```

### Navigation
- Use `<a href="/path">` for client-side navigation
- SvelteKit automatically handles routing

### Layouts
- `+layout.svelte` - Wraps all routes
- Can nest layouts in subdirectories
- Use `<slot />` to render child content
