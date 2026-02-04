# Pro Tips para Designs Systems

*Por medio de algunas paginas como las siguientes, puedo desarrollar un poco mas sobre los designs de estos MVPS, con algunos modelos en particular*


- [Figma Design](https://www.figma.com/community/file/1179801379118868320)
- [Dribble Design System](https://dribbble.com/search/design-system)
- [Medium Data Design System](https://uxdesign.cc/dear-llm-heres-how-my-design-system-works-b59fb9a342b7)


---
### Imagen de los componentes que quiero que use para el design pedido.

![imagen de muestra](../.img/design_system.jpg)

---

## 1. [Proyecto nuevo] → Usa improved_design_system_prompt.md → Genera: design/design-system.json
```bash
Deeply analyse the design of the attached screenshot to create a design.json file, in this project that describes the style and design of every UI component needed in a design system at a high level like a creative director. Capture high level guidelines for structure, spacing, fonts, colours, design style and design principles so I can use this file as the design guidelines for my app. The goal with this file is to instruct AI to be able to replicate this look easily in this project.
```
<details>
  <summary>Version mejorada sobre el prompt anterior</summary

  Analyze the attached screenshot with extreme precision to create a comprehensive `design.json` file that serves as a complete design system specification. Your analysis should enable AI to replicate this design with 95-100% accuracy.

  ## Core Analysis Requirements

  ### 1. Visual Hierarchy & Layout
  - **Grid System**: Identify the underlying grid (columns, gutters, margins). Measure exact spacing units.
  - **Container Widths**: Document max-widths, breakpoints, and responsive behavior patterns
  - **Section Spacing**: Capture vertical rhythm between sections (padding-top, padding-bottom in rem/px)
  - **Component Positioning**: Note absolute vs relative positioning, z-index layers, flex/grid patterns

  ### 2. Typography System (Exhaustive)
  For EACH text element visible:
  - **Font Family**: Exact name and fallback stack
  - **Font Weights**: All weights used (100-900)
  - **Font Sizes**: Desktop and mobile sizes in rem/px
  - **Line Heights**: Exact values (unitless or percentage)
  - **Letter Spacing**: Track specific letter-spacing values
  - **Text Transform**: Uppercase, lowercase, capitalize instances
  - **Font Style**: Italic, oblique usage
  - **Text Decoration**: Underlines, strikethroughs
  - **Text Alignment**: Left, center, right, justify
  - **Text Color**: Exact hex/rgba values with opacity
  - **Text Shadows**: If present, document offset, blur, color
  - **Responsive Scaling**: How typography changes across breakpoints

  ### 3. Color Palette (Complete Extraction)
  - **Primary Colors**: Main brand colors with exact hex codes
  - **Secondary Colors**: Supporting palette
  - **Accent Colors**: Highlights, CTAs, interactive states
  - **Neutral Scale**: Grays from lightest to darkest (include all shades)
  - **Semantic Colors**: Success, error, warning, info
  - **Background Colors**: Solids, gradients (with angle, stops, positions)
  - **Text Colors**: Body, headings, muted, links
  - **Border Colors**: All border color variations
  - **Shadow Colors**: Colors used in box-shadows and drop-shadows
  - **Overlay Colors**: Modal backgrounds, transparent overlays with opacity
  - **Gradient Specifications**: Linear/radial, angles, color stops, positions

  ### 4. Spacing & Sizing System
  - **Spacing Scale**: Identify the spacing progression (e.g., 4px, 8px, 16px, 24px, 32px, 48px, 64px)
  - **Component Padding**: Internal spacing for cards, buttons, inputs
  - **Component Margins**: External spacing between elements
  - **Gap Values**: Grid and flexbox gaps
  - **Border Radius Scale**: All radius values used (small, medium, large, full)
  - **Icon Sizes**: Standardized icon dimensions
  - **Avatar Sizes**: Profile image dimensions
  - **Container Constraints**: Min/max widths and heights

  ### 5. Component Specifications

  #### Buttons
  - **Variants**: Primary, secondary, tertiary, ghost, link
  - **States**: Default, hover, active, focus, disabled, loading
  - **Sizes**: Small, medium, large (height, padding, font-size)
  - **Border**: Width, style, color, radius
  - **Shadow**: Box-shadow values for each state
  - **Transitions**: Duration, easing functions, properties
  - **Icon Placement**: Left, right, icon-only specifications
  - **Min-Width**: Minimum button widths

  #### Cards
  - **Background**: Color, gradients, images, overlays
  - **Border**: Width, color, radius, style
  - **Shadow**: Elevation levels (0-5 scale)
  - **Padding**: Internal spacing
  - **Hover Effects**: Transform, shadow changes, opacity shifts
  - **Image Treatment**: Aspect ratios, object-fit, filters
  - **Content Layout**: Header, body, footer structure

  #### Forms & Inputs
  - **Input Fields**: Height, padding, border, radius, background
  - **Labels**: Position, size, color, required indicators
  - **Placeholder**: Color, opacity, font-style
  - **Focus State**: Border color, outline, shadow, glow effects
  - **Error State**: Border color, background, icon, message styling
  - **Success State**: Visual indicators
  - **Disabled State**: Opacity, cursor, background changes

  #### Navigation
  - **Nav Bar**: Height, padding, background, shadow, sticky behavior
  - **Logo**: Size, spacing, positioning
  - **Nav Links**: Spacing, padding, hover/active states, underline animations
  - **Mobile Menu**: Hamburger style, drawer animation, overlay
  - **Dropdown Menus**: Trigger, panel shadow, animation, arrow indicators

  ### 6. Animation & Motion
  - **Transition Properties**: Which properties animate (opacity, transform, color)
  - **Duration**: Timing in milliseconds for each animation type
  - **Easing Functions**: cubic-bezier values, ease-in-out, spring animations
  - **Hover Effects**: Scale, lift (translateY), shadow growth, color transitions
  - **Loading States**: Skeleton screens, spinners, progress indicators
  - **Scroll Animations**: Fade-in, slide-in, parallax specifications
  - **Micro-interactions**: Button clicks, toggle switches, checkbox animations
  - **Page Transitions**: Fade, slide animations between views

  ### 7. Effects & Filters
  - **Shadows**: 
    - Box shadows (x, y, blur, spread, color, inset)
    - Text shadows
    - Drop shadows for images
    - Elevation system (levels 0-5)
  - **Blur Effects**: Backdrop-filter blur values, Gaussian blur
  - **Opacity Levels**: All opacity values used across components
  - **Gradients**: 
    - Linear gradient angles and color stops
    - Radial gradient positions and stops
    - Conic gradients if present
  - **Blend Modes**: Multiply, overlay, screen, etc.
  - **Filters**: Brightness, contrast, saturate, grayscale, hue-rotate values
  - **Glassmorphism**: Backdrop blur + transparency combinations

  ### 8. Imagery & Media
  - **Image Treatment**: Border-radius, object-fit (cover/contain), filters
  - **Aspect Ratios**: Common ratios used (16:9, 4:3, 1:1, 3:2)
  - **Overlay Patterns**: Gradient overlays on hero images
  - **Background Patterns**: Textures, SVG patterns, noise
  - **Icon Style**: Outline, filled, duotone, size variations
  - **Illustration Style**: Color palette, line weight, visual style

  ### 9. Responsive Design Patterns
  - **Breakpoints**: Mobile, tablet, desktop, wide (exact px values)
  - **Layout Shifts**: How columns change (1-col → 2-col → 3-col)
  - **Typography Scaling**: Font-size changes per breakpoint
  - **Spacing Adjustments**: How padding/margins scale down
  - **Hidden Elements**: What hides/shows at different viewports
  - **Mobile-First Patterns**: Touch targets, swipe gestures, mobile nav

  ### 10. Design Principles & Style Guide
  - **Visual Style**: Modern, minimal, bold, playful, corporate, etc.
  - **Design Philosophy**: Clean, vibrant, energetic, calm, professional
  - **Personality Traits**: Friendly, authoritative, innovative, trustworthy
  - **Tone**: How does the design communicate? Casual, formal, energetic?
  - **Whitespace Strategy**: Generous, compact, balanced
  - **Visual Weight**: How attention is directed (bold headings, large CTAs)
  - **Accessibility**: Contrast ratios, focus indicators, keyboard navigation cues

  ### 11. Interactive States (Critical for Replication)
  For every interactive element, document:
  - **Default State**: Base appearance
  - **Hover State**: Color, transform, shadow changes
  - **Active/Pressed State**: During click/tap
  - **Focus State**: Keyboard navigation indicator
  - **Disabled State**: Visual treatment
  - **Loading State**: Spinner, skeleton, opacity
  - **Error/Success State**: Color changes, icons, borders

  ### 12. Advanced Details
  - **Border Styles**: Solid, dashed, dotted, gradient borders
  - **Dividers**: Line thickness, color, spacing around dividers
  - **Badges & Tags**: Size, color, radius, padding
  - **Tooltips**: Background, arrow, shadow, max-width, positioning
  - **Modals**: Backdrop color/blur, panel shadow, border, animation
  - **Toasts/Notifications**: Position, animation-in/out, auto-dismiss timing
  - **Progress Indicators**: Track color, fill color, height, animation
  - **Tabs**: Active indicator style, spacing, hover states
  - **Accordions**: Icon rotation, content reveal animation
  - **Carousels**: Dot indicators, arrow buttons, swipe behavior

  ## Output Format: design.json Structure

  {
    "projectName": "Extracted from screenshot",
    "designSystem": {
      "grid": {
        "columns": 12,
        "gutter": "24px",
        "margins": "auto",
        "maxWidth": "1440px",
        "breakpoints": {
          "mobile": "320px",
          "tablet": "768px",
          "desktop": "1024px",
          "wide": "1440px"
        }
      },
      "spacing": {
        "scale": [4, 8, 12, 16, 24, 32, 48, 64, 96, 128],
        "unit": "px"
      },
      "colors": {
        "primary": {
          "50": "#...",
          "100": "#...",
          // ... through 900
        },
        "gradients": {
          "hero": "linear-gradient(135deg, #... 0%, #... 100%)"
        }
        // Complete palette
      },
      "typography": {
        "fontFamily": {
          "heading": "'Font Name', sans-serif",
          "body": "'Font Name', sans-serif"
        },
        "fontWeights": {},
        "fontSizes": {},
        "lineHeights": {},
        "letterSpacing": {}
      },
      "effects": {
        "shadows": {
          "sm": "0 1px 2px 0 rgb(0 0 0 / 0.05)",
          // Elevation system
        },
        "blur": {
          "sm": "4px",
          // Blur scale
        },
        "transitions": {
          "fast": "150ms",
          "base": "250ms",
          "slow": "350ms",
          "easing": {
            "default": "cubic-bezier(0.4, 0, 0.2, 1)",
            "in": "cubic-bezier(0.4, 0, 1, 1)",
            "out": "cubic-bezier(0, 0, 0.2, 1)"
          }
        }
      },
      "components": {
        "button": {
          "variants": {
            "primary": {
              "default": {},
              "hover": {},
              "active": {},
              "disabled": {}
            }
          }
        }
        // All components
      },
      "designPrinciples": {
        "style": "Modern, vibrant, energetic",
        "philosophy": "...",
        "characteristics": []
      }
    }
  }


  ## Critical Instructions for AI Replication

  1. **Extract EXACT values** - Don't approximate. Use browser DevTools precision.
  2. **Document ALL states** - Hover, focus, active, disabled for every interactive element
  3. **Capture animations** - Duration, easing, properties that animate
  4. **Note responsive behavior** - How each element adapts to screen size
  5. **Identify patterns** - Reusable design tokens that repeat across components
  6. **Context matters** - Note when similar elements differ based on context
  7. **Measure precisely** - Use pixel-perfect measurements, not estimates

  ## Deliverable

  Create a `design.json` file that is so detailed and comprehensive that an AI can recreate this design with 95%+ visual accuracy without seeing the original screenshot. Every visual decision should be documented and explainable through the design system.

</details>

---
## 2. [Tienes screenshot de referencia] → Usa improved_design_prompt.md → Analiza y extrae: design.json con valores exactos
## Uso del JSON

```bash
Let's re-style the app design following the design style outlined in @design.json . Build this as a PWA app using React and translate all styling into tailwind v3.
```

<details>
<summary> Version Mejorada para usar el Prompt de aplicacion</summary>

  Using the attached `design.json` file as the SINGLE SOURCE OF TRUTH for all design decisions, create [COMPONENT NAME] with 100% adherence to the design system specifications.

  ## Strict Implementation Rules

  ### 1. Design Token Usage
  - **NEVER hardcode values** - Always reference design tokens from design.json
  - Use exact color values from the palette (no approximations)
  - Use exact spacing values from the spacing scale
  - Use exact typography specifications (font-size, line-height, letter-spacing)
  - Apply the exact shadow, blur, and transition values documented

  ### 2. State Management
  Implement ALL interactive states documented in design.json:
  - Default state (base appearance)
  - Hover state (cursor pointer, visual feedback)
  - Active/Pressed state (during interaction)
  - Focus state (keyboard navigation indicator)
  - Disabled state (reduced opacity, cursor not-allowed)
  - Loading state (if applicable)
  - Error state (if applicable)

  ### 3. Responsive Behavior
  - Implement breakpoints exactly as specified
  - Apply typography scaling per breakpoint
  - Adjust spacing as documented in responsive patterns
  - Handle layout shifts (column changes) as specified
  - Ensure touch targets are minimum 44x44px on mobile

  ### 4. Animation & Transitions
  - Apply transition duration from design.json
  - Use exact easing functions specified
  - Animate only the properties documented
  - Respect animation principles (subtle, purposeful, performant)

  ### 5. Accessibility Requirements
  - Minimum contrast ratio 4.5:1 for text
  - Focus indicators must be visible (from design.json)
  - Semantic HTML elements
  - ARIA labels where needed
  - Keyboard navigation support

  ### 6. Component Structure
  ```
  [ComponentName]/
    ├── [ComponentName].tsx (or .jsx)
    ├── [ComponentName].module.css (or styled-components)
    └── types.ts (if using TypeScript)
  ```

  ## Expected Output

  Provide:
  1. **Clean, production-ready code** using modern React best practices
  2. **CSS/styling** that precisely matches design.json specifications
  3. **PropTypes or TypeScript types** for component props
  4. **Usage example** showing the component in action
  5. **Variants** (if component has multiple variants in design.json)

  ## Design System Mapping

  When implementing, create a clear mapping:
  - Colors → CSS custom properties or theme object
  - Spacing → Use spacing scale values
  - Typography → Font family, size, weight from design.json
  - Effects → Shadows, blur, transitions as specified
  - Components → Exact dimensions, padding, border-radius

  ## Example Implementation Checklist

  - [ ] Component uses exact colors from design.json palette
  - [ ] Spacing matches spacing scale (no arbitrary values)
  - [ ] Typography matches specifications (size, weight, line-height)
  - [ ] All interactive states are implemented
  - [ ] Animations use documented duration and easing
  - [ ] Responsive behavior matches breakpoints
  - [ ] Accessibility requirements are met
  - [ ] Code is clean, reusable, and well-commented

  ## Fidelity Target

  The implemented component must be **visually indistinguishable** from the original screenshot when the design.json was extracted. Aim for 95-100% visual fidelity.

  ## Additional Notes

  - Use the design principles from design.json to guide any edge cases
  - When in doubt, reference the design system philosophy
  - Maintain consistency with other components in the system
  - Optimize for performance (avoid unnecessary re-renders, use CSS transforms for animations)

  ---

  **Specific Request**: [Describe the component you want built and any specific requirements]

  **Reference design.json**: [Ensure design.json is attached or in context]
</details>

## 3. [Construir features] → Usa implementation_prompt.md + design-system.json → Output: Componentes 100% consistentes

---
```bash
In this project create a folder named 'design' and create a design-system.json file in this folder that outlines the exact styling for all components and styles in this app along with high level design guidelines. The goal with the file is to create a comprehensive guide for AI to follow when builing new features in this app.
```


<details>
  <summary>Version Mejorada para usar el Prompt de aplicacion</summary>

# Comprehensive Design System Creation Prompt

Create a `design` folder in the project root and generate a `design-system.json` file that serves as the **single source of truth** for all visual design decisions, component specifications, and design guidelines in this application.

## Objectives

This design system file must enable any AI or developer to:
1. Build new features with **100% visual consistency** to existing components
2. Understand design decisions and their rationale
3. Scale the design system as the app grows
4. Maintain brand consistency across all touchpoints
5. Implement responsive, accessible, and performant UI

## File Structure Requirements

```
project-root/
└── design/
    ├── design-system.json          # Main design system file
    ├── design-tokens.json          # Exportable design tokens (optional)
    ├── component-specs.json        # Detailed component specifications (optional)
    └── README.md                   # Design system documentation
```

## design-system.json Comprehensive Specification

Create a JSON file with the following exhaustive structure:

### 1. Project Meta Information
```json
{
  "meta": {
    "projectName": "App Name",
    "version": "1.0.0",
    "lastUpdated": "2024-01-30",
    "designSystemVersion": "1.0.0",
    "brand": {
      "name": "Brand Name",
      "mission": "Brief mission statement",
      "personality": ["Trait 1", "Trait 2", "Trait 3"],
      "voiceAndTone": "Description of brand voice"
    }
  }
}
```

### 2. Design Principles & Philosophy
```json
{
  "designPrinciples": {
    "core": [
      {
        "principle": "Clarity over cleverness",
        "description": "Users should never be confused...",
        "example": "Plain language in CTAs, obvious navigation"
      }
    ],
    "visualStyle": {
      "descriptor": "Modern, vibrant, energetic",
      "characteristics": [
        "Bold typography",
        "Generous whitespace",
        "Subtle animations",
        "Vibrant accent colors"
      ],
      "avoid": [
        "Overly complex layouts",
        "Excessive ornamentation",
        "Conflicting animation patterns"
      ]
    },
    "userExperience": {
      "philosophy": "Mobile-first, accessibility-focused",
      "priorities": ["Speed", "Clarity", "Delight"],
      "interactions": "Responsive, predictable, with subtle feedback"
    }
  }
}
```

### 3. Foundation - Grid & Layout
```json
{
  "foundation": {
    "grid": {
      "columns": {
        "mobile": 4,
        "tablet": 8,
        "desktop": 12
      },
      "gutter": {
        "mobile": "16px",
        "tablet": "24px",
        "desktop": "32px"
      },
      "margin": {
        "mobile": "16px",
        "tablet": "32px",
        "desktop": "auto"
      },
      "maxWidth": "1440px",
      "containerPadding": {
        "mobile": "16px",
        "tablet": "32px",
        "desktop": "48px"
      }
    },
    "breakpoints": {
      "xs": "320px",
      "sm": "640px",
      "md": "768px",
      "lg": "1024px",
      "xl": "1280px",
      "2xl": "1536px"
    },
    "spacing": {
      "scale": {
        "0": "0px",
        "1": "4px",
        "2": "8px",
        "3": "12px",
        "4": "16px",
        "5": "20px",
        "6": "24px",
        "8": "32px",
        "10": "40px",
        "12": "48px",
        "16": "64px",
        "20": "80px",
        "24": "96px",
        "32": "128px"
      },
      "usage": {
        "componentPadding": "4-6",
        "sectionSpacing": "12-16",
        "elementMargin": "2-4"
      }
    },
    "zIndex": {
      "dropdown": 1000,
      "sticky": 1020,
      "fixed": 1030,
      "modalBackdrop": 1040,
      "modal": 1050,
      "popover": 1060,
      "tooltip": 1070
    }
  }
}
```

### 4. Color System (Complete Palette)
```json
{
  "colors": {
    "brand": {
      "primary": {
        "50": "#f0f9ff",
        "100": "#e0f2fe",
        "200": "#bae6fd",
        "300": "#7dd3fc",
        "400": "#38bdf8",
        "500": "#0ea5e9",
        "600": "#0284c7",
        "700": "#0369a1",
        "800": "#075985",
        "900": "#0c4a6e",
        "950": "#082f49",
        "DEFAULT": "#0ea5e9"
      },
      "secondary": {
        "50": "#...",
        "DEFAULT": "#..."
      },
      "accent": {
        "50": "#...",
        "DEFAULT": "#..."
      }
    },
    "neutral": {
      "white": "#ffffff",
      "black": "#000000",
      "50": "#fafafa",
      "100": "#f5f5f5",
      "200": "#e5e5e5",
      "300": "#d4d4d4",
      "400": "#a3a3a3",
      "500": "#737373",
      "600": "#525252",
      "700": "#404040",
      "800": "#262626",
      "900": "#171717",
      "950": "#0a0a0a"
    },
    "semantic": {
      "success": {
        "light": "#d1fae5",
        "DEFAULT": "#10b981",
        "dark": "#047857"
      },
      "error": {
        "light": "#fee2e2",
        "DEFAULT": "#ef4444",
        "dark": "#b91c1c"
      },
      "warning": {
        "light": "#fef3c7",
        "DEFAULT": "#f59e0b",
        "dark": "#b45309"
      },
      "info": {
        "light": "#dbeafe",
        "DEFAULT": "#3b82f6",
        "dark": "#1e40af"
      }
    },
    "text": {
      "primary": "#171717",
      "secondary": "#525252",
      "tertiary": "#a3a3a3",
      "inverse": "#ffffff",
      "link": "#0ea5e9",
      "linkHover": "#0284c7"
    },
    "background": {
      "primary": "#ffffff",
      "secondary": "#f5f5f5",
      "tertiary": "#e5e5e5",
      "inverse": "#171717",
      "overlay": "rgba(0, 0, 0, 0.5)"
    },
    "border": {
      "light": "#e5e5e5",
      "DEFAULT": "#d4d4d4",
      "dark": "#a3a3a3",
      "focus": "#0ea5e9"
    },
    "gradients": {
      "hero": "linear-gradient(135deg, #667eea 0%, #764ba2 100%)",
      "card": "linear-gradient(180deg, #ffffff 0%, #f5f5f5 100%)",
      "button": "linear-gradient(90deg, #0ea5e9 0%, #0284c7 100%)"
    }
  }
}
```

### 5. Typography System
```json
{
  "typography": {
    "fontFamily": {
      "sans": "'Inter', -apple-system, BlinkMacSystemFont, 'Segoe UI', sans-serif",
      "serif": "'Merriweather', Georgia, serif",
      "mono": "'Fira Code', 'Courier New', monospace",
      "display": "'Poppins', sans-serif"
    },
    "fontWeight": {
      "thin": 100,
      "extralight": 200,
      "light": 300,
      "normal": 400,
      "medium": 500,
      "semibold": 600,
      "bold": 700,
      "extrabold": 800,
      "black": 900
    },
    "fontSize": {
      "mobile": {
        "xs": "12px",
        "sm": "14px",
        "base": "16px",
        "lg": "18px",
        "xl": "20px",
        "2xl": "24px",
        "3xl": "28px",
        "4xl": "32px",
        "5xl": "36px",
        "6xl": "40px"
      },
      "desktop": {
        "xs": "12px",
        "sm": "14px",
        "base": "16px",
        "lg": "18px",
        "xl": "20px",
        "2xl": "24px",
        "3xl": "30px",
        "4xl": "36px",
        "5xl": "48px",
        "6xl": "60px",
        "7xl": "72px"
      }
    },
    "lineHeight": {
      "none": 1,
      "tight": 1.25,
      "snug": 1.375,
      "normal": 1.5,
      "relaxed": 1.625,
      "loose": 2
    },
    "letterSpacing": {
      "tighter": "-0.05em",
      "tight": "-0.025em",
      "normal": "0",
      "wide": "0.025em",
      "wider": "0.05em",
      "widest": "0.1em"
    },
    "textStyles": {
      "h1": {
        "mobile": {
          "fontSize": "32px",
          "lineHeight": 1.25,
          "fontWeight": 700,
          "letterSpacing": "-0.025em",
          "fontFamily": "display"
        },
        "desktop": {
          "fontSize": "60px",
          "lineHeight": 1.2,
          "fontWeight": 700,
          "letterSpacing": "-0.025em",
          "fontFamily": "display"
        }
      },
      "h2": {
        "mobile": { "fontSize": "28px", "lineHeight": 1.3, "fontWeight": 700 },
        "desktop": { "fontSize": "48px", "lineHeight": 1.25, "fontWeight": 700 }
      },
      "h3": {
        "mobile": { "fontSize": "24px", "lineHeight": 1.35, "fontWeight": 600 },
        "desktop": { "fontSize": "36px", "lineHeight": 1.3, "fontWeight": 600 }
      },
      "h4": {
        "mobile": { "fontSize": "20px", "lineHeight": 1.4, "fontWeight": 600 },
        "desktop": { "fontSize": "30px", "lineHeight": 1.35, "fontWeight": 600 }
      },
      "h5": {
        "mobile": { "fontSize": "18px", "lineHeight": 1.4, "fontWeight": 600 },
        "desktop": { "fontSize": "24px", "lineHeight": 1.4, "fontWeight": 600 }
      },
      "h6": {
        "mobile": { "fontSize": "16px", "lineHeight": 1.5, "fontWeight": 600 },
        "desktop": { "fontSize": "20px", "lineHeight": 1.5, "fontWeight": 600 }
      },
      "body-large": {
        "fontSize": "18px",
        "lineHeight": 1.625,
        "fontWeight": 400
      },
      "body": {
        "fontSize": "16px",
        "lineHeight": 1.5,
        "fontWeight": 400
      },
      "body-small": {
        "fontSize": "14px",
        "lineHeight": 1.5,
        "fontWeight": 400
      },
      "caption": {
        "fontSize": "12px",
        "lineHeight": 1.5,
        "fontWeight": 400
      }
    }
  }
}
```

### 6. Effects & Elevation
```json
{
  "effects": {
    "shadows": {
      "none": "none",
      "xs": "0 1px 2px 0 rgb(0 0 0 / 0.05)",
      "sm": "0 1px 3px 0 rgb(0 0 0 / 0.1), 0 1px 2px -1px rgb(0 0 0 / 0.1)",
      "md": "0 4px 6px -1px rgb(0 0 0 / 0.1), 0 2px 4px -2px rgb(0 0 0 / 0.1)",
      "lg": "0 10px 15px -3px rgb(0 0 0 / 0.1), 0 4px 6px -4px rgb(0 0 0 / 0.1)",
      "xl": "0 20px 25px -5px rgb(0 0 0 / 0.1), 0 8px 10px -6px rgb(0 0 0 / 0.1)",
      "2xl": "0 25px 50px -12px rgb(0 0 0 / 0.25)",
      "inner": "inset 0 2px 4px 0 rgb(0 0 0 / 0.05)"
    },
    "elevation": {
      "level0": {
        "shadow": "none",
        "description": "Base level, no elevation"
      },
      "level1": {
        "shadow": "0 1px 3px 0 rgb(0 0 0 / 0.1)",
        "description": "Subtle lift, cards at rest"
      },
      "level2": {
        "shadow": "0 4px 6px -1px rgb(0 0 0 / 0.1)",
        "description": "Raised cards, dropdowns"
      },
      "level3": {
        "shadow": "0 10px 15px -3px rgb(0 0 0 / 0.1)",
        "description": "Modals, popovers"
      },
      "level4": {
        "shadow": "0 20px 25px -5px rgb(0 0 0 / 0.1)",
        "description": "High priority elements"
      },
      "level5": {
        "shadow": "0 25px 50px -12px rgb(0 0 0 / 0.25)",
        "description": "Maximum elevation"
      }
    },
    "blur": {
      "none": "0",
      "sm": "4px",
      "md": "8px",
      "lg": "16px",
      "xl": "24px",
      "2xl": "40px"
    },
    "opacity": {
      "0": "0",
      "5": "0.05",
      "10": "0.1",
      "20": "0.2",
      "25": "0.25",
      "30": "0.3",
      "40": "0.4",
      "50": "0.5",
      "60": "0.6",
      "70": "0.7",
      "75": "0.75",
      "80": "0.8",
      "90": "0.9",
      "95": "0.95",
      "100": "1"
    },
    "borderRadius": {
      "none": "0",
      "sm": "4px",
      "md": "6px",
      "lg": "8px",
      "xl": "12px",
      "2xl": "16px",
      "3xl": "24px",
      "full": "9999px"
    },
    "borderWidth": {
      "0": "0",
      "DEFAULT": "1px",
      "2": "2px",
      "4": "4px",
      "8": "8px"
    }
  }
}
```

### 7. Animation & Motion
```json
{
  "animation": {
    "duration": {
      "instant": "0ms",
      "fast": "150ms",
      "normal": "250ms",
      "slow": "350ms",
      "slower": "500ms",
      "slowest": "700ms"
    },
    "easing": {
      "linear": "linear",
      "ease": "ease",
      "easeIn": "cubic-bezier(0.4, 0, 1, 1)",
      "easeOut": "cubic-bezier(0, 0, 0.2, 1)",
      "easeInOut": "cubic-bezier(0.4, 0, 0.2, 1)",
      "spring": "cubic-bezier(0.68, -0.55, 0.265, 1.55)",
      "bounce": "cubic-bezier(0.68, -0.6, 0.32, 1.6)"
    },
    "transitions": {
      "default": {
        "property": "all",
        "duration": "250ms",
        "easing": "cubic-bezier(0.4, 0, 0.2, 1)"
      },
      "colors": {
        "property": "background-color, border-color, color, fill, stroke",
        "duration": "150ms",
        "easing": "cubic-bezier(0.4, 0, 0.2, 1)"
      },
      "transform": {
        "property": "transform",
        "duration": "250ms",
        "easing": "cubic-bezier(0.4, 0, 0.2, 1)"
      },
      "opacity": {
        "property": "opacity",
        "duration": "150ms",
        "easing": "cubic-bezier(0.4, 0, 0.2, 1)"
      }
    },
    "keyframes": {
      "fadeIn": {
        "from": { "opacity": 0 },
        "to": { "opacity": 1 }
      },
      "fadeOut": {
        "from": { "opacity": 1 },
        "to": { "opacity": 0 }
      },
      "slideInUp": {
        "from": { "transform": "translateY(20px)", "opacity": 0 },
        "to": { "transform": "translateY(0)", "opacity": 1 }
      },
      "slideInDown": {
        "from": { "transform": "translateY(-20px)", "opacity": 0 },
        "to": { "transform": "translateY(0)", "opacity": 1 }
      },
      "scaleIn": {
        "from": { "transform": "scale(0.95)", "opacity": 0 },
        "to": { "transform": "scale(1)", "opacity": 1 }
      },
      "spin": {
        "from": { "transform": "rotate(0deg)" },
        "to": { "transform": "rotate(360deg)" }
      },
      "pulse": {
        "0%, 100%": { "opacity": 1 },
        "50%": { "opacity": 0.5 }
      }
    },
    "usage": {
      "hoverLift": {
        "transform": "translateY(-2px)",
        "shadow": "lg",
        "duration": "normal",
        "easing": "easeOut"
      },
      "buttonPress": {
        "transform": "scale(0.98)",
        "duration": "fast",
        "easing": "easeIn"
      },
      "modalEnter": {
        "animation": "fadeIn, scaleIn",
        "duration": "normal",
        "easing": "easeOut"
      }
    }
  }
}
```

### 8. Component Specifications

```json
{
  "components": {
    "button": {
      "base": {
        "fontFamily": "sans",
        "fontWeight": 600,
        "borderRadius": "md",
        "transition": "all 150ms cubic-bezier(0.4, 0, 0.2, 1)",
        "cursor": "pointer",
        "display": "inline-flex",
        "alignItems": "center",
        "justifyContent": "center",
        "textDecoration": "none",
        "outline": "none"
      },
      "sizes": {
        "sm": {
          "height": "32px",
          "paddingX": "12px",
          "paddingY": "6px",
          "fontSize": "14px",
          "iconSize": "16px",
          "gap": "6px"
        },
        "md": {
          "height": "40px",
          "paddingX": "16px",
          "paddingY": "8px",
          "fontSize": "16px",
          "iconSize": "20px",
          "gap": "8px"
        },
        "lg": {
          "height": "48px",
          "paddingX": "24px",
          "paddingY": "12px",
          "fontSize": "18px",
          "iconSize": "24px",
          "gap": "10px"
        }
      },
      "variants": {
        "primary": {
          "default": {
            "background": "colors.brand.primary.DEFAULT",
            "color": "colors.text.inverse",
            "border": "none",
            "shadow": "none"
          },
          "hover": {
            "background": "colors.brand.primary.600",
            "transform": "translateY(-1px)",
            "shadow": "md"
          },
          "active": {
            "background": "colors.brand.primary.700",
            "transform": "translateY(0)",
            "shadow": "sm"
          },
          "focus": {
            "outline": "2px solid colors.brand.primary.500",
            "outlineOffset": "2px"
          },
          "disabled": {
            "background": "colors.neutral.300",
            "color": "colors.neutral.500",
            "cursor": "not-allowed",
            "opacity": 0.6
          }
        },
        "secondary": {
          "default": {
            "background": "transparent",
            "color": "colors.brand.primary.DEFAULT",
            "border": "1px solid colors.brand.primary.DEFAULT"
          },
          "hover": {
            "background": "colors.brand.primary.50",
            "borderColor": "colors.brand.primary.600"
          }
        },
        "ghost": {
          "default": {
            "background": "transparent",
            "color": "colors.brand.primary.DEFAULT",
            "border": "none"
          },
          "hover": {
            "background": "colors.brand.primary.50"
          }
        },
        "danger": {
          "default": {
            "background": "colors.semantic.error.DEFAULT",
            "color": "colors.text.inverse"
          },
          "hover": {
            "background": "colors.semantic.error.dark"
          }
        }
      }
    },
    "input": {
      "base": {
        "fontFamily": "sans",
        "fontSize": "16px",
        "lineHeight": "normal",
        "borderRadius": "md",
        "border": "1px solid colors.border.DEFAULT",
        "transition": "all 150ms cubic-bezier(0.4, 0, 0.2, 1)",
        "outline": "none"
      },
      "sizes": {
        "sm": {
          "height": "32px",
          "paddingX": "12px",
          "fontSize": "14px"
        },
        "md": {
          "height": "40px",
          "paddingX": "16px",
          "fontSize": "16px"
        },
        "lg": {
          "height": "48px",
          "paddingX": "20px",
          "fontSize": "18px"
        }
      },
      "states": {
        "default": {
          "background": "colors.background.primary",
          "borderColor": "colors.border.DEFAULT",
          "color": "colors.text.primary"
        },
        "focus": {
          "borderColor": "colors.border.focus",
          "outline": "2px solid rgba(14, 165, 233, 0.2)",
          "outlineOffset": "0"
        },
        "error": {
          "borderColor": "colors.semantic.error.DEFAULT",
          "outline": "2px solid rgba(239, 68, 68, 0.2)"
        },
        "disabled": {
          "background": "colors.background.secondary",
          "borderColor": "colors.border.light",
          "color": "colors.text.tertiary",
          "cursor": "not-allowed"
        }
      },
      "placeholder": {
        "color": "colors.text.tertiary",
        "opacity": 0.6
      }
    },
    "card": {
      "base": {
        "background": "colors.background.primary",
        "borderRadius": "lg",
        "border": "1px solid colors.border.light",
        "padding": "24px",
        "transition": "all 250ms cubic-bezier(0.4, 0, 0.2, 1)"
      },
      "variants": {
        "default": {
          "shadow": "sm"
        },
        "elevated": {
          "shadow": "md",
          "border": "none"
        },
        "outlined": {
          "shadow": "none",
          "border": "1px solid colors.border.DEFAULT"
        },
        "interactive": {
          "cursor": "pointer",
          "hover": {
            "shadow": "lg",
            "transform": "translateY(-2px)",
            "borderColor": "colors.brand.primary.200"
          }
        }
      },
      "sections": {
        "header": {
          "marginBottom": "16px",
          "paddingBottom": "16px",
          "borderBottom": "1px solid colors.border.light"
        },
        "body": {
          "marginBottom": "16px"
        },
        "footer": {
          "marginTop": "16px",
          "paddingTop": "16px",
          "borderTop": "1px solid colors.border.light"
        }
      }
    },
    "modal": {
      "backdrop": {
        "background": "colors.background.overlay",
        "backdropFilter": "blur(4px)",
        "zIndex": "zIndex.modalBackdrop"
      },
      "panel": {
        "background": "colors.background.primary",
        "borderRadius": "xl",
        "shadow": "2xl",
        "maxWidth": "500px",
        "padding": "32px",
        "zIndex": "zIndex.modal"
      },
      "animation": {
        "enter": "fadeIn, scaleIn",
        "exit": "fadeOut",
        "duration": "normal"
      }
    },
    "tooltip": {
      "background": "colors.neutral.900",
      "color": "colors.text.inverse",
      "fontSize": "14px",
      "padding": "8px 12px",
      "borderRadius": "md",
      "shadow": "lg",
      "maxWidth": "200px",
      "zIndex": "zIndex.tooltip"
    },
    "badge": {
      "base": {
        "display": "inline-flex",
        "alignItems": "center",
        "fontSize": "12px",
        "fontWeight": 600,
        "paddingX": "8px",
        "paddingY": "4px",
        "borderRadius": "full"
      },
      "variants": {
        "success": {
          "background": "colors.semantic.success.light",
          "color": "colors.semantic.success.dark"
        },
        "error": {
          "background": "colors.semantic.error.light",
          "color": "colors.semantic.error.dark"
        },
        "warning": {
          "background": "colors.semantic.warning.light",
          "color": "colors.semantic.warning.dark"
        },
        "info": {
          "background": "colors.semantic.info.light",
          "color": "colors.semantic.info.dark"
        }
      }
    }
  }
}
```

### 9. Layout Patterns
```json
{
  "layoutPatterns": {
    "hero": {
      "minHeight": "600px",
      "padding": {
        "mobile": "48px 16px",
        "desktop": "96px 48px"
      },
      "textAlign": "center",
      "background": "gradient or image",
      "contentMaxWidth": "800px"
    },
    "section": {
      "padding": {
        "mobile": "48px 16px",
        "desktop": "96px 48px"
      },
      "marginBottom": "64px"
    },
    "container": {
      "maxWidth": "1440px",
      "margin": "0 auto",
      "padding": {
        "mobile": "0 16px",
        "tablet": "0 32px",
        "desktop": "0 48px"
      }
    },
    "grid": {
      "twoColumn": {
        "mobile": "1fr",
        "tablet": "1fr 1fr",
        "gap": "24px"
      },
      "threeColumn": {
        "mobile": "1fr",
        "tablet": "1fr 1fr",
        "desktop": "1fr 1fr 1fr",
        "gap": "24px"
      },
      "fourColumn": {
        "mobile": "1fr",
        "tablet": "1fr 1fr",
        "desktop": "1fr 1fr 1fr 1fr",
        "gap": "24px"
      }
    }
  }
}
```

### 10. Accessibility Standards
```json
{
  "accessibility": {
    "contrast": {
      "normalText": "4.5:1 minimum",
      "largeText": "3:1 minimum",
      "uiComponents": "3:1 minimum"
    },
    "focusIndicators": {
      "outline": "2px solid colors.border.focus",
      "outlineOffset": "2px",
      "visible": true
    },
    "touchTargets": {
      "minimum": "44px x 44px",
      "recommended": "48px x 48px"
    },
    "motion": {
      "respectPrefersReducedMotion": true,
      "fallback": "Disable animations for users who prefer reduced motion"
    },
    "semanticHTML": {
      "required": true,
      "examples": ["Use <button> for buttons", "Use <a> for links", "Use headings hierarchically"]
    }
  }
}
```

### 11. Icon System
```json
{
  "icons": {
    "library": "lucide-react | heroicons | custom",
    "sizes": {
      "xs": "12px",
      "sm": "16px",
      "md": "20px",
      "lg": "24px",
      "xl": "32px"
    },
    "strokeWidth": {
      "thin": 1,
      "normal": 1.5,
      "thick": 2
    },
    "usage": {
      "inline": "Align with text baseline",
      "standalone": "Center in container"
    }
  }
}
```

### 12. Usage Guidelines
```json
{
  "usageGuidelines": {
    "whenToBuild": {
      "newFeature": [
        "1. Reference this design-system.json file",
        "2. Use exact color values from the palette",
        "3. Use spacing scale values (never arbitrary spacing)",
        "4. Apply typography styles from textStyles",
        "5. Implement all component states (hover, focus, active, disabled)",
        "6. Follow animation guidelines",
        "7. Ensure responsive behavior matches breakpoints",
        "8. Meet accessibility standards"
      ]
    },
    "doAndDont": {
      "do": [
        "Use design tokens instead of hardcoded values",
        "Implement all interactive states",
        "Follow spacing scale consistently",
        "Use semantic color names",
        "Test on multiple breakpoints",
        "Ensure keyboard navigation works"
      ],
      "dont": [
        "Create new colors outside the palette",
        "Use arbitrary spacing values",
        "Skip hover/focus states",
        "Ignore accessibility guidelines",
        "Mix different animation durations randomly"
      ]
    },
    "decisionTree": {
      "choosingButton": {
        "primaryAction": "Use primary variant",
        "secondaryAction": "Use secondary variant",
        "destructiveAction": "Use danger variant",
        "lowEmphasis": "Use ghost variant"
      },
      "choosingShadow": {
        "card": "Use elevation level1",
        "cardHover": "Use elevation level2",
        "dropdown": "Use elevation level2",
        "modal": "Use elevation level3"
      }
    }
  }
}
```

## Implementation Instructions

1. **Analyze the existing app thoroughly**:
   - Inspect all existing components and pages
   - Extract exact color values, spacing, typography
   - Document all interactive states
   - Identify animation patterns
   - Note responsive behavior

2. **Create consistent token system**:
   - Group similar values (e.g., all blues together)
   - Create progressive scales (50-900 for colors, 1-32 for spacing)
   - Name tokens semantically (primary, secondary, not blue-500, red-600)

3. **Document component anatomy**:
   - Break down each component into base styles + variants
   - Document all states (default, hover, active, focus, disabled)
   - Specify exact measurements (height, padding, font-size)

4. **Add usage context**:
   - When to use each variant
   - Common patterns and layouts
   - Do's and don'ts

5. **Ensure consistency**:
   - Same values should reference same tokens
   - Similar components should share base styles
   - Animation timing should be consistent across similar interactions

## Success Criteria

The design-system.json file is successful if:
- Any AI can build new features visually consistent with existing app
- No hardcoded values needed (everything references tokens)
- All interactive states are documented
- Responsive behavior is clear
- Accessibility standards are met
- Design decisions have clear rationale
- File serves as single source of truth

## Final Output Structure

```bash
design/
├── design-system.json       (Main file - comprehensive as outlined above)
├── README.md               (Documentation on how to use the design system)
└── examples/               (Optional: Code examples of common patterns)
    ├── button-examples.tsx
    ├── card-examples.tsx
    └── form-examples.tsx
```

This design system should be treated as the **architectural blueprint** for all UI development in this project. Every new component, page, or feature should strictly adhere to the specifications in this file to maintain visual consistency and brand integrity.
</details>

--- 

## Y la hora de implementar una nueva feature con este ecosistema creado

```
Build [FEATURE NAME] following design-system.json strictly. Non-negotiables: Read design-system.json first, use design tokens ONLY (colors/spacing/typography/effects), implement all interactive states, mobile-first responsive, accessible. Structure: clean component code, styles with design tokens only, works on all breakpoints, keyboard navigable. Provide: component code, styles, usage example, design decisions (which tokens used and why). Must be visually consistent with existing app - zero design drift allowed.
```

<details>
<summary>Version Mejorada para usar el Prompt de aplicacion</summary>

# New Feature Implementation Prompt

Implement [FEATURE NAME] following the design system strictly. Build this feature to be visually indistinguishable from existing components.

## Non-Negotiable Rules

1. **ALWAYS reference `design/design-system.json`** - Read it first before writing any code
2. **ZERO hardcoded values** - Every color, spacing, font must come from design tokens
3. **ALL interactive states required** - default, hover, active, focus, disabled
4. **Responsive by default** - Mobile-first, test all breakpoints
5. **Accessible** - Semantic HTML, keyboard nav, ARIA when needed

## Implementation Checklist

### Before You Code
- [ ] Read the relevant sections in `design/design-system.json`
- [ ] Identify which existing components you can reuse
- [ ] Note the breakpoints and responsive behavior needed

### Code Requirements
- [ ] Use design tokens only (no `#0ea5e9`, use `colors.brand.primary.DEFAULT`)
- [ ] Use spacing scale (no `padding: 23px`, use `spacing.6` = 24px)
- [ ] Apply correct typography style (h1, h2, body, etc.)
- [ ] Implement all 5 interactive states (default, hover, active, focus, disabled)
- [ ] Add transitions (duration from `animation.duration`, easing from `animation.easing`)
- [ ] Apply correct shadow elevation level
- [ ] Use proper border-radius from the scale

### Component Structure
```
features/
└── [feature-name]/
    ├── [FeatureName].tsx           # Main component
    ├── [FeatureName].module.css    # Styles (design tokens only)
    ├── components/                 # Sub-components if needed
    │   └── [SubComponent].tsx
    └── index.ts                    # Exports
```

### Styling Rules
```css
/* ✅ CORRECT - Uses design tokens */
.button {
  background: var(--color-primary-500);
  padding: var(--spacing-4) var(--spacing-6);
  border-radius: var(--radius-md);
  font-size: var(--text-base);
  transition: all var(--duration-normal) var(--easing-ease-out);
}

.button:hover {
  background: var(--color-primary-600);
  transform: translateY(-2px);
  box-shadow: var(--shadow-md);
}

/* ❌ WRONG - Hardcoded values */
.button {
  background: #0ea5e9;
  padding: 16px 24px;
  border-radius: 8px;
  font-size: 16px;
  transition: all 0.25s ease-out;
}
```

## Quality Gates

Your implementation must pass these checks:

### Visual Consistency
- [ ] Colors match existing components exactly
- [ ] Spacing feels natural and consistent with the app
- [ ] Typography hierarchy is correct
- [ ] Shadows and effects match existing patterns
- [ ] Animations feel the same as other interactions

### Technical Quality
- [ ] No console errors or warnings
- [ ] Works on mobile, tablet, desktop
- [ ] Keyboard navigation works
- [ ] Loading states handled (if applicable)
- [ ] Error states handled (if applicable)

### Code Quality
- [ ] Clean, readable code
- [ ] Reuses existing components where possible
- [ ] No duplicate code
- [ ] Properly typed (if using TypeScript)
- [ ] Follows project's file structure

## Common Patterns Reference

### Using Buttons
```tsx
// Primary CTA
<Button variant="primary" size="md">Save Changes</Button>

// Secondary action
<Button variant="secondary" size="md">Cancel</Button>

// Destructive action
<Button variant="danger" size="md">Delete</Button>

// Low emphasis
<Button variant="ghost" size="sm">Learn More</Button>
```

### Using Cards
```tsx
<Card variant="elevated">
  <CardHeader>
    <h3>Card Title</h3>
  </CardHeader>
  <CardBody>
    <p>Card content...</p>
  </CardBody>
  <CardFooter>
    <Button variant="primary">Action</Button>
  </CardFooter>
</Card>
```

### Using Form Inputs
```tsx
<Input
  label="Email"
  type="email"
  placeholder="you@example.com"
  error={errors.email}
  required
/>
```

### Responsive Layout
```tsx
<div className="grid grid-cols-1 md:grid-cols-2 lg:grid-cols-3 gap-6">
  {items.map(item => <Card key={item.id}>{item.content}</Card>)}
</div>
```

## Output Format

Provide:

1. **Component code** (React/Vue/Svelte - whatever the project uses)
2. **Styles** (CSS Modules, Styled Components, or Tailwind - match project style)
3. **Usage example** showing the component in context
4. **Brief explanation** of design decisions (which tokens you used and why)

## Example Output

```tsx
// features/user-profile/UserProfile.tsx
import { Card, Button, Avatar } from '@/components';
import styles from './UserProfile.module.css';

export function UserProfile({ user }) {
  return (
    <Card variant="elevated" className={styles.profileCard}>
      <div className={styles.header}>
        <Avatar src={user.avatar} size="lg" />
        <div className={styles.info}>
          <h2 className={styles.name}>{user.name}</h2>
          <p className={styles.role}>{user.role}</p>
        </div>
      </div>
      
      <div className={styles.stats}>
        <Stat label="Projects" value={user.projects} />
        <Stat label="Tasks" value={user.tasks} />
        <Stat label="Completed" value={user.completed} />
      </div>
      
      <div className={styles.actions}>
        <Button variant="primary" size="md">Edit Profile</Button>
        <Button variant="ghost" size="md">View Activity</Button>
      </div>
    </Card>
  );
}
```

```css
/* features/user-profile/UserProfile.module.css */
.profileCard {
  padding: var(--spacing-8);
}

.header {
  display: flex;
  align-items: center;
  gap: var(--spacing-4);
  margin-bottom: var(--spacing-6);
}

.info {
  flex: 1;
}

.name {
  font-size: var(--text-2xl);
  font-weight: var(--font-bold);
  color: var(--color-text-primary);
  margin: 0 0 var(--spacing-1) 0;
}

.role {
  font-size: var(--text-base);
  color: var(--color-text-secondary);
  margin: 0;
}

.stats {
  display: grid;
  grid-template-columns: repeat(3, 1fr);
  gap: var(--spacing-6);
  margin-bottom: var(--spacing-6);
  padding: var(--spacing-6) 0;
  border-top: 1px solid var(--color-border-light);
  border-bottom: 1px solid var(--color-border-light);
}

.actions {
  display: flex;
  gap: var(--spacing-3);
  flex-wrap: wrap;
}

/* Responsive */
@media (max-width: 768px) {
  .header {
    flex-direction: column;
    text-align: center;
  }
  
  .stats {
    grid-template-columns: 1fr;
    gap: var(--spacing-4);
  }
  
  .actions {
    flex-direction: column;
  }
  
  .actions button {
    width: 100%;
  }
}
```

**Design Decisions:**
- Used `Card variant="elevated"` for subtle lift (elevation level 1)
- Spacing scale: 8 (32px) for card padding, 6 (24px) for section spacing, 4 (16px) for element gaps
- Typography: 2xl for name (prominent), base for role (secondary)
- Colors: Primary text for name, secondary for role, border-light for dividers
- Responsive: Stack vertically on mobile, horizontal on desktop
- Actions: Primary button for main action, ghost for secondary

## Quick Reference

| Need | Use |
|------|-----|
| Primary action button | `variant="primary"` |
| Form input | `<Input>` with label, error props |
| Content container | `<Card>` with appropriate variant |
| Small spacing | `spacing.2` (8px) or `spacing.3` (12px) |
| Medium spacing | `spacing.4` (16px) or `spacing.6` (24px) |
| Large spacing | `spacing.8` (32px) or `spacing.12` (48px) |
| Heading | Use predefined textStyles (h1-h6) |
| Hover lift effect | `transform: translateY(-2px)` + shadow upgrade |
| Quick transition | `duration.fast` (150ms) |
| Standard transition | `duration.normal` (250ms) |

---

**What I'm building:** [Describe your feature here]

**Attach:** `design/design-system.json` file
</details>



