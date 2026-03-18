# Data-viz checklist (React + Next/Router)

## Before coding
- Define: audience + decision + metric definitions
- Choose chart by question:
  - Compare: bar
  - Trend: line/area
  - Distribution: histogram/box
  - Relationship: scatter
  - Parts of whole: stacked (avoid pie unless simple)

## Implementation tips
- Use URL query params for chart state (range, filters)
- Memoize derived series and scales (`useMemo`)
- Use virtualization for big tables (TanStack Table + virtualization)
- Provide loading/skeleton + empty states
- Accessibility: labels, tooltips, keyboard focus where possible
