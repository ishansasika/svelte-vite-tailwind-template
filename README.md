# SvelteKit Template

A modern, lightning-fast Svelte template built with SvelteKit, TypeScript, and Tailwind CSS. Perfect for building your next web application with a beautiful blue-purple gradient design theme.

## Features

- 🟠 **Svelte 5** - Truly reactive framework with runes
- 🚀 **SvelteKit** - Web development framework for Svelte
- 📘 **TypeScript** - Type safety and enhanced developer experience
- 🎨 **Tailwind CSS** - Utility-first CSS framework
- 🌙 **Dark Mode** - Built-in dark mode support
- 📱 **Responsive** - Mobile-first responsive design
- ⚡ **Vite** - Next-generation frontend tooling
- 🎯 **Production Ready** - Optimized build configuration

## Project Structure

```
svelte-vite-tailwind-template/
├── src/
│   ├── lib/
│   │   └── components/   # Reusable components (Header, Footer)
│   ├── routes/           # File-based routing
│   │   ├── about/        # About page
│   │   ├── services/     # Services page
│   │   ├── contact/      # Contact page
│   │   ├── +layout.svelte  # Root layout
│   │   └── +page.svelte    # Home page
│   ├── app.css           # Global styles with Tailwind directives
│   └── app.html          # HTML template
├── static/               # Static assets
└── svelte.config.js      # SvelteKit configuration
```

## Getting Started

### Prerequisites

- Node.js 18+ and npm

### Installation

1. Clone the repository:
```bash
git clone https://github.com/ishansasika/svelte-vite-tailwind-template.git
cd svelte-vite-tailwind-template
```

2. Install dependencies:
```bash
npm install
```

3. Start the development server:
```bash
npm run dev
```

4. Open your browser and navigate to `http://localhost:5173`

## Available Scripts

- `npm run dev` - Start development server
- `npm run build` - Build for production
- `npm run preview` - Preview production build
- `npm run check` - Run svelte-check for type checking
- `npm run check:watch` - Run svelte-check in watch mode

## Pages

- **Home** - Landing page with hero, features, stats, and CTA sections
- **About** - Mission, tech stack, values, and team information
- **Services** - Service offerings with color-coded cards
- **Contact** - Contact form and information

## Customization

### Colors

The template uses a blue-purple gradient theme. To customize the colors, modify the Tailwind classes in the components:

- Primary gradient: `from-blue-600 to-purple-600`
- Background gradients: `from-blue-50 to-purple-50`

### Logo

Update the logo letter in `Header.svelte` and `Footer.svelte`:
```svelte
<span class="text-white font-bold text-xl">S</span>
```

### Branding

Replace "SvelteKit" with your brand name in:
- `src/lib/components/Header.svelte`
- `src/lib/components/Footer.svelte`
- `src/routes/+layout.svelte` (title tag)

## Technologies

- [Svelte 5](https://svelte.dev/) - Truly reactive framework
- [SvelteKit](https://kit.svelte.dev/) - Web development framework
- [TypeScript](https://www.typescriptlang.org/) - Typed superset of JavaScript
- [Tailwind CSS](https://tailwindcss.com/) - Utility-first CSS framework
- [Vite](https://vitejs.dev/) - Next generation frontend tooling

## License

MIT License - feel free to use this template for your projects!

## Author

Created with ❤️ by [Ishan Sasika](https://github.com/ishansasika)
