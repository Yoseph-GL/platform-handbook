# HTML/CSS Level 8: Animations

## Architecture / Rationale

CSS animations bring your pages to life. They provide visual feedback, guide attention, and make interfaces feel responsive. This level covers transitions, keyframe animations, and scroll-driven effects.

Scope:
- CSS transitions as animation foundation.
- Keyframe animations with `@keyframes`.
- Animated buttons and typewriter effect.
- Scroll-based animations (modern CSS).
- Integrating animations into real projects.

## Query / Code Blocks

```html
<!-- Module pages -->
<!-- [[01-transitions-recap]] -->
<!-- [[02-animations]] -->
<!-- [[03-animated-buttons-and-typewriter]] -->
<!-- [[04-scroll-based-animations]] -->
<!-- [[05-animation-range]] -->
<!-- [[06-integrating-animations]] -->
<!-- [[07-animations-fulfilling-the-promise]] -->
```

## Performance / Optimization Notes

- Only animate `transform` and `opacity` for 60fps animations. They skip layout and paint recalculations.
- Respect `prefers-reduced-motion`. Some users need animations turned off.
- Animations should enhance the experience, not distract from content.
