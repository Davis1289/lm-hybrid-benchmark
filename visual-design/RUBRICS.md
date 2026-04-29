# Visual Design Benchmark — Rubric Templates

Use these templates when manually scoring task output.

---


## T1 Rubric: Rendered Mockup Evaluation (0–5 per dimension)

| Score | Visual Hierarchy | Color Contrast | Accessibility |
|---|---|---|---|
| 5 | Dominant element instantly identifiable; clear path through layout | All text meets 7:1 AAA; UI components meet 4.5:1 | All inputs labeled, focus visible, errors announced |
| 4 | Some hierarchy present but minor competing elements | 1–2 minor violations (>=4.5:1 but not AAA) | Minor a11y gaps (e.g., missing helper text) |
| 3 | Average; reader must search for key action | 1–2 clear violations (some >=3:1) | Partial compliance; some inputs unlabeled |
| 2 | Weak hierarchy; most elements compete equally | Multiple violations; below 3:1 somewhere | Several inputs without labels or focus indication |
| 1 | No discernible hierarchy | Predominantly low-contrast | Mostly inaccessible |
| 0 | No hierarchy; chaos | Contrast failures everywhere | No accessibility effort |


---

## T2 Rubric: Layout Polishing (binary 0/1 per item)


| Item | Pass | Fail |
|---|---|---|
| Breakpoint >=768 px | 3-column layout present | 2-column or broken |
| Breakpoint <768 px | 1-column layout present | 2+ columns visible |
| Brand primary color | Correct plan highlighted | Wrong plan or wrong color |
| Font scale | Within +-1 step of spec | Clearly wrong scale |
| Hover transition | CSS transition defined on `.pricing-card` | No transition or JS-only |


---

## T3 Rubric: Accessibility Audit (1 pt per item)

| Issue | WCAG | Element | Fix |
|---|---|---|---|
| Ex: Missing alt on product image | 1.1.1 | `#product-img` | Add `alt="Classic Toaster Model T-200"` |
| Ex: Low contrast on submit button | 1.4.11 | `#submit-btn` | Increase background to `#0055AA` |

Each row scored: criterion right -> 1 pt; element right -> 1 pt; fix right -> 1 pt.


---

## T4 Rubric: Branding Consistency (0/1 per flag)

| Brand Rule | Detection | Fix |
|---|---|---|
| Logo clear-space | Check 4 cardinal directions from logo edge | Increase surrounding space |
| Primary color tolerance | Compare hex values; fail if delta-E > 5 | Adjust to within tolerance |
| Typeface | Inspect computed font-family | Replace with brand font |
| CTA style | Inspect border-radius, padding, font-weight | Match brand button spec |
| Visual style | Detect prohibited patterns (e.g., drop shadows on logos) | Remove prohibited style |

---

## T5 Rubric: Visual Judgment (argument quality)

| Criterion | Points |
|---|---|
| Choice stated clearly (A/B/tie) | 2 pt |
| Each relevant visual argument (max 3) | 1 pt each |
| Demographic/context consideration | 1 pt |
| Max total | 6 pt |

---

## T6 Rubric: Artifact Generation (1 pt per check)

| Check | Method |
|---|---|
| 4 activity items rendered | Count DOM elements with activity class |
| Avatar initial shown | Visual check of first character in row |
| Action verb and subject | Text content match against wireframe spec |
| Timestamp present | Format check (HH:MM or relative) |
| Row height 48 px (+-4 px) | Measure computed height in devtools |
| Alternating colors | Check background-color values on odd/even rows |
| "Load more" button | Element presence with correct text |
| Brand accent on button | Compare button bg to brand accent hex |
| No external assets | Verify no `<img>` or `@import` tags |
| Valid renderable HTML | Browser loads without crash |
