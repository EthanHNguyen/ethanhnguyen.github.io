---
version: alpha
name: Ethan Nguyen Professional Brand
description: Dark, precise, high-trust frontier AI systems identity for a public personal website.
colors:
  primary: "#08090A"
  secondary: "#D0D6E0"
  tertiary: "#5E6AD2"
  neutral: "#0F1115"
  success: "#007A33"
typography:
  h1:
    fontFamily: Inter
    fontSize: 4.5rem
    fontWeight: 600
    lineHeight: 0.98
    letterSpacing: "-0.04em"
  h2:
    fontFamily: Inter
    fontSize: 1.18rem
    fontWeight: 560
    lineHeight: 1.2
    letterSpacing: "0.12em"
  body-md:
    fontFamily: Inter
    fontSize: 1.02rem
    fontWeight: 400
    lineHeight: 1.72
  mono-label:
    fontFamily: JetBrains Mono
    fontSize: 0.68rem
    fontWeight: 500
    lineHeight: 1.6
    letterSpacing: "0.16em"
rounded:
  sm: 6px
  md: 14px
  lg: 22px
spacing:
  sm: 8px
  md: 16px
  lg: 24px
components:
  hero-panel:
    backgroundColor: "{colors.primary}"
    textColor: "#F7F8F8"
    rounded: "{rounded.lg}"
    padding: 34px
  ghost-button:
    backgroundColor: "{colors.neutral}"
    textColor: "{colors.secondary}"
    rounded: 999px
    padding: 10px
  primary-link:
    backgroundColor: "{colors.tertiary}"
    textColor: "#FFFFFF"
    rounded: "{rounded.sm}"
    padding: 8px
  trust-pill:
    backgroundColor: "{colors.success}"
    textColor: "#FFFFFF"
    rounded: 999px
    padding: 6px
---

## Overview

This design system positions Ethan Nguyen as a frontier AI systems builder: technical, precise, founder-oriented, and OPSEC-aware. The site should feel like high-trust infrastructure rather than a generic academic portfolio.

The visual language combines Linear-style dark precision with government/high-trust restraint. It should signal systems judgment, operational trust, and frontier AI proximity without implying access to sensitive details.

## Colors

- **Primary (#08090A):** Near-black canvas for depth, focus, and technical seriousness.
- **Neutral (#0F1115):** Elevated panels and navigation surfaces.
- **Secondary (#D0D6E0):** Main body text, bright enough for accessibility without pure-white glare.
- **Tertiary (#5E6AD2):** Frontier AI accent for links, nav indicators, and glow.
- **Success (#007A33):** High-trust/government green used sparingly as a secondary signal.

## Typography

Inter is the primary font. Use tight tracking for major headlines and controlled weights rather than heavy bold. JetBrains Mono is reserved for technical labels, metadata, and the hero overline.

Headlines should be short, thesis-driven, and high-signal. Section headings can use uppercase `//` treatment to imply systems documentation without turning the page into a terminal theme.

## Layout

Use a dark native layout with translucent panels, subtle borders, and generous whitespace. The homepage hero should be the strongest visual moment, followed by readable text sections and compact project proof.

Maintain a restrained content width so the site feels editorial and credible, not like a SaaS landing page.

## Elevation & Depth

On dark surfaces, elevation comes from luminance, borders, and subtle glow, not heavy drop shadows. Use translucent cards with `rgba(255,255,255,0.03–0.06)` and borders around `rgba(255,255,255,0.06–0.09)`.

## Shapes

Use precise rounded surfaces: small pills for controls, medium radius for images/cards, and a large rounded hero panel. Avoid playful blobs or excessive gradients.

## Components

- **Hero panel:** Large dark card with subtle gradient, border, and mono taxonomy line.
- **Navigation:** Sticky dark glass header with compact links and a small gradient brand dot.
- **Sidebar:** Muted profile card behavior; headshot gets subtle border and shadow.
- **Archive cards:** Dark translucent cards with small lift on hover.
- **Footer:** Dark, quiet, and subordinate to the main content.

## Do's and Don'ts

Do:

- Signal operational trust, evaluation, infrastructure, and systems judgment.
- Keep the theme dark, precise, and restrained.
- Use accent colors sparingly.
- Preserve readability and OPSEC-friendly abstraction.

Don't:

- Use generic academic white-page styling.
- Overuse neon/cyberpunk effects.
- Make the site feel like a sales landing page.
- Add sensitive deployment language or access signals.
