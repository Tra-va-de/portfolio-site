# Portfolio Website

A modern, responsive portfolio website with PWA (Progressive Web App) support.

## Features

- **Responsive Design** - looks great on all devices
- **PWA Support** - can be installed as an app
- **Modular Structure** - easy to maintain and extend
- **SEO Optimized** - ready for search engines
- **Fast Loading** - optimized resources

## Project Structure

```
portfolio-site/
├── index.html              # Main page
├── manifest.json           # PWA manifest
├── README.md              # Documentation
├── src/
│   ├── css/
│   │   ├── main.css       # Main CSS file
│   │   ├── base.css       # Base styles
│   │   ├── hero.css       # Hero section styles
│   │   ├── sections.css   # Section styles
│   │   └── components.css # Component styles
│   ├── js/
│   │   ├── main.js        # Main JavaScript
│   │   └── service-worker.js # Service Worker
│   └── images/            # Images
├── assets/
│   ├── fonts/             # Fonts
│   └── icons/             # Icons
└── docs/                  # Documentation
```

## Technologies

- **HTML5** - semantic markup
- **CSS3** - modern styles with Flexbox and Grid
- **JavaScript (ES6+)** - interactivity
- **PWA** - Service Worker and Web App Manifest
- **Font Awesome** - icons

## Quick Start

1. **Clone the repository:**
   ```bash
   git clone <your-repo-url>
   cd portfolio-site
   ```

2. **Open in browser:**
   - Simply open `index.html` in your browser
   - Or use a local server:
   ```bash
   # Python 3
   python -m http.server 8000
   
   # Node.js
   npx serve .
   ```

3. **Customize for yourself:**
   - Edit `index.html` - replace content
   - Update `manifest.json` - change name and icons
   - Add your images to `src/images/`

## Configuration

### Content Changes

1. **Personal Information:**
   - Open `index.html`
   - Replace "Your Name" with your name
   - Update description and contact information

2. **Projects:**
   - Replace images in `src/images/`
   - Update project descriptions in HTML

3. **Skills:**
   - Edit the skills list in the `#skills` section

### Styling

1. **Color Scheme:**
   - Open `src/css/base.css`
   - Change color variables

2. **Fonts:**
   - Replace Google Fonts in `src/css/base.css`
   - Add your fonts to `assets/fonts/`

### PWA Configuration

1. **Icons:**
   - Add icons to `assets/icons/`
   - Update paths in `manifest.json`

2. **Caching:**
   - Edit `src/js/service-worker.js`
   - Add new files to `urlsToCache`

## Development

### Adding New Sections

1. Create HTML section in `index.html`
2. Add styles to appropriate CSS file
3. Add JavaScript functionality if needed

### Optimization

- Compress images before adding
- Minify CSS and JS for production
- Use modern image formats (WebP)

## PWA Features

- **Install as App** - add to home screen
- **Offline Work** - basic content available without internet
- **Fast Loading** - resource caching

## Contributing

1. Fork the repository
2. Create a branch for new feature
3. Make changes
4. Create Pull Request

## License

This project is available under the MIT license.

## Contact

If you have questions or suggestions, create an Issue in the repository.

---

**Happy coding!** 