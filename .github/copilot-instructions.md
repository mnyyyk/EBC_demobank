# Copilot Instructions - EBC Demo Bank Project

## Project Overview
This is a Japanese-language web demo showcasing two business website prototypes:
- **みらい銀行** (`index.html`) - A comprehensive bank website with detailed financial services
- **雅美堂百貨店** (`index_store.html`) - A luxury department store website

Both are complete, production-ready single-page applications built with modern web technologies.

## Architecture & Technology Stack

### Core Technologies
- **Tailwind CSS 2.2.19** - Primary styling framework (CDN-based)
- **Font Awesome 6.4.0** - Icon library for UI elements
- **Noto Sans JP** - Japanese font for optimal readability
- **Vanilla JavaScript** - Minimal custom interactions
- **VOC.AI Live Chat** - Third-party chat integration

### File Structure
```
├── index.html           # Bank website (2,427 lines, 146KB)
├── index_store.html     # Department store (822 lines, 52KB)
└── .github/
    └── copilot-instructions.md
```

## Design & Development Patterns

### CSS Architecture
1. **Inline Tailwind Classes** - Primary styling approach using utility-first CSS
2. **Custom CSS Overrides** - Defined in `<style>` blocks for:
   - Gradient backgrounds (`.bank-gradient`, `.hero-gradient`, `.luxury-gold`)
   - Hover transitions (`.service-card:hover`, `.product-card:hover`) 
   - Print styles (`@media print`)
   - Accordion animations (`.accordion-content.active`)

### Component Patterns
- **Section-based Layout**: Each major feature is a `<section>` with ID for navigation
- **Service Cards**: Repeating card pattern with icons, titles, descriptions, and hover effects
- **Breadcrumb Navigation**: Used in bank site for deep content hierarchy
- **FAQ Accordions**: Interactive expand/collapse sections in store site

### JavaScript Functionality
- **Smooth Scrolling**: Anchor links with `scrollIntoView({ behavior: 'smooth' })`
- **Accordion Toggle**: Single-active accordion system with rotation animations
- **Third-party Integration**: VOC.AI live chat embedded via dynamic script loading

### Japanese Content Standards
- All content is in Japanese (ja-JP locale)
- Professional financial/retail terminology
- Hierarchical information architecture (service > product > details)
- Mobile-responsive design considerations for Japanese text

## Development Guidelines

### When Adding New Sections
1. Follow the section pattern: `<section id="unique-name" class="mb-16 page-section">`
2. Use breadcrumb navigation for deep content: `<div class="breadcrumb">`
3. Include section dividers: `<div class="section-divider"></div>`
4. Maintain consistent heading hierarchy (h2 → h3 → h4 → h5)

### Styling Conventions
- **Color Scheme (Bank)**: Blue gradients (`#1e40af`, `#3b82f6`) for trust/stability
- **Color Scheme (Store)**: Gold accents (`#d4af37`, `#ffd700`) for luxury
- **Spacing**: Use `mb-16` for major sections, `mb-8` for subsections
- **Cards**: Apply hover transforms and shadow effects for interactivity

### Content Structure
- **Services**: Icon + title + description + features list
- **Products**: Image + name + price + description + purchase CTA
- **FAQ**: Accordion format with consistent question/answer pairs

### JavaScript Interactions
- Keep vanilla JS for simplicity and performance
- Use `addEventListener` for event handling
- Implement single-responsibility functions (e.g., `toggleAccordion`)
- Ensure smooth scrolling for all internal navigation

## Integration Points
- **VOC.AI Chat**: Each site has unique bot ID and token
- **CDN Dependencies**: Tailwind, Font Awesome, Google Fonts (ensure version consistency)
- **No Build Process**: Direct HTML files for easy deployment and testing

## Common Tasks
- **Adding Services**: Clone existing service card structure in respective sections
- **Content Updates**: Modify Japanese text while maintaining HTML structure
- **Styling Changes**: Prefer Tailwind utilities over custom CSS when possible
- **New Interactions**: Follow accordion/smooth-scroll patterns for consistency