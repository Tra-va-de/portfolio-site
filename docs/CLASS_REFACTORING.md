# Class Refactoring

## Changing `section` class to unique class names

### Rationale

The `section` class was too generic and could conflict with the HTML `<section>` element. Replacing it with unique class names makes each section more specific and semantically clear.

### Changes

#### HTML (index.html)
- ✅ Replaced `class="section"` with unique classes for each section
- ✅ Affected sections:
  - `about-section` - "About Me" section
  - `skills-section` - "Skills & Technologies" section
  - `projects-section` - "Projects" section
  - `experience-section` - "Experience" section
  - `contact-section` - "Contact" section

#### CSS (src/css/sections.css)
- ✅ Replaced `.section` with specific selectors for each section
- ✅ Replaced `.section p` with specific selectors for paragraphs

### Benefits

1. **Semantic clarity**: Each class clearly indicates the section's purpose
2. **Conflict avoidance**: No conflict with HTML `<section>` element
3. **Uniqueness**: Each section has its own unique class
4. **Flexibility**: Easy to style each section individually
5. **Readability**: Code becomes more understandable and self-documenting

### Structure Before and After

#### Before:
```html
<section class="section" id="about">
  <!-- content -->
</section>
```

```css
.section {
  padding: 60px 20px;
  max-width: 1100px;
  margin: auto;
}
```

#### After:
```html
<section class="about-section" id="about">
  <!-- content -->
</section>
```

```css
.about-section,
.skills-section,
.projects-section,
.experience-section,
.contact-section {
  padding: 60px 20px;
  max-width: 1100px;
  margin: auto;
}
```

### Preserved Classes

- `.section-header` - remains unchanged as it's a separate class for section headers
- `.section-header h2` - styles for section headers
- `.section-header h2::after` - decorative header elements

### Verification of Changes

1. ✅ All `class="section"` replaced with unique classes
2. ✅ CSS selectors `.section` replaced with specific selectors
3. ✅ Styling works correctly
4. ✅ Semantic structure improved

### Next Steps

If additional sections need to be added in the future:
- Create unique classes for each section (e.g., `services-section`, `blog-section`)
- Use semantic class names
- Add specific styles for each section as needed 