# Migration Instructions

## Moving Images

If you have images from the original project, move them to the appropriate folders:

### Profile and Project Images
```
Move from root to src/images/:
- resume photo.jpg → src/images/profile.jpg
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
- "Your Name" with your real name
- Contact information (email, phone, location)
- Description in the "About Me" section

### 2. Projects
- Replace project images in `src/images/`
- Update project descriptions in HTML
- Change technologies in `<span class="tech">` tags

### 3. Skills
Edit the skills list in the `#skills` section:
```html
<ul class="skills-list">
  <li>Your skill 1</li>
  <li>Your skill 2</li>
  <!-- Add your skills -->
</ul>
```

### 4. Social Networks
Update social network links in the hero section:
```html
<div class="social-icons">
  <a href="https://github.com/yourusername" aria-label="GitHub">
    <i class="fab fa-github"></i>
  </a>
  <!-- Add other networks -->
</div>
```

### 5. PWA Configuration
In `manifest.json`:
- Change `name` and `short_name`
- Update `theme_color` if needed
- Make sure icon paths are correct

### 6. Package.json
In `package.json`:
- Replace "Your Name" with your name
- Update `repository.url` to your repository

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

## Structure After Migration

```
portfolio-site/
├── index.html              # ✅ Updated
├── manifest.json           # ✅ Updated
├── package.json            # ✅ Created
├── README.md              # ✅ Created
├── .gitignore             # ✅ Created
├── src/
│   ├── css/
│   │   ├── main.css       # ✅ Created
│   │   ├── base.css       # ✅ Created
│   │   ├── hero.css       # ✅ Created
│   │   ├── sections.css   # ✅ Created
│   │   └── components.css # ✅ Created
│   ├── js/
│   │   ├── main.js        # ✅ Updated
│   │   └── service-worker.js # ✅ Updated
│   └── images/            # 📁 Move images here
├── assets/
│   ├── fonts/             # 📁 For fonts
│   └── icons/             # 📁 Move PWA icons here
└── docs/                  # ✅ Created
```

## Next Steps

1. Move images to correct folders
2. Set up personal information
3. Add your projects
4. Configure social networks
5. Test PWA functionality
6. Deploy to GitHub Pages or other hosting 