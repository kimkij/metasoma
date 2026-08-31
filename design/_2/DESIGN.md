---
name: Serene Logic
colors:
  surface: '#f7f9ff'
  surface-dim: '#cbdcee'
  surface-bright: '#f7f9ff'
  surface-container-lowest: '#ffffff'
  surface-container-low: '#ecf4ff'
  surface-container: '#e2efff'
  surface-container-high: '#d9eafc'
  surface-container-highest: '#d4e4f6'
  on-surface: '#0d1d2a'
  on-surface-variant: '#43483d'
  inverse-surface: '#223240'
  inverse-on-surface: '#e7f2ff'
  outline: '#74796c'
  outline-variant: '#c4c8ba'
  surface-tint: '#486730'
  primary: '#486730'
  on-primary: '#ffffff'
  primary-container: '#87a96b'
  on-primary-container: '#213d0b'
  inverse-primary: '#aed18f'
  secondary: '#5c5d6e'
  on-secondary: '#ffffff'
  secondary-container: '#e1e1f5'
  on-secondary-container: '#626374'
  tertiary: '#5e604d'
  on-tertiary: '#ffffff'
  tertiary-container: '#9fa08a'
  on-tertiary-container: '#353726'
  error: '#ba1a1a'
  on-error: '#ffffff'
  error-container: '#ffdad6'
  on-error-container: '#93000a'
  primary-fixed: '#c9eea9'
  primary-fixed-dim: '#aed18f'
  on-primary-fixed: '#0b2000'
  on-primary-fixed-variant: '#314e1b'
  secondary-fixed: '#e1e1f5'
  secondary-fixed-dim: '#c5c5d8'
  on-secondary-fixed: '#191b29'
  on-secondary-fixed-variant: '#444655'
  tertiary-fixed: '#e4e4cc'
  tertiary-fixed-dim: '#c8c8b0'
  on-tertiary-fixed: '#1b1d0e'
  on-tertiary-fixed-variant: '#474836'
  background: '#f7f9ff'
  on-background: '#0d1d2a'
  surface-variant: '#d4e4f6'
typography:
  display-lg:
    fontFamily: Plus Jakarta Sans
    fontSize: 40px
    fontWeight: '700'
    lineHeight: 48px
    letterSpacing: -0.02em
  headline-lg:
    fontFamily: Plus Jakarta Sans
    fontSize: 32px
    fontWeight: '600'
    lineHeight: 40px
    letterSpacing: -0.01em
  headline-md:
    fontFamily: Plus Jakarta Sans
    fontSize: 24px
    fontWeight: '600'
    lineHeight: 32px
  headline-sm:
    fontFamily: Plus Jakarta Sans
    fontSize: 20px
    fontWeight: '600'
    lineHeight: 28px
  body-lg:
    fontFamily: Noto Sans
    fontSize: 18px
    fontWeight: '400'
    lineHeight: 28px
  body-md:
    fontFamily: Noto Sans
    fontSize: 16px
    fontWeight: '400'
    lineHeight: 24px
  body-sm:
    fontFamily: Noto Sans
    fontSize: 14px
    fontWeight: '400'
    lineHeight: 20px
  label-md:
    fontFamily: Noto Sans
    fontSize: 14px
    fontWeight: '600'
    lineHeight: 16px
    letterSpacing: 0.05em
  label-sm:
    fontFamily: Noto Sans
    fontSize: 12px
    fontWeight: '600'
    lineHeight: 14px
    letterSpacing: 0.05em
rounded:
  sm: 0.25rem
  DEFAULT: 0.5rem
  md: 0.75rem
  lg: 1rem
  xl: 1.5rem
  full: 9999px
spacing:
  base: 8px
  xs: 4px
  sm: 12px
  md: 24px
  lg: 40px
  xl: 64px
  gutter: 24px
  margin-mobile: 16px
  margin-desktop: 48px
---

## Brand & Style

The design system is engineered for a psychological counseling environment, prioritizing emotional safety and professional organization. The aesthetic merges **Modern Minimalist** clarity with **Soft Glassmorphism** to create a sense of breathability and lightness. 

The UI should evoke a sense of "digital sanctuary"—where administrative tasks feel less like data entry and more like mindful stewardship. By utilizing translucent layers and an airy color palette, the system reduces the cognitive load on practitioners, allowing them to focus on patient care. The overall personality is empathetic, secure, and impeccably organized.

## Colors

The palette is rooted in nature and tranquility.
- **Primary (Soft Sage Green):** Used for primary actions, success states, and growth-oriented indicators. It represents healing and progress.
- **Secondary (Pastel Lavender):** Used for reflective elements, secondary tags, and creative counseling types. It adds a touch of calm and spiritual wellness.
- **Tertiary (Warm Beige):** Used for container backgrounds and subtle section separators to provide a "paper-like" warmth that avoids the sterility of pure white.
- **Neutral (Slate Gray):** Reserved for high-legibility text and borders to maintain a professional, grounded structure.
- **Background (Soft White):** The canvas for the entire system, providing a clean, bright foundation.

## Typography

This design system utilizes **Plus Jakarta Sans** for headings to introduce a modern, friendly, and soft geometric touch. For body copy and data-heavy interfaces, **Noto Sans** provides maximum legibility and a neutral, professional tone. 

- Use `display-lg` sparingly for dashboard greetings or empty state headlines.
- `label` styles should be set in uppercase when used for table headers or small metadata tags to improve scannability.
- Maintain generous line-heights (1.5x minimum for body text) to ensure content feels approachable and easy to digest during long sessions.

## Layout & Spacing

The layout philosophy follows a **Fluid Grid** model with high internal margins to prevent visual clutter. 

- **Desktop:** 12-column grid with a 24px gutter. Content is centered with a max-width of 1440px.
- **Tablet:** 8-column grid with 24px margins.
- **Mobile:** 4-column grid with 16px margins.

The spacing rhythm is based on an 8px scale. Large "breathable" gaps (`lg` and `xl`) should be used between major sections (e.g., between the header and the main content area) to reinforce the calming atmosphere.

## Elevation & Depth

Depth is communicated through **Glassmorphism** and **Soft Ambient Shadows**.

- **Level 0 (Base):** Soft White (#FFFAFA) background.
- **Level 1 (Cards/Containers):** Warm Beige (#F5F5DC) with a 1px border of 10% Slate Gray. No shadow.
- **Level 2 (Interactive Elements):** 60% opacity white background with a `backdrop-filter: blur(12px)`. Subtle shadow: `0 8px 32px rgba(112, 128, 144, 0.08)`.
- **Level 3 (Modals/Drawers):** Solid white or high-opacity glass. Pronounced shadow: `0 16px 48px rgba(112, 128, 144, 0.15)`.

Avoid harsh black shadows; always tint shadows with the Slate Gray (#708090) palette to maintain a soft, cohesive look.

## Shapes

The shape language is organic and inviting. 
- **Standard Radius:** 16px (0.5rem base in this system's scaling) is the minimum for cards and major UI blocks.
- **Large Radius:** 24px (1.5rem) for main dashboard containers and slide-out drawers.
- **Pill:** Used for buttons and status chips to remove all sharp edges, symbolizing the "softening" of clinical data.

## Components

- **Interactive Cards:** Counseling types (e.g., "Individual," "Group") use 16px rounded corners, a glass effect, and a subtle Sage Green border on hover.
- **Admin Data Tables:** Clean, borderless rows with Soft Beige alternating backgrounds. Headers use `label-sm` in Slate Gray. High horizontal padding (24px) for readability.
- **Slide-out Drawers:** Client details appear from the right. These use a 24px top-left/bottom-left corner radius and a high backdrop blur on the main content to focus the user's attention.
- **Buttons:** Primary buttons are Sage Green with white text, using a pill shape. Secondary buttons use a Sage Green outline with a transparent background.
- **Input Fields:** Soft Beige background, 12px padding, and a 1px Slate Gray (20% opacity) border. On focus, the border transitions to Sage Green with a soft glow.
- **Toast Notifications:** Gentle, floating pills at the bottom center. Use Lavender for info, Sage for success, and a muted coral (secondary color variant) for alerts.
- **Timeline/Journal:** A vertical line component using Lavender dots to mark counseling milestones, emphasizing the journey of the patient.