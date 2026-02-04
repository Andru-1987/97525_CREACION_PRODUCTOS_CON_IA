# Ultra-Concise Design Prompts

## 1  .  Extract Design from Screenshot
```
Deeply analyze the attached screenshot to create a design.json file in this project that describes the style and design of every UI component at a pixel-perfect level. Capture exact values for: grid system, spacing scale, complete color palette (50-950 shades + gradients), typography (sizes, weights, line-heights for mobile + desktop), shadows (all elevation levels), border-radius, transitions (duration + easing), and ALL component states (default, hover, active, focus, disabled, loading). Document responsive breakpoints and how each element adapts. Include animation specifications and accessibility standards. The goal: enable AI to replicate this design with 95%+ accuracy without seeing the original.
```

## 2️ .  Create Project Design System
```
In this project create a 'design/' folder with a comprehensive design-system.json file that captures: brand identity, design principles, complete foundation (grid, breakpoints, spacing scale, z-index), full color system (primary/secondary/accent 50-950, neutrals, semantics, gradients), typography system (font stacks, weights, responsive sizes, predefined text styles), effects (5-level shadow system, blur, opacity, border-radius), animation (durations, easing functions, keyframes), detailed component specs (button/input/card/modal/tooltip/badge with ALL variants and states), layout patterns, accessibility standards, and icon system. Include usage guidelines with decision trees. Every value must be a reusable token - ZERO hardcoded values allowed.
```

## 3️ .  Build Components from Design System
```
Using the attached design-system.json as SINGLE SOURCE OF TRUTH, create [COMPONENT NAME] with 100% fidelity. Rules: (1) Reference design tokens ONLY - no hardcoded values, (2) Implement ALL 5 states: default, hover, active, focus, disabled, (3) Apply exact transitions/animations from design system, (4) Responsive across all breakpoints, (5) Accessible (semantic HTML, keyboard nav, ARIA). Provide: clean component code, styles using design tokens, usage example, and brief explanation of which tokens you used and why. The component must be visually indistinguishable from the design system specifications.
```

## 4️ .  Implement New Feature (Maintains Consistency)
```
Build [FEATURE NAME] following design-system.json strictly. Non-negotiables: Read design-system.json first, use design tokens ONLY (colors/spacing/typography/effects), implement all interactive states, mobile-first responsive, accessible. Structure: clean component code, styles with design tokens only, works on all breakpoints, keyboard navigable. Provide: component code, styles, usage example, design decisions (which tokens used and why). Must be visually consistent with existing app - zero design drift allowed.
```


## When to Use Which Prompt

| Scenario | Use Prompt | Result |
|----------|------------|---------|
| Have a screenshot to replicate | **#1** | design.json with exact values |
| Starting new project | **#2** | design-system.json foundation |
| Building base components | **#3** | Button, Card, Input, Modal, etc. |
| Adding new features | **#4** | Dashboard, Profile, Settings, etc. |

---

## Pro Tips

**Make it even shorter:**
```
[Screenshot] → Prompt #1 → design.json
[New project] → Prompt #2 → design-system.json  
[Base components] → Prompt #3 + design-system.json → Components
[New features] → Prompt #4 + design-system.json → Features
```

**Add context for better results:**
- Attach screenshots when available
- Specify framework: "Build as React component" or "Build as Vue component"
- Specify styling: "Use Tailwind v3" or "Use CSS Modules" or "Use styled-components"
- Mention deployment: "Run locally with Vite" or "Deploy to Vercel"

**Combine prompts:**
```
[Attach screenshot]

Prompt #1 first to extract design, then immediately use Prompt #3 to build the Hero component using the extracted design.json.
```