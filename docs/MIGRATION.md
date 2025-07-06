# Migration Instructions

## Moving Images

If you have images from the original project, move them to the appropriate folders:

### Profile and Project Images
```
Move from root to src/images/:
- resume photo.jpg → src/images/resume photo.jpg (profile image)
- ecommerce.jpg → src/images/ecommerce.jpg
- project1.png → src/images/project1.png
- project2.png → src/images/project2.png
- portfolio.jpg → src/images/portfolio.jpg
- blog-site.jpg → src/images/blog-site.jpg
- Data-Visualization-Tools.jpg → src/images/Data-Visualization-Tools.jpg
```

### PWA Icons
```
Move from images/ to assets/icons/:
- icon-192.png → assets/icons/icon-192.png
- icon-512.png → assets/icons/icon-512.png
```

## Personalization Setup

### 1. Personal Information
Open `index.html` and replace:
- "Piyush Raorane" with your real name
- Contact information (email, phone, location)
- Description in the "About Me" section

### 2. Projects
- Replace project images in `src/images/`
- Update project descriptions in HTML
- Change technologies in `<span class="projects__tech">` tags

### 3. Skills
Edit the skills list in the `#skills` section:
```html
<ul class="skills__list skills__list--primary" role="list" aria-label="Skills and Technologies">
  <li class="skills__item" role="listitem">Your skill 1</li>
  <li class="skills__item" role="listitem">Your skill 2</li>
  <!-- Add your skills -->
</ul>
```

### 4. Social Networks
Update social network links in the hero section:
```html
<nav class="social-nav" aria-label="Social Networks">
  <a href="https://github.com/yourusername" aria-label="GitHub">
    <i class="fab fa-github"></i>
  </a>
  <!-- Add other networks -->
</nav>
```

### 5. PWA Configuration
In `manifest.json`:
- Change `name` and `short_name`
- Update `theme_color` if needed
- Make sure icon paths are correct

### 6. Package.json
In `package.json`:
- Replace author information with your details
- Update `repository.url` to your repository

## Project Structure

The project now uses BEM methodology and modular CSS:

```
portfolio-site/
├── index.html              # ✅ Updated with BEM classes
├── manifest.json           # ✅ Updated
├── package.json            # ✅ Created
├── README.md              # ✅ Created
├── .gitignore             # ✅ Created
├── src/
│   ├── css/
│   │   ├── main.css       # ✅ Main CSS import
│   │   ├── base.css       # ✅ Base styles
│   │   ├── hero.css       # ✅ Hero section styles
│   │   ├── sections.css   # ✅ Section styles with carousel
│   │   └── components.css # ✅ Component styles (nav, cards, etc.)
│   ├── js/
│   │   ├── main.js        # ✅ Updated
│   │   └── service-worker.js # ✅ Updated
│   └── images/            # 📁 Move images here
├── assets/
│   ├── fonts/             # 📁 For fonts
│   └── icons/             # 📁 Move PWA icons here
└── docs/                  # ✅ Created
```

## BEM Class Structure

The project uses BEM methodology for CSS classes:

### Navigation
- `.nav` - main navigation block
- `.nav__logo` - navigation logo element
- `.nav__menu` - navigation menu element
- `.nav__link` - navigation link element

### Sections
- `.about` - about section block
- `.about__header` - about section header
- `.about__title` - about section title
- `.about__content` - about section content
- `.about__text` - about section text

### Skills Carousel
- `.skills__content` - skills content container
- `.skills__carousel` - skills carousel container
- `.skills__list` - skills list
- `.skills__list--primary` - primary skills list modifier
- `.skills__list--duplicate` - duplicate skills list modifier
- `.skills__item` - individual skill item

### Projects
- `.projects__list` - projects list container
- `.projects__item` - individual project item
- `.projects__image` - project image
- `.projects__content` - project content
- `.projects__name` - project name
- `.projects__desc` - project description
- `.projects__footer` - project footer
- `.projects__tech` - project technologies

## Running the Project

1. **Simple launch:**
   ```bash
   # Just open index.html in browser
   ```

2. **With local server:**
   ```bash
   # Install dependencies
   npm install
   
   # Start development server
   npm run dev
   
   # Or use simple server
   npm start
   ```

## PWA Testing

1. Open the site in Chrome
2. Open DevTools (F12)
3. Go to "Application" tab
4. Check:
   - Manifest loads correctly
   - Service Worker is registered
   - Cache is working

## Production Optimization

1. **Compress images:**
   - Use WebP format
   - Optimize sizes

2. **Minify CSS and JS:**
   - Use tools like UglifyJS, CSSNano

3. **Configure caching:**
   - Update `urlsToCache` in service-worker.js

## Next Steps

1. Move images to correct folders
2. Set up personal information
3. Add your projects
4. Configure social networks
5. Test PWA functionality
6. Deploy to GitHub Pages or other hosting 