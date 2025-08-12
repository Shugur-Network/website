# Shugur Relay Website

Official website for Shugur Relay - a production-ready Nostr relay built with Go and CockroachDB for enterprise-grade reliability and performance.

## 🌐 Live Website

**Production**: [https://shugur-network.github.io/Relay-Website/](https://shugur-network.github.io/Relay-Website/)

## 🚀 About Shugur Relay

Shugur Relay is a high-performance Nostr relay designed for production environments. It enables censorship-resistant social networks with enterprise features like monitoring, analytics, and managed scaling.

### Key Features
- **Production-Ready**: Built for enterprise-grade reliability
- **High Performance**: Optimized for thousands of concurrent connections
- **Go & CockroachDB**: Robust technology stack for scalability
- **Enterprise Features**: Monitoring, analytics, and managed scaling
- **Quick Deployment**: Ready in 10 minutes

## 🛠️ Technology Stack

- **Framework**: [SvelteKit](https://kit.svelte.dev/) with TypeScript
- **Styling**: [Tailwind CSS](https://tailwindcss.com/) for responsive design
- **Icons**: [Lucide Svelte](https://lucide.dev/) for beautiful iconography
- **Fonts**: League Spartan for Shugur branding
- **Deployment**: Netlify with automatic builds
- **Static Generation**: Pre-rendered for optimal performance

## 📖 Documentation

- **Main Documentation**: [docs.relay.shugur.com](https://docs.relay.shugur.com)
- **Installation Guide**: [docs.relay.shugur.com/installation](https://docs.relay.shugur.com/installation)
- **Getting Started**: [docs.relay.shugur.com/getting-started](https://docs.relay.shugur.com/getting-started)
- **Architecture**: [docs.relay.shugur.com/architecture](https://docs.relay.shugur.com/architecture)

## 🏃 Quick Start

```bash
# Clone the repository
git clone https://github.com/Shugur-Network/Relay-Website.git
cd Relay-Website

# Install dependencies
npm install

# Start development server
npm run dev

# Open http://localhost:5173 in your browser
```

## 📦 Available Scripts

```bash
# Development
npm run dev              # Start dev server with hot reload
npm run dev -- --host    # Expose dev server to network

# Building
npm run build            # Build for production
npm run preview          # Preview production build locally

# Code Quality
npm run check            # Run Svelte type checking
npm run check:watch      # Watch mode for type checking
npm run lint             # Run ESLint
npm run format           # Format code with Prettier
```

## 📁 Project Structure

```
src/
├── routes/                    # SvelteKit routes
│   ├── +layout.svelte        # Global layout with navigation
│   ├── +layout.ts            # Layout configuration (prerender)
│   ├── +page.svelte          # Homepage
│   └── about-nostr/          
│       └── +page.svelte      # About Nostr detailed page
├── lib/
│   └── components/           # Reusable Svelte components
│       ├── Navigation.svelte # Header with logo and navigation
│       ├── Hero.svelte       # Landing hero section
│       ├── Features.svelte   # Key features showcase
│       ├── Installation.svelte # Installation instructions
│       ├── Architecture.svelte # Technical overview
│       └── Footer.svelte     # Site footer
├── app.html                  # HTML template with fonts
├── app.css                   # Global styles and logo CSS
└── ...
static/
├── favicon.ico              # Site favicon
└── shugur-logo.svg          # Shugur brand logo
```

## 🎨 Design System

### Brand Colors
- **Primary**: `#36BA98` (Shugur Green)
- **Dark**: `#1A1A1A` (Text)
- **Light**: `#FAFAFA` (Background)

### Typography
- **Primary Font**: League Spartan (Brand)
- **Body Font**: System fonts via Tailwind CSS

### Components
- **Navigation**: Responsive header with Shugur branding
- **Hero**: Call-to-action with Quick Start and Documentation links
- **Features**: Grid layout showcasing relay capabilities
- **Installation**: Code snippets with copy functionality
- **Architecture**: Technical benefits and implementation details
- **Footer**: Minimal footer with copyright and GitHub link

## 🚀 Deployment

### Automatic Deployment
- **Platform**: Netlify
- **Trigger**: Push to `main` branch
- **Build Command**: `npm run build`
- **Publish Directory**: `build`
- **Base Path**: `/Relay-Website/` (configured for subdirectory deployment)

### Configuration
The site is configured for deployment to a subdirectory path:
- **Production Base**: `/Relay-Website/`
- **Assets Path**: Configured for proper static asset resolution
- **Prerendering**: Enabled for optimal SEO and performance

### Manual Deployment
```bash
# Build the site
npm run build

# The 'build' directory contains the static site
# Upload to any static hosting provider
```

**Supported Platforms:**
- ✅ Netlify (current)
- ✅ Vercel
- ✅ GitHub Pages
- ✅ Cloudflare Pages
- ✅ Any static hosting provider

## 🔗 Related Links

- **Main Relay Repository**: [Shugur-Network/Relay](https://github.com/Shugur-Network/Relay)
- **Company Website**: [shugur.com](https://shugur.com)
- **Documentation Site**: [docs.relay.shugur.com](https://docs.relay.shugur.com)

## 🤝 Contributing

1. **Fork** the repository
2. **Create** a feature branch: `git checkout -b feature/amazing-feature`
3. **Make** your changes
4. **Test** locally: `npm run dev`
5. **Build** to verify: `npm run build`
6. **Commit** your changes: `git commit -m 'Add amazing feature'`
7. **Push** to the branch: `git push origin feature/amazing-feature`
8. **Submit** a pull request

### Development Guidelines
- Use TypeScript for type safety
- Follow existing component patterns
- Ensure responsive design (mobile-first)
- Test on multiple screen sizes
- Maintain consistent branding

## 📄 License

This project is part of the Shugur Network ecosystem. See the main [Relay repository](https://github.com/Shugur-Network/Relay) for license information.

## 🆘 Support

- **Issues**: [GitHub Issues](https://github.com/Shugur-Network/Relay-Website/issues)
- **Documentation**: [docs.relay.shugur.com](https://docs.relay.shugur.com)
- **Main Project**: [Shugur-Network/Relay](https://github.com/Shugur-Network/Relay)

---

Built with ❤️ by Shugur team for the decentralized web.
