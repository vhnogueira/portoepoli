# Porto e Poli - Design System

## Concept: Geometric Precision

A sharp, architectural aesthetic inspired by Brazilian modernism that conveys corporate sophistication and efficiency. Zero border radius creates a distinctive, memorable identity.

---

## Color Palette

### Tailwind Configuration

```javascript
theme: {
  extend: {
    colors: {
      'pp-navy': '#0B1D3F',    // Primary brand, backgrounds
      'pp-deep': '#1A2F54',    // Secondary surfaces, cards
      'pp-blue': '#2B7FE5',    // CTAs, interactive, links
      'pp-gold': '#D4AF37',    // Premium features, highlights
      'pp-slate': '#64748B',   // Secondary text, borders
      'pp-light': '#FAFBFC',   // Primary text on dark
      'pp-gray': '#E2E8F0',    // Dividers, subtle backgrounds
    }
  }
}
```

### Usage Guidelines

- **Primary**: `pp-navy` for backgrounds, `pp-deep` for cards/surfaces
- **Accent**: `pp-blue` for CTAs and interactive elements, `pp-gold` for premium features
- **Text**: `pp-light` on dark backgrounds, `pp-navy` on light backgrounds, `pp-slate` for secondary text

---

## Typography

### Font Families

```html
<link href="https://fonts.googleapis.com/css2?family=Lexend:wght@300;400;500;600;700;800&family=IBM+Plex+Sans:wght@300;400;500;600&display=swap" rel="stylesheet">
```

```javascript
fontFamily: {
  'display': ['Lexend', 'sans-serif'],  // Headings, titles
  'body': ['IBM Plex Sans', 'sans-serif'], // Body text, UI
}
```

### Type Scale

| Element | Size | Weight | Letter Spacing | Usage |
|---------|------|--------|----------------|-------|
| Display 1 | 72px (4.5rem) | 800 | -0.02em | Hero headlines |
| Display 2 | 56px (3.5rem) | 700 | -0.02em | Section headers |
| H1 | 48px (3rem) | 700 | -0.01em | Page titles |
| H2 | 36px (2.25rem) | 700 | normal | Major sections |
| H3 | 30px (1.875rem) | 600 | normal | Subsections |
| H4 | 24px (1.5rem) | 600 | normal | Card titles |
| H5 | 20px (1.25rem) | 600 | normal | Small headings |
| Body Large | 18px (1.125rem) | 400 | normal | Intro text |
| Body | 16px (1rem) | 400 | normal | Standard text |
| Body Small | 14px (0.875rem) | 400 | normal | Captions, hints |
| Caption | 12px (0.75rem) | 500 | 0.05em | Labels (uppercase) |

### Tailwind Classes

```
text-6xl font-display font-extrabold  // Display 1
text-5xl font-display font-bold      // Display 2
text-4xl font-display font-bold      // H1
text-3xl font-display font-bold      // H2
text-2xl font-display font-semibold  // H3
text-xl font-display font-semibold   // H4
text-lg font-body                    // Body Large
text-base font-body                  // Body
text-sm font-body                    // Body Small
text-xs font-medium uppercase tracking-wider  // Caption
```

---

## Spacing System

Use Tailwind's default spacing (4px base unit):

- **Micro**: `p-1, p-2` (4-8px) - Icons, badges
- **Small**: `p-3, p-4` (12-16px) - Form labels, list items
- **Medium**: `p-4, p-6` (16-24px) - Cards, containers
- **Large**: `p-8, p-12` (32-48px) - Section padding
- **XL**: `p-16, p-24` (64-96px) - Page sections

### Layout Guidelines

- Container: `max-w-screen-xl` (1400px)
- Content: `max-w-3xl` (768px) for readability
- Grid gaps: `gap-6` (24px) mobile / `gap-8` (32px) desktop
- Padding: `px-4` mobile / `px-8` desktop

---

## Border Radius & Shadows

### Border Radius
**Always use zero border radius:**
```css
/* NO rounded corners anywhere */
border-radius: 0;
```

### Shadow System

```css
/* Sharp Shadow - Primary */
.shadow-sharp {
  box-shadow: 8px 8px 0px 0px rgba(0, 0, 0, 0.2);
}

/* Sharp Accent Shadow - Interactive */
.shadow-sharp-accent {
  box-shadow: 6px 6px 0px 0px rgba(43, 127, 229, 0.3);
}
```

**Usage**:
- `.shadow-sharp` for cards, buttons, primary elements
- `.shadow-sharp-accent` for hover states, interactive elements
- Never use soft shadows (blur)

---

## Components

### Buttons

```jsx
// Primary Button
<button className="bg-pp-blue text-pp-light px-8 py-4 font-semibold shadow-sharp
                   hover:translate-x-[-4px] hover:translate-y-[-4px]
                   hover:shadow-[12px_12px_0px_0px_rgba(0,0,0,0.3)]
                   transition-all duration-300">
  Buscar Passagens
</button>

// Secondary Button
<button className="border-2 border-pp-blue text-pp-light px-8 py-4 font-semibold
                   shadow-sharp-accent
                   hover:translate-x-[-4px] hover:translate-y-[-4px]
                   transition-all duration-300">
  Ver Pacotes
</button>

// Accent Button
<button className="bg-pp-gold text-pp-navy px-8 py-4 font-semibold shadow-sharp
                   hover:translate-x-[-4px] hover:translate-y-[-4px]
                   transition-all duration-300">
  Contato Premium
</button>
```

### Cards

```jsx
<div className="bg-pp-deep p-6 shadow-sharp
                hover:translate-x-[-4px] hover:translate-y-[-4px]
                transition-transform duration-300">
  <div className="w-12 h-12 bg-pp-blue flex items-center justify-center mb-4">
    {/* Icon */}
  </div>
  <h4 className="text-xl font-semibold text-pp-light mb-3">
    Voos Corporativos
  </h4>
  <p className="text-sm text-pp-slate">
    Passagens aéreas para empresas com as melhores tarifas negociadas.
  </p>
</div>
```

### Form Inputs

```jsx
<div>
  <label className="text-xs font-medium uppercase tracking-wider text-pp-blue block mb-3">
    Origem
  </label>
  <input
    type="text"
    placeholder="São Paulo (GRU)"
    className="w-full bg-pp-deep border-2 border-pp-slate text-pp-light
               px-4 py-3 focus:border-pp-blue focus:outline-none
               transition-colors"
  />
</div>
```

### Navigation

```jsx
<nav className="bg-pp-navy p-6 shadow-sharp">
  <div className="flex items-center justify-between">
    <div className="flex items-center space-x-2">
      <div className="w-10 h-10 bg-pp-gold flex items-center justify-center">
        <span className="text-pp-navy font-display font-bold text-lg">PP</span>
      </div>
      <span className="text-xl font-bold text-pp-light">Porto e Poli</span>
    </div>
    <div className="flex items-center space-x-8">
      <a href="#" className="text-pp-light hover:text-pp-gold transition-colors">
        Passagens
      </a>
      <a href="#" className="text-pp-light hover:text-pp-gold transition-colors">
        Corporativo
      </a>
      <button className="bg-pp-blue text-pp-light px-6 py-2 font-semibold">
        Contato
      </button>
    </div>
  </div>
</nav>
```

### Badges

```jsx
<span className="bg-pp-blue text-pp-light px-4 py-2 text-xs font-semibold
                 uppercase tracking-wide">
  Executivo
</span>

<span className="bg-pp-gold text-pp-navy px-4 py-2 text-xs font-semibold
                 uppercase tracking-wide">
  Premium
</span>

<span className="border-2 border-pp-blue text-pp-blue px-4 py-2 text-xs
                 font-semibold uppercase tracking-wide">
  Econômico
</span>
```

---

## Animation Principles

### Guidelines

- **Duration**: Fast and snappy (200-400ms for interactions, 600-800ms for page transitions)
- **Easing**: `cubic-bezier(0.4, 0, 0.2, 1)` - Sharp acceleration
- **Direction**: Slide transitions (horizontal/vertical), geometric reveals
- **Transform-based**: Use `translate` not `position`

### Example Animations

```css
/* Slide In Right */
@keyframes slideInRight {
  from {
    transform: translateX(100px);
    opacity: 0;
  }
  to {
    transform: translateX(0);
    opacity: 1;
  }
}

/* Geometric Reveal */
@keyframes geometricReveal {
  from {
    clip-path: polygon(0 0, 0 0, 0 100%, 0 100%);
  }
  to {
    clip-path: polygon(0 0, 100% 0, 100% 100%, 0 100%);
  }
}

/* Button Hover */
.btn:hover {
  transform: translate(-4px, -4px);
  box-shadow: 12px 12px 0px 0px rgba(0, 0, 0, 0.3);
  transition: all 0.3s cubic-bezier(0.4, 0, 0.2, 1);
}
```

### Tailwind Classes

```
transition-all duration-300 ease-out
hover:translate-x-[-4px] hover:translate-y-[-4px]
```

---

## Iconography

- Use **stroke-based** icons (not filled)
- Set `stroke-linecap="square"` (not round)
- Set `stroke-linejoin="miter"` (not round)
- Use `stroke-width="2"` for consistency
- Base size: 24x24px (scale to 16, 20, 32, 40px as needed)
- Recommended: Heroicons library with customization

```jsx
<svg className="w-6 h-6 text-pp-blue" fill="none" stroke="currentColor" viewBox="0 0 24 24">
  <path strokeLinecap="square" strokeLinejoin="miter" strokeWidth="2" d="M12 19l9 2-9-18-9 18 9-2zm0 0v-8"></path>
</svg>
```

---

## Layout Patterns

### Hero Section

```jsx
<section className="bg-pp-deep p-12 shadow-sharp min-h-[400px] flex items-center relative overflow-hidden">
  {/* Diagonal Accent */}
  <div className="absolute top-0 right-0 w-[200px] h-full
                  bg-gradient-to-br from-transparent to-pp-blue/10
                  [clip-path:polygon(0_0,100%_0,100%_100%,20%_100%)]" />

  <div className="max-w-2xl relative z-10">
    <span className="bg-pp-gold text-pp-navy px-4 py-2 text-xs font-semibold
                     uppercase tracking-wide inline-block mb-6">
      Viagens Corporativas
    </span>
    <h1 className="text-5xl font-bold text-pp-light mb-6">
      Conectando seu negócio ao mundo
    </h1>
    <p className="text-lg text-pp-slate mb-8">
      Soluções completas em passagens aéreas...
    </p>
    <button className="bg-pp-blue text-pp-light px-8 py-4 font-semibold shadow-sharp">
      Solicitar Orçamento
    </button>
  </div>
</section>
```

### Asymmetric Grid

```jsx
<div className="grid grid-cols-12 gap-6">
  <div className="col-span-7 bg-pp-deep p-8 shadow-sharp">
    {/* Featured content */}
  </div>
  <div className="col-span-5 bg-pp-navy p-8 shadow-sharp-accent">
    {/* Secondary content */}
  </div>
  <div className="col-span-4 bg-pp-navy p-6 shadow-sharp">Card 1</div>
  <div className="col-span-4 bg-pp-navy p-6 shadow-sharp">Card 2</div>
  <div className="col-span-4 bg-pp-navy p-6 shadow-sharp">Card 3</div>
</div>
```

---

## Responsive Design

### Breakpoints (Tailwind Defaults)

- **sm**: 640px
- **md**: 768px
- **lg**: 1024px
- **xl**: 1280px
- **2xl**: 1536px

### Mobile Considerations

- Touch targets: minimum 44x44px
- Stack cards vertically on mobile
- Collapse navigation to hamburger menu
- Reduce type scale by 20-30%
- Simplify shadows and animations
- **Maintain zero border radius** across all devices

```jsx
<div className="text-3xl md:text-5xl lg:text-6xl">
  {/* Responsive text */}
</div>

<div className="grid grid-cols-1 md:grid-cols-2 lg:grid-cols-3 gap-6">
  {/* Responsive grid */}
</div>
```

---

## Accessibility

### Color Contrast (WCAG 2.1 AA)

- Navy (#0B1D3F) + Light (#FAFBFC): ✓ AA
- Blue (#2B7FE5) + Light (#FAFBFC): ✓ AA
- Gold (#D4AF37) + Navy (#0B1D3F): ✓ AA

### Best Practices

- Use semantic HTML (`<nav>`, `<main>`, `<section>`, `<article>`)
- Add ARIA labels for interactive elements
- Support keyboard navigation with visible focus states
- Include alt text for all images
- Add 2px focus indicators
- Implement skip navigation links

```jsx
<button
  className="bg-pp-blue text-pp-light px-8 py-4
             focus:outline-none focus:ring-2 focus:ring-pp-gold focus:ring-offset-2
             focus:ring-offset-pp-navy"
  aria-label="Buscar passagens aéreas"
>
  Buscar
</button>
```

---

## Background Patterns

### Grid Background

```jsx
<div className="[background-image:linear-gradient(to_right,rgba(43,127,229,0.05)_1px,transparent_1px),linear-gradient(to_bottom,rgba(43,127,229,0.05)_1px,transparent_1px)]
                [background-size:40px_40px]">
  {/* Content */}
</div>
```

### Diagonal Accent

```jsx
<div className="relative overflow-hidden">
  <div className="absolute top-0 right-0 w-[200px] h-full
                  bg-gradient-to-br from-transparent to-pp-blue/10
                  [clip-path:polygon(0_0,100%_0,100%_100%,20%_100%)]" />
  {/* Content */}
</div>
```

---

## Quick Start Checklist

- [ ] Import Google Fonts (Lexend + IBM Plex Sans)
- [ ] Configure Tailwind with Porto e Poli color palette
- [ ] Set all border-radius to 0 globally
- [ ] Add sharp shadow utilities
- [ ] Use geometric icons with square linecaps
- [ ] Implement hover effects with translate transforms
- [ ] Test color contrast for accessibility
- [ ] Ensure touch targets are 44x44px minimum
- [ ] Add keyboard focus indicators
- [ ] Test responsive layouts on mobile

---

## File Reference

- **Full Design Guide**: `design-guide.html` - Interactive showcase with all components
- **This Document**: Quick reference for developers

---

**Design System v1.0** | Porto e Poli - Passagens e Turismo
