# DESIGN.md: Silvio Schäfer | Training & Coaching

## 1. Brand Identity & Design Read

**Reading this as:** High-ticket executive performance & hormonal optimization coaching platform for entrepreneurs and executives, crafted in a dark, architectural **Bio-Mechanical Luxury** visual language.

- **Dials (Desktop):** `ENERGY 3 / RHYTHM 3 / MOTION 3` (Story-driven scroll choreography, living Power Signet state machine, orbital 5-pillar system stage, interactive split transformation comparison).
- **Dials (Mobile <= 900px):** `ENERGY 2 / RHYTHM 2 / MOTION 2` (Streamlined, thumb-ergonomic vertical flow, native momentum horizontal snap-carousel for the 5 pillars, zero scroll-fatigue).
- **Core Visual Motif:** The **Silvio Schäfer Power Signet** (open circular arc + vertical ignition bar). On desktop, it acts as a continuous, physically tracked living element that discharges across the 5 Status Quo symptoms, glides to center stage, recharges in liquid orange across the 3 Prime Code™ phases, and docks into the interactive Orbital Hub CTA.

---

## 2. Color Schema & Semantic Tokens

The palette is strictly capped at **2 core dark surfaces + 1 deliberate high-energy accent** (`#FF6D29`), paired with high-contrast neutral typography to guarantee WCAG AA/AAA legibility across all states.

### Core Palette Tokens

| Token | Hex / Value | Role & Written Purpose (R-01, R-29, R-31) |
| :--- | :--- | :--- |
| `--bg-dark` | `#171217` | Primary obsidian-plum canvas ("Unser Schwarz" from brand moodboard). Grounds the interface with warm dark depth rather than sterile pure black. |
| `--bg-deep` | `#141014` | Alternating architectural section backdrop (Authority & Footer) to create subtle structural separation without harsh borders. |
| `--bg-surface` | `#1E1A1E` | Elevated Bento card and module fill. Separates interactive containers from the primary canvas. |
| `--bg-card` | `#1B161B` | High-focus application form and testimonial container surface. |
| `--color-accent` | `#FF6D29` | **Performance Orange** (Brand Accent). Reserved strictly for primary conversion actions, active state indicators, and the living Power Signet ignition. |
| `--color-accent-hover` | `#FF7E42` | Luminous hover/active state for primary CTAs and interactive controls. |
| `--color-danger-drain` | `#E04A26` | Critical low-energy indicator when the Power Signet drains below 20% in the Status Quo section. |

### Typography & Contrast Tokens (WCAG AA Verified, R-25)

| Token | Hex / Value | Contrast vs `#171217` | Usage |
| :--- | :--- | :--- | :--- |
| `--text-white` | `#FFFFFF` | **18.6 : 1** (AAA) | Headlines (`h1`–`h4`), active symptom copy, primary metrics. |
| `--text-secondary` | `#D4D0D2` | **12.1 : 1** (AAA) | Lead paragraphs, body copy, card descriptions. |
| `--text-muted` | `#8E898C` | **5.4 : 1** (AA) | Metadata, eyebrows, subtle hints, form labels. |
| `--text-on-accent` | `#0D090C` | **6.58 : 1** vs `#FF6D29` (AA) | Ultra-crisp dark ink on Performance Orange CTA buttons for maximum legibility. |

### Surface, Border & Glass Tokens (R-10, R-12, R-13)

```css
:root {
  --border-subtle: rgba(255, 255, 255, 0.08);
  --border-elevated: rgba(255, 255, 255, 0.14);
  --border-accent: rgba(255, 109, 41, 0.45);
  --glass-header: rgba(23, 18, 23, 0.88);
  --shadow-card: 0 24px 60px rgba(0, 0, 0, 0.65);
  --shadow-cta: 0 8px 24px rgba(255, 109, 41, 0.35);
  --shadow-cta-hover: 0 12px 32px rgba(255, 109, 41, 0.55);
}
```
- **Glassmorphism Dose Cap (R-10):** `backdrop-filter: blur()` is restricted to the fixed navigation header (`18px`) and the orbital satellite cards (`20px`) so foreground hierarchy remains sharp.
- **Glow Dose Cap (R-13):** Ambient orange glow is restricted to the living Power Signet and active conversion focal points.

---

## 3. Typography System

- **Brand Font Family (`--font-brand`):** `'Montserrat', sans-serif` (weights: `300` Light, `400` Regular, `500` Medium, `600` SemiBold, `700` Bold, `800` ExtraBold).
- **Reason (R-06):** Preserves the established Silvio Schäfer corporate identity; geometric precision in `800` weight headlines conveys executive authority, while `400` weight body copy with generous line-height (`1.65`–`1.75`) ensures effortless reading.

### Responsive Type Scale

| Element | Desktop (`> 1100px`) | Tablet (`901px–1100px`) | Mobile (`<= 900px`) | Line-Height / Tracking |
| :--- | :--- | :--- | :--- | :--- |
| **Hero H1 (`.hero-headline`)** | `64px` (`800`) | `48px` (`800`) | `clamp(26px, 7.2vw, 34px)` | `1.12` / `0.015em` (`text-wrap: balance`) |
| **Section H2 (`.minimal-section-title`, `.story-title`, `.results-title`)** | `48px` (`800`) | `36px–42px` (`800`) | `clamp(23px, 6.2vw, 28px)` | `1.15` / `-0.01em` (`text-wrap: balance`) |
| **Symptom / Phase H3 (`.point-title`, `.story-phase-title`)** | `34px–40px` (`800`) | `28px–32px` (`800`) | `15.5px–16.5px` (`700`) | `1.22` / `0.01em` |
| **Bento / Orbital Card H4 (`.card-title`)** | `16px` (`700`) | `15px` (`700`) | `15px` (`700`) | `1.25` / `0.01em` |
| **Lead / Body Copy (`.hero-subline`, `.story-lead`, `.results-lead`)** | `18px` (`400`) | `16px–17px` (`400`) | `13.5px` (`400`) | `1.7` (Desktop) / `1.55` (Mobile) |
| **Section Eyebrow (`.minimal-eyebrow`)** | `13px` (`700`) | `12px` (`700`) | `11px` (`700`) | Uppercase, `0.12em` tracking |
| **Form Controls (`.contact-control`)** | `15px` (`400`) | `15px` (`400`) | `16px` (`400`, prevents iOS auto-zoom) | `1.5` |

---

## 4. Layout, Bento Architecture & Spacing System

### Structural Rhythm & Asymmetric Composition (R-05, R-14)
Every section uses a distinct layout tailored to its narrative role rather than repeating a uniform template:
1. **Hero Stage (`#top`):** Full-viewport (`100dvh`) asymmetric portrait stage with multi-layered cinematic vignette, left-aligned typographic focal point, and tactile hardware-inspired Toggle-Switch CTA (`.btn-toggle-switch`).
2. **Status Quo (`#system`):** 2-column asymmetric split (`minmax(360px, 460px) 1fr`). Left column houses the sticky discharging Power Signet; right column houses 5 proximity-illuminated symptom blocks tracked by a vertical wandering laser line (`#wanderingLine`).
3. **Der Wendepunkt / Prime Code™ (`#prime-code`):**
   - **Desktop:** `500vh` pinned scroll-scrubbed stage where the Power Signet glides to center, ignites, and recharges across 3 chronological phases (`Fundamentals`, `Momentum`, `Mastery`), culminating in the **Orbital 5-Pillar Bento Stage** (`Blutanalyse`, `Training`, `Ernährung`, `Schlaf`, `Stressmanagement`) radiating around the central Round Power Hub CTA.
   - **Mobile (`<= 900px`):** Unpinned, zero-fatigue editorial flow (`height: auto`). Overhead statements become pure typographic quotes, the 3 phases render as compact roadmap Bento cards, and the 5 pillars transform into a hardware-accelerated horizontal momentum `scroll-snap` carousel.
4. **Ergebnisse & Social Proof (`#ergebnisse`):** Asymmetric Bento Dual-Stage (`minmax(320px, 520px) 1fr`). Left cell features a `1:1` interactive drag-split Before/After transformation showcase (10 real client pairs with progress dots); right cell stacks 2 horizontal inline-playable video testimonial Bento cards (`Helge Sidow`, `Gerhard Stichauner`), anchored by a grayscale-to-color executive client logo bar below.
5. **Über Silvio (`#ueber-silvio`):** Editorial 2-column authority split (`minmax(340px, 440px) 1fr`) pairing a `4:5` portrait card with Silvio's personal founder narrative (*"Ich bin nicht der Coach. Ich bin der Kunde."*).
6. **Warteliste / Bewerbung (`#kontakt`):** High-conversion 2-column split (`1fr 1.15fr`) combining scarcity framing with an interactive goal-chip selector (`aria-pressed` toggle pills) and inline validation/success state.

### Spacing & Breakpoint Tokens

| Context | Section Vertical Padding | Container Max-Width | Horizontal Padding | Grid Gap |
| :--- | :--- | :--- | :--- | :--- |
| **Desktop (`> 1100px`)** | `120px–130px` | `1540px` (Hero/System) / `1400px` (Results) / `1240px` (Contact) | `32px` | `48px–120px` |
| **Tablet (`901px–1100px`)** | `90px–100px` | `100%` | `32px` | `36px–48px` |
| **Mobile (`<= 900px`)** | `36px–48px` | `100vw` (`overflow-x: clip`) | `16px` + `env(safe-area-inset-*)` | `14px–22px` |

### Border Radius Hierarchy (R-11)
- **Cards & Bento Containers:** `14px–16px` (Desktop), `12px` (Mobile)
- **Form Inputs:** `6px` (distinct from buttons and cards)
- **Phase Tags:** `4px` (sharp technical badge)
- **Primary Action Buttons & Toggle Switch:** `9999px` (tactile pill/switch geometry)

---

## 5. Micro-Interactions, Motion & Accessibility Rules

1. **Spring Physics Curve:** All interactive transitions use `cubic-bezier(0.16, 1, 0.3, 1)` for responsive, weightless feedback.
2. **Hero Toggle-Switch CTA (`.btn-toggle-switch`):** On hover/focus, the metallic track ignites into `#FF6D29`, the power-signet knob slides across the track with a `360deg` rotation, and the label shifts from light to high-contrast dark ink.
3. **Luminous Section Horizons (`.section-horizon-wrap`):** Scroll-triggered `1px` center-outward gradient lines (`scaleX(0)` -> `scaleX(1)`) introduce major sections without heavy box borders.
4. **Touch & Mobile Ergonomics (R-03):**
   - All interactive controls enforce a minimum `44px × 44px` tap target on mobile.
   - Touch feedback uses `:active { transform: scale(0.96); }`.
   - Mouse-following ambient glow (`#mouse-glow`) is automatically disabled on touch/mobile viewports and when `prefers-reduced-motion: reduce` is active.
5. **Keyboard & Screen Reader Accessibility (R-32):**
   - Every interactive element (`a`, `button`, `input`, `[role="button"]`, `.contact-chip`) displays a high-visibility `2px solid var(--color-accent)` focus ring on `:focus-visible`.
   - Mobile navigation overlay supports `Escape` key dismissal and `aria-expanded` / `aria-hidden` state synchronization.
