# Visual Design Benchmark — Reference Documents

## Brand Guide Template

When the benchmark runner provides a `brand-guide.pdf`, it must include:

1. **Primary color** — hex value, RGB, and CMYK
2. **Secondary color** — hex value, RGB, and CMYK
3. **Accent color** — hex value, RGB, and CMYK
4. **Typography** — typeface name(s), font weights, size scale (px/rem at standard viewport), line-height ratio
5. **Logo** — usage rules, minimum size, clear-space formula, prohibited modifications
6. **Voice/tone** — 2–3 example phrases demonstrating brand tone
7. **Prohibited uses** — list of disallowed color combinations, fonts, or imagery

---

## ASCII Wireframe Format

ASCII wireframes are stored as plain-text files and must contain:

- Named sections (e.g., `[HEADER]`, `[HERO]`, `[PRICING]`)
- Approximate spatial layout using monospace characters
- Dimension annotations in pixels or relative units
- Interactivity notes where applicable (e.g., `<hover state>`)

Example:

```
[PRICING]
+--[col-1]--+--[col-2 MARKED]--+--[col-3]--+  (1280px)
| Plan A    | Plan B (rec.)     | Plan C    |
| $10/mo    | $20/mo            | $40/mo    |
| [CTA btn] | [CTA btn]         | [CTA btn] |
+----------+-------------------+-----------+
```

---


## WCAG 2.2 AA Checklist (abbreviated for benchmarking)


Used for T3 — Accessibility Audit. The full checklist is in `a11y-checklist.yaml`.



| Criterion | Description |
|---|---|
| 1.1.1 | Non-text content has text alternative |
| 1.3.1 | Info and relationships conveyed through structure |
| 1.4.3 | Contrast minimum 4.5:1 (text), 3:1 (UI components) |
| 1.4.11 | Non-text contrast minimum 3:1 |
| 2.1.1 | Keyboard operable |
| 2.4.7 | Focus visible |
| 3.3.2 | Labels or instructions for inputs |
| 4.1.2 | Name, role, value programmatically determinable |


---

## Screenshot Submission Protocol


1. Screenshots must be saved as PNG at 2x pixel density for clarity.
2. Minimum viewport for desktop tasks: 1280x800 px.
3. Minimum viewport for mobile tasks: 375x667 px (iPhone SE frame optional).
4. Screenshots must not include browser chrome or OS chrome unless the task explicitly requires it.
5. Filename convention: `{Task-ID}-{variant}-{viewport}.png`  
   Example: `vd-005a-checkout-mobile.png`

---

## Pixel Comparison Protocol (for automated T6 scoring)

- Render LM output in a headless browser at 1280x800 px viewport.
- Capture screenshot at 2x DPI.
- Compare per-element bounding boxes to reference render using pixel hash per region.
- Tolerance: +-10 px on positional metrics, +-5 pct on color values.
- Font-size comparison: +-2 px; font-weight: +-50 on CSS numeric value.
