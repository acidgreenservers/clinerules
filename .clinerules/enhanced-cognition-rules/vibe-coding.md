---
description: Guidelines for writing semantic, accessible, and modern HTML with vibe coding principles
author: "Devin AI + https://github.com/acidgreenservers"
version: 1.0
globs: ["**/*.html", "**/*.htm", "**/*.jsx", "**/*.tsx"]
tags: ["html", "accessibility", "semantic-html", "coding-guideline", "vibe-coding"]
---

# HTML Vibe Coding Practices

## 🚨 CRITICAL INSTRUCTIONS FOR AI LANGUAGE MODELS 🚨

When generating HTML, you MUST follow semantic HTML principles and accessibility best practices. "Vibe coding" means writing HTML that feels right, is accessible, and uses modern semantic elements.

## ABSOLUTE REQUIREMENTS

1. You MUST use semantic HTML5 elements
2. You MUST include proper ARIA attributes when needed
3. You MUST NEVER use divs when semantic elements exist
4. You MUST ensure keyboard navigation works
5. You SHOULD use meaningful class names that describe content, not presentation

## ❌ NEVER GENERATE THIS CODE - ANTI-PATTERNS

```html
<!-- ❌ NEVER: Generic divs for everything -->
<div class="header">
  <div class="nav">
    <div class="nav-item">Home</div>
  </div>
</div>

<!-- ❌ NEVER: Non-semantic structure -->
<div class="button" onclick="doSomething()">Click me</div>

<!-- ❌ NEVER: Images without alt text -->
<img src="logo.png">

<!-- ❌ NEVER: Form inputs without labels -->
<input type="text" placeholder="Enter your name">

<!-- ❌ NEVER: Click handlers on non-interactive elements -->
<div onclick="navigate()">Click here</div>

<!-- ❌ NEVER: Empty links or buttons -->
<a href="#"></a>
<button></button>
```

## ✅ ALWAYS GENERATE THIS PATTERN - BEST PRACTICES

```html
<!-- ✅ ALWAYS: Use semantic HTML5 elements -->
<header>
  <nav>
    <ul>
      <li><a href="/">Home</a></li>
    </ul>
  </nav>
</header>

<!-- ✅ ALWAYS: Use proper button elements -->
<button type="button" onclick="doSomething()">Click me</button>

<!-- ✅ ALWAYS: Include descriptive alt text -->
<img src="logo.png" alt="Company Logo">

<!-- ✅ ALWAYS: Associate labels with inputs -->
<label for="name">Name:</label>
<input type="text" id="name" name="name">

<!-- ✅ ALWAYS: Use interactive elements for interactions -->
<button type="button" onclick="navigate()">Navigate</button>

<!-- ✅ ALWAYS: Provide meaningful content -->
<a href="/about">Learn more about us</a>
<button type="submit">Submit Form</button>
```

## SEMANTIC HTML ELEMENT HIERARCHY

You MUST use these semantic elements in the correct context:

- `<header>` - For page or section headers
- `<nav>` - For navigation menus
- `<main>` - For main content (ONE per page)
- `<article>` - For self-contained content
- `<section>` - For thematic grouping of content
- `<aside>` - For tangential content
- `<footer>` - For page or section footers
- `<figure>` and `<figcaption>` - For images with captions
- `<time>` - For dates and times
- `<address>` - For contact information

## ACCESSIBILITY REQUIREMENTS

### 1. Interactive Elements
```html
<!-- ✅ Buttons must have type attribute -->
<button type="button">Action</button>
<button type="submit">Submit</button>
<button type="reset">Reset</button>

<!-- ✅ Links must have descriptive text -->
<a href="/products">View our products</a>

<!-- ❌ NEVER: "Click here" or "Read more" without context -->
```

### 2. ARIA Attributes
```html
<!-- ✅ Use ARIA when semantic HTML isn't enough -->
<button aria-label="Close dialog" aria-expanded="false">×</button>
<nav aria-label="Main navigation">...</nav>
<div role="alert" aria-live="polite">Success message</div>

<!-- ✅ Mark up landmarks -->
<nav aria-label="Primary">...</nav>
<nav aria-label="Breadcrumb">...</nav>
```

### 3. Form Accessibility
```html
<!-- ✅ ALWAYS: Proper form structure -->
<form>
  <fieldset>
    <legend>Personal Information</legend>
    
    <label for="email">Email Address</label>
    <input 
      type="email" 
      id="email" 
      name="email" 
      required 
      aria-describedby="email-help"
    >
    <small id="email-help">We'll never share your email</small>
  </fieldset>
</form>
```

### 4. Heading Hierarchy
```html
<!-- ✅ ALWAYS: Maintain proper heading order -->
<h1>Page Title</h1>
  <h2>Section Title</h2>
    <h3>Subsection Title</h3>
  <h2>Another Section</h2>

<!-- ❌ NEVER: Skip heading levels -->
<h1>Title</h1>
<h3>Skipped h2</h3>
```

## MODERN HTML PATTERNS

### 1. Responsive Images
```html
<!-- ✅ Use srcset for responsive images -->
<img 
  src="image.jpg" 
  srcset="image-320.jpg 320w, image-640.jpg 640w, image-1024.jpg 1024w"
  sizes="(max-width: 640px) 100vw, 640px"
  alt="Descriptive text"
>

<!-- ✅ Use picture element for art direction -->
<picture>
  <source media="(min-width: 1024px)" srcset="large.jpg">
  <source media="(min-width: 640px)" srcset="medium.jpg">
  <img src="small.jpg" alt="Descriptive text">
</picture>
```

### 2. Loading Optimization
```html
<!-- ✅ Use loading attribute for images -->
<img src="hero.jpg" alt="Hero image" loading="eager">
<img src="footer-logo.jpg" alt="Footer logo" loading="lazy">

<!-- ✅ Preload critical resources -->
<link rel="preload" href="critical.css" as="style">
<link rel="preload" href="hero.jpg" as="image">
```

## AI MODEL VERIFICATION STEPS

Before generating HTML, you MUST verify:

1. ✅ Am I using semantic HTML5 elements instead of divs?
2. ✅ Do all images have descriptive alt text?
3. ✅ Do all form inputs have associated labels?
4. ✅ Are buttons using the `<button>` element with proper type?
5. ✅ Is the heading hierarchy logical (h1 → h2 → h3)?
6. ✅ Are interactive elements keyboard accessible?
7. ✅ Have I included necessary ARIA attributes?
8. ✅ Is there only ONE `<main>` element per page?

If ANY answer is "no", STOP and FIX before proceeding.

## CONSEQUENCES OF INCORRECT IMPLEMENTATION

Failing to follow these practices will result in:
1. Poor accessibility for screen reader users
2. SEO penalties
3. Keyboard navigation failures
4. Semantic confusion
5. Maintenance difficulties
6. Legal compliance issues (ADA, WCAG)

## VIBE CODING PHILOSOPHY

The "vibe" of good HTML means:
- **Semantic First**: Use the right element for the job
- **Accessible Always**: Everyone should be able to use your site
- **Progressive Enhancement**: Start with HTML, enhance with CSS/JS
- **Meaningful Names**: Classes describe content, not appearance
- **Clean Structure**: Nested logically, easy to scan
- **Future-Proof**: Uses modern standards that will age well

## AI MODEL RESPONSE TEMPLATE

When generating HTML, you MUST:
1. Start with semantic structure
2. Add accessibility attributes
3. Include all required content (alt text, labels)
4. Verify against the checklist above
5. NEVER use divs when semantic elements exist
6. ALWAYS ensure keyboard navigation works
```
