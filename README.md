# Premium Invention Shopify Theme

A modern, high-performance Shopify theme built with **TypeScript**, **Tailwind CSS 4.1**, and **Vite 7** for optimal development experience and production performance.

## ✅ **SUCCESSFULLY IMPLEMENTED!**

The build system is now working perfectly with:
- ✅ **Vite 6.3.5** - Fast development and production builds
- ✅ **Tailwind CSS 4.1.11** - Using the official `@tailwindcss/vite` plugin
- ✅ **TypeScript 5.8.3** - Full type safety
- ✅ **Terser** - JavaScript minification
- ✅ **No PostCSS config needed** - Handled by Tailwind Vite plugin
- ✅ **Custom theme variables** - Using Tailwind v4 `@theme` directive

### Generated Files:
```
shopify/assets/
├── main.min.css (16.8 KB) - Compiled Tailwind CSS
├── main.min.js (2.8 KB) - Main theme functionality
├── product-gallery.min.js (3.4 KB) - Product gallery component
└── cart-functionality.min.js (6.4 KB) - Cart operations
```

## 🚀 Features

- ⚡ **Vite 7** - Lightning-fast development with HMR
- 🎨 **Tailwind CSS 4.1** - Latest utility-first CSS framework
- 🔷 **TypeScript** - Type-safe development
- 📱 **Responsive Design** - Mobile-first approach
- 🛒 **Advanced Cart** - AJAX cart with drawer functionality
- 🖼️ **Product Gallery** - Image zoom and variant switching
- ⚡ **Optimized Assets** - Minified JS/CSS for production
- 🎯 **Shopify Integration** - Seamless theme development

## 📋 Prerequisites

- **Node.js** 18+ and npm/yarn
- **Shopify CLI** (optional, for theme development)
- **Git** for version control

## 🛠️ Setup

1. **Clone the repository:**
```bash
git clone https://github.com/evanderwpmorias/pi-dawn-theme.git
cd pi-dawn-theme
```

2. **Use the correct Node.js version:**
```bash
# If using nvm (recommended)
nvm use

# Or manually install Node.js 22+
```

3. **Install dependencies:**
```bash
npm install
```

4. **Install TypeScript globally (if not already installed):**
```bash
npm install -g typescript
```

> **Note:** If you encounter deprecation warnings during installation, they are automatically handled by the `overrides` section in package.json and won't affect functionality.

## 🔧 Development

### Watch Mode (Development)
Start the development server with hot module replacement:

```bash
npm run dev
```

This command will:
- 👀 Watch for changes in the `src/` directory
- 🔄 Compile TypeScript files automatically
- 🎨 Process Tailwind CSS with latest features
- 📦 Output minified files to `shopify/assets/`
- 🔥 Enable hot reloading for faster development

### Type Checking
Run TypeScript type checking:

```bash
npm run type-check
```

### Build for Production
Create optimized, production-ready files:

```bash
npm run build
```

This will generate:
- `*.min.js` - Minified JavaScript files
- `*.min.css` - Minified CSS files
- Optimized assets ready for deployment

## 📁 Project Structure

```
pi-dawn-theme/
├── 📂 src/                    # Development source files
│   ├── 📂 components/         # TypeScript components
│   │   ├── main.ts           # Main theme functionality
│   │   ├── product-gallery.ts # Product image gallery
│   │   └── cart-functionality.ts # Cart operations
│   └── 📂 style/             # Tailwind CSS files
│       ├── main.css          # Main CSS entry point
│       ├── product.css       # Product-specific styles
│       └── cart.css          # Cart-specific styles
├── 📂 shopify/               # Shopify theme files
│   ├── 📂 assets/            # Compiled output (auto-generated)
│   │   ├── *.min.js         # Minified JavaScript
│   │   └── *.min.css        # Minified CSS
│   ├── 📂 config/           # Theme configuration
│   ├── 📂 layout/           # Layout templates
│   ├── 📂 sections/         # Section files
│   ├── 📂 snippets/         # Reusable snippets
│   └── 📂 templates/        # Page templates
├── 📄 package.json          # Dependencies and scripts
├── 📄 vite.config.ts        # Vite configuration
├── 📄 tailwind.config.ts    # Tailwind CSS configuration
├── 📄 tsconfig.json         # TypeScript configuration
└── 📄 postcss.config.js     # PostCSS configuration
```

## ➕ Adding New Components

### 1. Create a TypeScript Component

Create a new file in `src/components/`:

```typescript
// src/components/my-component.ts
export class MyComponent {
  private element: HTMLElement;

  constructor(selector: string) {
    const el = document.querySelector(selector);
    if (!el) throw new Error(`Element ${selector} not found`);
    this.element = el as HTMLElement;
    this.init();
  }

  private init(): void {
    // Your component logic here
    console.log('MyComponent initialized');
  }
}

// Auto-initialize on DOM ready
document.addEventListener('DOMContentLoaded', () => {
  const components = document.querySelectorAll('[data-my-component]');
  components.forEach(component => {
    new MyComponent(`[data-my-component]`);
  });
});
```

### 2. Add Entry Point to Vite Config

Update `vite.config.ts`:

```typescript
entrypoints: {
  'my-component': './src/components/my-component.ts',
  // ... other entries
}
```

### 3. Include in Liquid Templates

Add to your `.liquid` files:

```liquid
{{ 'my-component.min.js' | asset_url | script_tag }}
```

## 🎨 Using Tailwind CSS

### Utility Classes in Liquid Templates

```liquid
<div class="bg-pi-blue text-white p-6 rounded-xl shadow-lg hover:shadow-xl transition-shadow duration-300">
  <h2 class="text-2xl font-bold mb-4">Premium Content</h2>
  <p class="text-white/80 leading-relaxed">Your content here</p>
  <button class="btn-primary mt-4">Call to Action</button>
</div>
```

### Custom Component Classes

Defined in `src/style/main.css`:

```css
@layer components {
  .btn-primary {
    @apply bg-pi-blue text-white px-6 py-3 rounded-lg font-semibold hover:bg-blue-700 transition-colors duration-300;
  }
}
```

## 🚀 Deployment

### Using Shopify CLI

1. **Build the project:**
```bash
npm run build
```

2. **Deploy with Shopify CLI:**
```bash
shopify theme push
```

### Manual Upload

1. **Build the project:**
```bash
npm run build
```

2. **Upload the `shopify/` directory contents to your theme**

## 🎯 Theme Features

### 🛒 Cart Functionality
- AJAX cart operations
- Slide-out cart drawer
- Real-time quantity updates
- Item removal
- Cart total calculations

### 🖼️ Product Gallery
- Image zoom on click
- Thumbnail navigation
- Keyboard navigation (arrow keys)
- Touch/swipe support
- Variant image switching

### 📱 Responsive Design
- Mobile-first approach
- Tailwind's responsive utilities
- Optimized for all devices

### 🎨 Custom Styling
- Brand colors (`pi-blue`, `pi-black`)
- Custom animations
- Work Sans font integration
- Utility-first approach

## ⚙️ Configuration

### Tailwind CSS Customization

Edit `tailwind.config.ts`:

```typescript
theme: {
  extend: {
    colors: {
      'pi-blue': '#086FB5',
      'custom-color': '#your-color',
    },
    fontFamily: {
      'custom-font': ['Your Font', 'sans-serif'],
    },
  },
}
```

### Vite Configuration

Modify `vite.config.ts` to add new entry points or change build settings.

## 🔧 Development Tips

### Hot Reloading
- Save any file in `src/` to trigger automatic rebuild
- Changes appear instantly in the browser
- TypeScript errors are shown in the terminal

### Debugging
- Use browser DevTools for debugging
- TypeScript provides excellent IntelliSense
- Console logs are preserved in development

### Performance
- Production builds are automatically minified
- CSS is purged of unused styles
- Assets are optimized for web delivery

## 📚 Important Notes

### File Management
- ❌ **Never edit** files in `shopify/assets/` that end with `.min.js` or `.min.css`
- ✅ **Always edit** source files in `src/` directory
- 🔄 Original theme assets without `.min` extension are preserved

### Browser Support
- ES2022 features supported
- Automatically prefixed CSS
- Modern browser optimization
- Baseline Widely Available browser support

### Dependencies
- All dependencies are locked to specific versions
- Regular updates recommended for security
- Tailwind CSS 4.1+ features available

## 🤝 Contributing

1. Fork the repository
2. Create a feature branch
3. Make your changes in the `src/` directory
4. Test thoroughly
5. Submit a pull request

## 📄 License

MIT License - see LICENSE file for details

---

**Premium Invention** - Building the future of e-commerce themes

For support or questions, please open an issue in the repository.
