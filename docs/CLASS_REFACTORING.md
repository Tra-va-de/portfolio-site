# Class Refactoring

## BEM Methodology Implementation

The project has been completely refactored to use BEM (Block Element Modifier) methodology for better maintainability and semantic clarity.

### Rationale

- **Semantic clarity**: Each class clearly indicates the component's purpose
- **Maintainability**: Easy to understand and modify styles
- **Scalability**: Consistent naming convention for future components
- **Avoiding conflicts**: No conflicts with HTML elements or other frameworks

## BEM Structure

### Block__Element--Modifier Pattern

#### Hero Block
```html
<header class="hero" id="home">
  <div class="hero__content">
    <div class="container">
      <img src="..." alt="Profile Photo" class="hero__image" />
      <h1 class="hero__title">Piyush Raorane</h1>
      <p class="hero__subtitle">Full-Stack Web Developer | Computer Engineering Student</p>
      <nav class="hero__social" aria-label="Social Networks">
        <a href="#" class="hero__social-link" aria-label="GitHub"><i class="fab fa-github"></i></a>
      </nav>
    </div>
  </div>
</header>
```

#### Navigation Block
```html
<nav class="nav" aria-label="Main Navigation">
  <div class="container">
    <a href="#home" class="nav__logo" aria-label="Go home">Portfolio</a>
    <ul class="nav__menu">
      <li><a href="#about" class="nav__link">About</a></li>
    </ul>
  </div>
</nav>
```

#### Section Blocks
```html
<section class="about" id="about">
  <div class="container">
    <header class="about__header section-header">
      <h2 class="about__title">About Me</h2>
    </header>
    <article class="about__content">
      <p class="about__text">Content...</p>
    </article>
  </div>
</section>
```

#### Skills Carousel Block
```html
<div class="skills__content">
  <div class="skills__carousel">
    <ul class="skills__list skills__list--primary" role="list">
      <li class="skills__item" role="listitem">React</li>
    </ul>
    <ul class="skills__list skills__list--duplicate" role="list" aria-hidden="true">
      <!-- Duplicate content for infinite scroll -->
    </ul>
  </div>
</div>
```

#### Projects Block
```html
<div class="projects__list projects-grid" role="grid">
  <article class="projects__item card" role="gridcell">
    <img src="..." alt="..." class="projects__image">
    <div class="projects__content">
      <h3 class="projects__name">Project Name</h3>
      <p class="projects__desc">Project Description</p>
      <footer class="projects__footer">
        <span class="projects__tech">Technologies</span>
      </footer>
    </div>
  </article>
</div>
```

## CSS Structure

### Modular CSS Files
```
src/css/
├── main.css       # Main import file
├── base.css       # Base styles and resets
├── hero.css       # Hero section styles
├── sections.css   # Section styles with carousel
└── components.css # Component styles (nav, cards, etc.)
```

### BEM Class Examples

#### Hero Classes
```css
.hero {
  background: linear-gradient(to right, #0f2027, #203a43, #2c5364);
  color: #fff;
  text-align: center;
  padding: 80px 20px 40px;
  padding-top: 120px; /* Account for fixed nav */
}

.hero__content {
  text-align: center;
}

.hero__image {
  display: block;
  width: 160px;
  aspect-ratio: 1;
  margin: 0 auto 20px;
  border-radius: 50%;
  border: 4px solid #fff;
  object-fit: cover;
}

.hero__title {
  font-size: 2.5rem;
  margin-bottom: 10px;
}

.hero__subtitle {
  font-size: 1.1rem;
  opacity: 0.9;
  margin-bottom: 20px;
}

.hero__social {
  margin-top: 15px;
}

.hero__social-link {
  font-size: 1.4rem;
  color: #fff;
  margin: 0 10px;
  transition: transform 0.3s ease;
  text-decoration: none;
}

.hero__social-link:hover {
  transform: scale(1.2);
}
```

#### Navigation Classes
```css
.nav {
  position: fixed;
  top: 0;
  left: 0;
  right: 0;
  background: rgba(255, 255, 255, 0.95);
  backdrop-filter: blur(10px);
  z-index: 1000;
}

.nav__logo {
  font-size: 1.5rem;
  font-weight: 700;
  color: #007bff;
  text-decoration: none;
}

.nav__menu {
  display: flex;
  list-style: none;
  gap: 30px;
  margin: 0;
  padding: 0;
}

.nav__link {
  color: #333;
  text-decoration: none;
  font-weight: 500;
  transition: color 0.3s ease;
}
```

#### Skills Carousel Classes
```css
.skills__content {
  overflow: hidden;
  position: relative;
  padding: 20px 0;
}

.skills__carousel {
  display: flex;
  width: fit-content;
  gap: 20px;
  animation: skills-scroll 30s linear infinite;
}

.skills__list {
  display: flex;
  gap: 20px;
  justify-content: space-around;
  align-items: center;
  flex-shrink: 0;
  margin: 0;
  padding: 0;
  list-style: none;
}

.skills__list--primary {
  /* Primary list styles */
}

.skills__list--duplicate {
  /* Duplicate list for infinite scroll */
}

.skills__item {
  background: #f0f0f0;
  padding: 8px 14px;
  border-radius: 6px;
  font-size: 0.95rem;
  white-space: nowrap;
  transition: background 0.3s ease, transform 0.3s ease;
}
```

## Benefits of BEM Implementation

### 1. Semantic Clarity
- Each class clearly indicates the component's purpose
- Easy to understand component relationships
- Self-documenting code

### 2. Maintainability
- Easy to locate and modify specific components
- Consistent naming convention
- Reduced CSS specificity conflicts

### 3. Scalability
- Easy to add new components following the same pattern
- Modular structure allows independent development
- Clear component boundaries

### 4. Team Collaboration
- Consistent naming conventions across team
- Easy to understand for new developers
- Reduced merge conflicts

## Container Pattern

The project uses a universal container pattern:

```html
<section class="about" id="about">
  <div class="container">
    <!-- Section content -->
  </div>
</section>
```

```css
.container {
  padding: 60px 20px;
  max-width: 1100px;
  margin: auto;
}
```

## Verification of Changes

1. ✅ All sections use BEM methodology
2. ✅ CSS classes follow BEM naming convention
3. ✅ Modular CSS structure implemented
4. ✅ Container pattern applied consistently
5. ✅ Skills carousel with infinite scroll
6. ✅ Semantic HTML structure maintained

## Next Steps

When adding new components in the future:
- Follow BEM naming convention: `block__element--modifier`
- Create modular CSS files for new features
- Use semantic HTML elements
- Maintain accessibility standards
- Add appropriate ARIA attributes 