# Shugur Relay Website

This is the official website for Shugur Relay, built with SvelteKit and Tailwind CSS.

## 🌐 Live Website

The website is automatically deployed to GitHub Pages: **https://shugur-network.github.io/Relay-Website/**

## Getting Started

```bash
# Install dependencies
npm install

# Run development server
npm run dev

# Build for production
npm run build

# Preview production build
npm run preview
```

## Features

- **SvelteKit**: Modern framework with excellent performance
- **TypeScript**: Type safety and better developer experience
- **Tailwind CSS**: Utility-first CSS framework
- **Lucide Icons**: Beautiful, customizable icons
- **Responsive Design**: Mobile-first approach
- **SEO Optimized**: Meta tags and semantic HTML
- **GitHub Pages Deployment**: Automatic deployment on push to main

## Project Structure

```
src/
├── routes/              # SvelteKit routes
│   ├── +layout.svelte   # Main layout
│   ├── +layout.ts       # Layout configuration
│   ├── +page.svelte     # Homepage
│   └── about-nostr/     # About Nostr page
├── lib/
│   └── components/      # Reusable Svelte components
├── app.html            # HTML template
├── app.css             # Global styles
└── ...
```

## Components

- **Navigation**: Responsive navigation with mobile menu
- **Hero**: Landing page hero section with call-to-action
- **Features**: Grid showcasing key features and benefits
- **Installation**: Copy-paste installation commands
- **Architecture**: Technical overview and benefits
- **Footer**: Simple footer with links

## Deployment

This website is automatically deployed to GitHub Pages using GitHub Actions. Any push to the `main` branch triggers a new deployment.

### Manual Deployment

For other hosting providers:

```bash
npm run build
# Upload the 'build' directory to your hosting provider
```

Supported platforms:
- GitHub Pages (current)
- Vercel
- Netlify
- Cloudflare Pages
- Any static hosting provider

## Contributing

1. Fork the repository
2. Create a feature branch
3. Make your changes
4. Test locally with `npm run dev`
5. Submit a pull request

## Related Projects

- **Main Relay**: [Shugur-Network/Relay](https://github.com/Shugur-Network/Relay)
- **Documentation**: Available in the main relay repository
