# Visual Design — Task Definitions

## VD-001 · T1 · Rendered Mockup Evaluation

**Area:** Layout & Composition  
**Max points:** 15  

### Prompt
> You will be shown a screenshot of a desktop dashboard for a project management app. Rate it independently on these three dimensions (0–5 each):
> 1. Visual hierarchy — are the most important elements immediately obvious?
> 2. Color contrast — does the palette meet WCAG AA minimums?
> 3. Input field accessibility — are labels, focus states, and error messages handled correctly?
> For each dimension give a score, a short justification, and one specific improvement recommendation.



**Artifacts provided:** `screenshots/vd-001-dashboard.png`


**Scoring (per dimension):**
- Score 0–5 assigned with justification: 0–3 pt
- Specific improvement recommendation: 1 pt
- Max per dimension: 4 pt → Total max: 12 pt (scaled to 15)

---


## VD-002 · T2 · Layout Polishing

**Area:** Layout & Composition, Branding  
**Max points:** 5 (binary checklist)  

### Prompt
> Using the brand guide in `brand-guide.pdf`, produce a single-file HTML page for the pricing section described in `wireframes/pricing-section.ascii`. Requirements:
> - Responsive: show 3 columns at >=768 px, 1 column at <768 px
> - Use brand primary color for the highlighted (recommended) plan
> - Font scale matches the type scale in the brand guide
> - Each pricing card has a hover lift effect (CSS transition)
> - No inline JavaScript; CSS only

**Artifacts provided:** `brand-guide.pdf`, `wireframes/pricing-section.ascii`

**Scoring (0/1 per check):**
- [ ] 3-column layout at >=768 px
- [ ] 1-column layout at <768 px
- [ ] Brand primary on recommended plan
- [ ] Font scale within +-1 step
- [ ] Hover transition defined on cards

Max: 5 pt

---

## VD-003 · T3 · Accessibility Audit

**Area:** Accessibility  
**Max points:** 15

### Prompt
> Audit the form shown in `screenshots/vd-003-form.png` for accessibility violations. For each issue provide:
> - WCAG 2.2 criterion violated (e.g., 1.3.1, 2.4.7)
> - Element affected (e.g., 'Name input field')
> - Concrete fix (e.g., 'Add visible focus indicator with 3:1 contrast ratio')
>
> Do not list issues that are not genuine accessibility failures.

**Artifacts provided:** `screenshots/vd-003-form.png`

**Scoring:**
- Correct WCAG criterion: 1 pt each (max 5 pt)
- Correct element identified: 1 pt each (max 5 pt)
- Feasible fix described: 1 pt each (max 5 pt)
- Total: 15 pt

---

## VD-004 · T4 · Branding Consistency Check

**Area:** Branding Consistency  
**Max points:** 5 (binary per flag)

### Prompt
> Compare the hero section in `screenshots/vd-004-hero.png` against the brand guide. Flag every violation. Each flag must name the violated rule and the specific fix. If no violations, state "Fully compliant."


**Artifacts provided:** `screenshots/vd-004-hero.png`, `brand-guide.pdf`

**Scoring:**
- Logo clear-space violation detected: 1 pt
- Primary brand color out of tolerance (+-5 pct): 1 pt
- Typeface mismatch: 1 pt
- CTA style violation: 1 pt
- Unauthorized visual style detected: 1 pt
- No false positives penalized (bonus 1 pt if zero false positives, max score unchanged)

Max: 5 pt

---

## VD-005 · T5 · Visual Judgment (Comparative)


**Area:** Visual Judgment  
**Max points:** 6

### Prompt
> Two variants of a mobile checkout screen are provided: `screenshots/vd-005a-checkout.png` and `screenshots/vd-005b-checkout.png`. The target users are adults aged 35-54 on mid-range Android devices in the United States.
> Which variant is more likely to reduce friction for this demographic, and why? Give three specific visual arguments. Cite specific elements (e.g., "the back button placement in variant A").

**Artifacts provided:** `screenshots/vd-005a-checkout.png`, `screenshots/vd-005b-checkout.png`


**Scoring:**
- Choice made (A, B, or tie with justification): 2 pt
- Each relevant visual argument (3 max): 1 pt each
- Demographic/target context mentioned: 1 pt
- Total: max 6 pt

---

## VD-006 · T6 · Screenshot Artifact Generation

**Area:** Layout & Composition, Typography  
**Max points:** 10

### Prompt
> Produce a single-file HTML page for the "Recent Activity" feed component described in `wireframes/activity-feed.ascii`. Do not use external images, fonts, or JavaScript. The output must:
> - Render a list of 4 activity items (avatar initial, action verb, timestamp, subject)
> - Use a consistent row height of 48 px
> - Display alternating row background colors (#FFFFFF and #F5F5F5)
> - Include a "Load more" button at the bottom styled with brand accent color

**Artifacts provided:** `wireframes/activity-feed.ascii`, `brand-guide.pdf`

**Scoring (automated):**
- Correct number of items rendered (4): 1 pt
- Avatar initial displayed: 1 pt
- Action verb and subject text present: 1 pt
- Timestamp displayed: 1 pt
- Row height 48 px (+-4 px tolerance): 1 pt
- Alternating row colors correct: 1 pt
- "Load more" button present: 1 pt
- Button uses brand accent color: 1 pt
- No external assets: 1 pt
- HTML valid and renderable: 1 pt

Max: 10 pt

---

## Scoring Sheet Summary

| Task ID | Type | Skill Area | Max Pt |
|---|---|---|---|
| VD-001 | T1 | Layout & Composition, Color, A11y | 15 |
| VD-002 | T2 | Layout & Composition, Branding | 5 |
| VD-003 | T3 | Accessibility | 15 |
| VD-004 | T4 | Branding Consistency | 5 |
| VD-005 | T5 | Visual Judgment | 6 |
| VD-006 | T6 | Layout & Composition, Typography | 10 |
| **Total** | | | **56** |

**Pass threshold (Competent): 20 / 56**  
**Proficient threshold: 35 / 56**  
**Expert threshold: 47 / 56**
