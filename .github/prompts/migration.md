# Next.js to Vue.js Migration Guide

## Core Principle
**Make the Vue app look and behave exactly like the Next.js source app through iterative visual comparison.**

## Quick Start Workflow

### 1. Discovery & Asset Migration
- **Locate source app** and identify its structure (pages, components, assets)
- **Find and copy ALL assets** to Vue public folder:
  - Images (logos, screenshots, backgrounds, avatars)
  - SVG files
  - Any other static assets
  - Verify file sizes (>1KB) - small files are likely placeholders
- **Extract Tailwind config** from source app and migrate to `src/styles/tailwind.css`
- **Add smooth scrolling**: `html { scroll-behavior: smooth; }` in tailwind.css

### 2. Component Migration Pattern
For each component:
1. **Read** the source component (JSX/TSX file)
2. **Copy** exact structure, Tailwind classes, and text content
3. **Convert** to Vue 3 Composition API:
   - JSX → Vue template syntax
   - `useState` → `ref()`
   - Props interface → `defineProps()`
   - Event handlers → `@click` directives
4. **Test** in browser immediately
5. **Compare** side-by-side with source app
6. **Fix** any visual differences by inspecting source classes

### 3. Critical Rules
- **Never simplify or "improve"** - copy exactly as-is
- **Use exact Tailwind classes** from source components
- **Copy real asset files**, not placeholders
- **Test frequently** - open browser after each change
- **Check file sizes** - if images are <1KB, they're placeholders (copy real ones)
- **Match responsive behavior** - desktop vs mobile layouts must be identical

### 4. Common Patterns

**Images:**
```vue
<!-- Source (Next.js/React) -->
<Image src={screenshot} alt="" />

<!-- Vue Target -->
<img :src="screenshot" alt="" class="w-full" />
```

**Tabs/State:**
```vue
<!-- Use ref() for selected index -->
const selectedIndex = ref(0)
```

**Carousels:**
```vue
<!-- Items need fixed width and flex-shrink-0 -->
<div class="w-[52.75rem] flex-shrink-0" :style="{ transform: `translateX(-${selectedIndex * 100}%)` }">
```

**Loops:**
```vue
<!-- Source -->
{features.map((feature) => <Feature feature={feature} />)}

<!-- Vue -->
<Feature v-for="feature in features" :key="feature.name" :feature="feature" />
```

### 5. Vue Target Structure
All migrated code follows this structure:
```
src/
  components/          # Reusable UI components
  styles/
    tailwind.css      # Tailwind config + custom styles
  App.vue             # Root component
  main.js             # Entry point
  router.js           # Vue Router (if multi-page)
public/
  images/             # All image assets
```

### 6. Testing Checklist
- [ ] Run both apps side-by-side (source vs Vue)
- [ ] Compare every section visually
- [ ] Test all interactive features (tabs, buttons, mobile menu)
- [ ] Check responsive layouts at 640px, 1024px, 1280px
- [ ] Verify smooth scrolling on anchor links
- [ ] Confirm all images load correctly (no broken images)
- [ ] Check console for errors

## Quick Reference: React/Next.js → Vue Conversions

| Source | Vue |
|---------|-----|
| `import { useState }` | `import { ref }` |
| `const [count, setCount] = useState(0)` | `const count = ref(0)` |
| `<Link href="/page">` | `<router-link to="/page">` |
| `className={clsx(...)}` | `:class="[...]"` |
| `{variable}` | `{{ variable }}` |
| `onClick={handler}` | `@click="handler"` |
| `Image component` | `<img>` tag |
| `{condition && <Component />}` | `<Component v-if="condition" />` |

## Success Criteria
✅ Vue app is pixel-perfect match to source app
✅ All images display correctly (no broken images)
✅ All interactive features work (tabs, carousels, navigation)
✅ Responsive design matches at all breakpoints
✅ No console errors
✅ Smooth scrolling enabled
