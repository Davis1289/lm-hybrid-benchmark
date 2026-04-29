# Visual Design Benchmark — Hybrid LM Evaluation

## 1. Overview

The visual-design module measures an LM's ability to produce, refine, and critique designs that are judged from screenshots or rendered artifacts (HTML/CSS output, exported images, etc.). It is designed to work even if the benchmark later runs as a web application — tasks are defined by artifacts, not proprietary tooling.

---


## 2. Skill Areas

| Area | What Is Tested |
|---|---|
| **Layout & Composition** | Spatial hierarchy, grid adherence, responsiveness, element spacing |
| **Color & Contrast** | Palette harmony, WCAG contrast compliance, brand color fidelity |
| **Typography** | Font pairing, font scale, readability, line-height, kerning |
| **Accessibility** | ARIA labeling, keyboard nav order, focus indicators, alt-text |
| **Branding Consistency** | Logo placement, brand color usage, tone alignment, asset fidelity |
| **Polish & Micro-interactions** | Hover states, transitions, loading indicators, error states |

---

## 3. Task Types

### T1 — Rendered Mockup Evaluation
The LM is shown (or generates) a screenshot of a UI and rates it against a rubric.
**Example task:**
> "Rate this login screen screenshot on (a) visual hierarchy, (b) color contrast, (c) input field accessibility. Score each 0–5 with written justification."

**Scoring:** 3 dimensions × 0–5 = max 15 points. Partial credit allowed per dimension.

---

### T2 — Layout Polishing
The LM receives a sparse wireframe (ASCII or JSON description) and a brand guide, then produces refined HTML/CSS. Grading is done by human or automated screenshot comparison against a reference render.
**Example task:**
> "Using the provided brand colors and grid spec, produce the HTML for a pricing section. The output must be responsive, use the correct font scale, and include hover states on the pricing cards."

**Scoring rubric (per item, 0 or 1):**
- Responsive at 320 px / 768 px / 1280 px breakpoints
- Brand colors present (primary, secondary, accent) in correct roles
- Font scale matches spec (±1 step tolerance)
- Hover states defined on cards
- No overlapping elements at any breakpoint

Max score: 5/5 binary checks.

---

### T3 — Accessibility Audit
The LM reviews a screenshot or HTML snippet and identifies violations.

**Example task:**
> "List every accessibility issue in the provided screenshot of a data table. For each issue give the WCAG criterion, the affected element, and a recommended fix."

**Scoring:**
- Correct WCAG criterion named: 1 pt each (max 5 pt)
- Correct element identified: 1 pt each (max 5 pt)
- Feasible fix offered: 1 pt each (max 5 pt)
- Total: 15 pt

---

### T4 — Branding Consistency Check
The LM compares a screenshot against a brand guide (colors, logo rules, typography, voice).


**Example task:**
> "Does the hero section of this landing page comply with the brand guide? Flag any violations and suggest corrections."

**Scoring (0/1 per flag):**
- Logo clear-space respected
- Primary color within ±5 % tolerance of brand value
- Typeface matches brand font
- CTA button style matches brand button spec
- No unauthorized stock-photo style

Max: 5/5

---


### T5 — Visual Judgment (Comparative)
The LM is given two screenshots (variant A vs. variant B) and a business goal and must recommend a choice with justification.

**Example task:**
> "Which variant of the checkout flow is more likely to reduce cart abandonment for a mobile user in their 40s? Argue for A or B and give three specific visual reasons."

**Scoring:**
- Correct choice or well-reasoned tie: 2 pt
- Each relevant visual argument (up to 3): 1 pt each
- Mention of target user/mobile/context: 1 pt
Total: max 6 pt


---

### T6 — Screenshot Artifact Generation
The LM produces HTML/CSS that renders to a screenshot; the screenshot is compared pixel-level or via vision model to a reference.

**Example task:**
> "Produce a single-file HTML page for a 'Recent Activity' feed component matching this ASCII wireframe. Do not use any external assets."

**Scoring (automated):**
- Element presence: binary per element (5 elements = 5 pt)
- Layout match: check grid alignment (±10 px threshold)
- Color match: per-element pixel comparison (pass/fail per element)
- Typography match: font-size within ±2 px, font-weight within ±50

Max: 10 pt

---

## 4. Scoring Summary Table

| Task Type | Max Points | Evaluation Method |
|---|---|---|
| T1 Rendered Mockup Eval | 15 | Vision model or human rubric |
| T2 Layout Polishing | 5 | Screenshot comparison (automated or human) |
| T3 Accessibility Audit | 15 | Rule-based or human checklist |
| T4 Branding Consistency | 5 | Brand guide cross-check |
| T5 Visual Judgment | 6 | Human rubric (argument quality) |
| T6 Artifact Generation | 10 | Pixel/model comparison |
| **Total** | **56** | |

---

## 5. Scoring Levels

| Score Range | Label | Interpretation |
|---|---|---|
| 0–19 | **Novice** | Frequent misalignments, missing accessibility, weak visual judgment |
| 20–34 | **Competent** | Acceptable design sense; some polish or compliance gaps |
| 35–46 | **Proficient** | Solid design output; minor deviations from spec |
| 47–56 | **Expert** | Near-reference quality; strong accessibility and branding fidelity |

---

## 6. Reference Artifacts (stored in `/assets/` in the benchmark repo)

- `brand-guide.pdf` — colors, fonts, logo rules, voice
- `wireframes/` — ASCII and JSON wireframes per task
- `reference-screenshots/` — golden screenshots for T2 and T6
- `a11y-checklist.yaml` — WCAG 2.2 AA checklist used for T3

---

## 7. Interoperability Notes

- All tasks are defined using artifacts stored in the repo (no proprietary formats).
- Screenshots can be provided by the user or generated by the benchmark runner from HTML output.
- Vision-capable models can evaluate screenshots directly; non-vision models receive task prompts with structured textual descriptions of visual elements.
- The benchmark runner may expose a web UI for human raters but the task definitions are artifact-centric, not UI-centric.


---

## 8. Example Task Sheet (excerpt)

```
Task ID  : VD-2025-04
Area     : Typography + Color
Type     : T2 Layout Polishing
Prompt   : "Using the brand guide, produce the HTML for a three-column feature
           section. Use the correct font scale, brand primary/secondary/accent,
           and ensure the middle column is hidden at mobile (<640 px) widths."
Artifacts: brand-guide.pdf, wireframes/three-col-feature.ascii
Scoring  : Binary checklist (5 items), max 5 pt
```

---

*Last updated: 2026-04-29*
*Section owner: Visual Design*
*Integration: Hybrid Benchmark v1.0*
