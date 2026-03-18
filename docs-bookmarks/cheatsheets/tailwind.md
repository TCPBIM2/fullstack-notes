[ Home](../README.md)

---

# Tailwind patterns

## Class organization
- Layout: `flex/grid`, `gap-*`, `items-*`, `justify-*`
- Spacing: `p-*`, `m-*`
- Typography: `text-*`, `font-*`, `leading-*`
- Color: `bg-*`, `text-*`, `border-*`
- State: `hover:*`, `focus:*`, `disabled:*`, `aria-*` (if used)

## Recommended utilities
- `clsx` + `tailwind-merge` for conditional classes
- Use `@layer components` sparingly for repeated patterns

## Common UI
- Buttons: base + variants (primary/secondary/destructive)
- Inputs: consistent focus ring + error states
