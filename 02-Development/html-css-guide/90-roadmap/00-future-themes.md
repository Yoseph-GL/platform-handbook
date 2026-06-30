# HTML/CSS Roadmap: Future Themes

## Architecture / Rationale

This roadmap keeps the guide scalable without mixing advanced topics into the foundational levels.

Planned progression:
1. **CSS Frameworks**: Tailwind CSS, Bootstrap, and when to use them.
2. **CSS Preprocessors**: Sass/SCSS — variables, mixins, and nesting.
3. **CSS Architecture**: ITCSS, utility-first, and design system patterns.
4. **Performance Deep Dive**: critical CSS, font loading strategies, and Core Web Vitals.
5. **JavaScript + HTML/CSS**: DOM manipulation, event-driven styling, and Web Components.
6. **Build Tools**: Vite, PostCSS, Autoprefixer, and CSS optimization pipelines.
7. **Web APIs**: Intersection Observer, Resize Observer, and the Animation API.

## Query / Code Blocks

```css
/* Example placeholder for upcoming CSS Architecture module */
/* Define a design token system with CSS custom properties */

:root {
    --space-unit: 4px;
    --space-xs: calc(var(--space-unit) * 1);
    --space-sm: calc(var(--space-unit) * 2);
    --space-md: calc(var(--space-unit) * 4);
    --space-lg: calc(var(--space-unit) * 6);
}
```

## Performance / Optimization Notes

- Keep advanced topics isolated by level to preserve entry-level readability.
- Promote topics from the roadmap to active modules only after studying them.
- New CSS features ship frequently. Check the baseline status before adding a topic.
