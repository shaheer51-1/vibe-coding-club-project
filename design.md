# Design System & UI/UX Guidelines (design.md)
## VibeForge 2.0 — Visual Identity, Tokens & Component Specifications

**Document Version:** 1.0.0  
**Phase:** Phase 1 (Foundation & UI)  
**Author:** Antigravity Senior Product Designer & UI Architect  

---

### 1. Visual Direction & Principles

VibeForge 2.0 embodies a **High-Performance Developer Studio Aesthetic**:
- **Dark, Focused Atmosphere:** Deep charcoal surfaces minimize eye strain and elevate code and live preview contrast.
- **Electric Precision Accents:** Violet (`#8b5cf6`) and Electric Blue (`#3b82f6`) signal intelligence, velocity, and creativity.
- **Glassmorphism & Depth:** Layered translucent panels (`rgba(18, 22, 34, 0.75)` with `backdrop-filter: blur(12px)`) provide tactile spatial hierarchy without visual clutter.
- **Deliberate Micro-Interactions:** Subtle scale transitions (`scale-105`), ambient borders, and smooth viewport transitions create a responsive, living feel.

---

### 2. Design Tokens

#### 2.1 Color Palette

| Token Name | Hex Code | Utility Class | Purpose |
| :--- | :--- | :--- | :--- |
| **Canvas Background** | `#0b0d13` | `bg-charcoal-900` | Global application backdrop |
| **Card / Surface Base**| `#121622` | `bg-surface-800` | Workspace cards, sidebar background |
| **Panel Surface High** | `#181e2e` | `bg-surface-700` | Modals, elevated dialogs, active tabs |
| **Border Subtle** | `rgba(255, 255, 255, 0.08)` | `border-white/10` | Default card borders and dividers |
| **Border Active / Focus**| `#8b5cf6` | `border-violet-500` | Focused inputs, active file selection |
| **Accent Primary (Violet)**| `#8b5cf6` | `bg-violet-600` | Primary buttons, brand logo gradient |
| **Accent Electric (Blue)**| `#3b82f6` | `bg-blue-500` | Viewport controls, secondary highlights |
| **Accent Cyan** | `#06b6d4` | `bg-cyan-500` | Status badges, live preview indicators |
| **Text Primary** | `#f8fafc` | `text-slate-100` | High-emphasis headers, active code |
| **Text Muted** | `#94a3b8` | `text-slate-400` | Subtitles, labels, file paths |
| **Text Faint** | `#64748b` | `text-slate-500` | Placeholder text, line numbers |

#### 2.2 Typography Scale
- **Font Family:** `Inter`, system-ui, -apple-system, sans-serif. Monospace font: `ui-monospace`, `Consolas`, monospace.
- **Headings:**
  - `Display / H1`: `2.25rem` (36px), font-bold, tracking-tight.
  - `H2 (Section Titles)`: `1.5rem` (24px), font-semibold.
  - `H3 (Card Titles)`: `1.125rem` (18px), font-medium.
- **Body & Controls:**
  - `Body Regular`: `0.875rem` (14px), font-normal, line-height 1.5.
  - `Small / Badge`: `0.75rem` (12px), font-medium, tracking-wide.
  - `Code / Monospace`: `0.8125rem` (13px), font-mono, line-height 1.6.

#### 2.3 Radii & Elevation
- **Card Radius:** `rounded-xl` (12px)
- **Button Radius:** `rounded-lg` (8px)
- **Pill / Tag Radius:** `rounded-full` (9999px)
- **Elevations (Shadows):**
  - Subtle Card: `0 4px 20px -2px rgba(0, 0, 0, 0.5)`
  - Active Glow: `0 0 25px -5px rgba(139, 92, 246, 0.35)`

---

### 3. Core UI Components

#### 3.1 Primary Action Button
- **Gradient:** `linear-gradient(135deg, #8b5cf6 0%, #3b82f6 100%)`
- **States:**
  - Hover: `filter: brightness(1.15); transform: translateY(-1px);`
  - Active: `transform: translateY(0); filter: brightness(0.95);`
  - Disabled: `opacity: 0.45; cursor: not-allowed; filter: grayscale(0.5);`
  - Focus Ring: `ring-2 ring-violet-400 ring-offset-2 ring-offset-[#0b0d13]`

#### 3.2 Viewport Switcher Controls
Segmented button group housing three responsive modes:
- **Desktop:** Monitor icon with `"Desktop"` label (or icon only on small screens).
- **Tablet:** Tablet icon with `"Tablet (768px)"` indicator.
- **Mobile:** Smartphone icon with `"Mobile (375px)"` indicator.
- **Active State:** Solid violet background with bright white icon and high-contrast text.

#### 3.3 Device Mockup Frame
When switching the central preview to Tablet or Mobile:
- The preview canvas transitions with `transition-all duration-300 ease-out`.
- Mobile mode features a simulated phone top-speaker notch and sleek rounded outer bezel (`rounded-[32px]` with a 1px border and soft drop shadow).

#### 3.4 Tokenized Code Viewer
- Left gutter with muted right-aligned line numbers.
- Syntax highlighting tone:
  - HTML tags: `#60a5fa` (Soft Blue)
  - Attributes: `#c084fc` (Soft Violet)
  - Strings: `#34d399` (Mint Green)
  - Comments: `#64748b` (Slate Muted)
- Header toolbar displaying active filename, file size, line count, and a `"Copy Code"` action.

---

### 4. Accessibility & Contrast Verification

- **Color Contrast:** All body text (`#f8fafc` on `#0b0d13`) exceeds `15:1` contrast ratio (far surpassing WCAG AAA requirement of 7:1).
- **Focus Rings:** Visible high-contrast violet rings on all interactive elements.
- **Keyboard Navigation:** Full tab order across navigation, search, create buttons, and builder tabs.
- **Semantic HTML:** Semantic landmark tags (`<header>`, `<main>`, `<nav>`, `<section>`, `<aside>`) used throughout.
