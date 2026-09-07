# COMPUTE Design System

## Product

COMPUTE is a premium landing page for autonomous AI agents running on distributed computing infrastructure. The design should feel cinematic, technical, confident, and operational rather than playful or SaaS-generic.

## Creative Direction

**Aesthetic:** dark technical editorial with cinematic motion.

The interface combines an almost-black canvas, oversized Instrument Serif headlines, restrained monospace metadata, thin technical rules, and immersive infrastructure imagery. The primary visual signature is the contrast between quiet black-and-white typography and brief spectral color moments used for active agent states and animated words.

Avoid generic dashboard styling, excessive rounded cards, decorative gradients, and unnecessary icons. Every visual should reinforce distributed systems, automation, reliability, or execution.

## Color Palette

Use the existing semantic tokens in `app/globals.css` rather than hard-coded colors wherever possible.

- **Canvas:** near-black blue-black background (`--background`)
- **Text:** warm white (`--foreground`)
- **Muted text:** low-contrast warm gray (`--muted-foreground`)
- **Surface:** slightly lifted charcoal (`--card`, `--secondary`)
- **Rule:** subtle charcoal border (`--border`)
- **Spectral accent:** restrained pink, violet, cyan, and amber used only for animated agent states and live metrics

Keep the palette disciplined. The page should remain primarily monochrome; spectral color is a signal, not a background treatment.

## Typography

Two primary families are used, plus one utility family:

- **Instrument Serif / `font-display`:** hero headlines, section titles, large metrics, testimonials, plan names
- **Instrument Sans / `font-sans`:** body copy, navigation, buttons, labels
- **JetBrains Mono / `font-mono`:** eyebrow labels, technical metadata, status indicators, pricing labels, code/infrastructure details

Typography hierarchy:

- Hero headline: very large, tight leading around `0.9`, left aligned
- Section titles: oversized and editorial, often responsive up to approximately `128px`
- Body copy: readable, muted, relaxed line height
- Metadata: small, uppercase or compact monospace with generous tracking

Use `text-balance` or `text-pretty` for important headings. Never introduce additional font families.

## Layout Principles

- Use a full-width, single-page narrative: navigation → hero → capabilities → process → infrastructure → metrics → integrations → security → developers → testimonials → pricing → CTA → footer.
- Prefer flexbox for one-dimensional layouts and CSS grid for intentional two-dimensional compositions.
- Use a centered content width between `1200px` and `1400px` on large screens.
- Use generous vertical rhythm and let large headlines create the visual pacing.
- Use thin borders and open negative space instead of dense card stacks.
- Avoid arbitrary absolute positioning except for overlays, hero media, navigation layers, and decorative technical lines.
- On mobile, collapse multi-column sections into a clear vertical reading order and preserve generous touch targets.

## Navigation

The navigation is fixed and changes state after scrolling:

- At the top: transparent, spacious, white-on-hero presentation
- After scrolling: compact floating panel with translucent background, blur, border, and shadow
- Desktop: logo, five anchor links, sign-in link, and primary “Deploy agent” CTA
- Mobile: full-screen menu overlay with oversized display-font links and bottom actions

Navigation links should use underline reveals on hover. Maintain visible focus states for keyboard users.

## Hero

The hero is the signature moment of the page:

- Full viewport height with cinematic video background
- Dark left-to-right and bottom overlays for text contrast
- Subtle grid lines suggest an observability or compute grid
- Left-aligned eyebrow in monospace
- Oversized headline: “Distributed compute, agents that [verb]”
- The changing verb uses a staggered blur-to-sharp reveal and spectral color transition
- Bottom-aligned proof points communicate active agents, uptime, and latency

Hero media is atmospheric and subordinate to the headline. Do not allow the video or grid to reduce text legibility.

## Sections and Components

### Capabilities
Present core agent capabilities with strong headings, concise explanations, and minimal supporting UI. Favor interaction states and rhythm over decorative illustration.

### Process
Show the deployment or execution workflow as a clear sequence. Numbering is appropriate here because this is a true process; keep the steps direct and operational.

### Infrastructure
Explain distributed execution with diagrams, system labels, or terminal-like metadata. Use monospace details sparingly to make the system feel real.

### Metrics
Make metrics legible at a glance. Use oversized serif values, compact labels, and restrained live-state accents. Metrics should support the product claim, not act as decoration.

### Integrations
Use a quiet logo/system matrix with consistent sizing and strong alignment. Avoid mixing icon styles or adding unsupported partner marks.

### Security
Use high-contrast editorial typography, certification tags, and feature rows. Security content should feel calm, precise, and trustworthy.

### Developers
Show implementation details with code-like presentation, clear API language, and a direct path to deployment. Keep the visual treatment consistent with the infrastructure section.

### Testimonials
Use large quotes, strong author context, and an understated metric panel. Navigation controls should be simple square or rectangular controls rather than ornamental pills.

### Pricing
Use a three-column comparison on large screens and a stacked layout on mobile. Plans should be separated by thin borders. The highlighted plan may scale subtly and use a solid label, but avoid loud gradients.

### CTA and Footer
End with a decisive deployment invitation. The footer should be quiet, structured, and monospace-led, with clear navigation and product/legal links.

## Motion

Motion should explain state and create confidence:

- Staggered entrance reveals for hero and section content
- Blur-to-sharp transition for rotating hero verbs
- Smooth navigation morph on scroll
- Marquee motion only for meaningful ecosystem or infrastructure content
- Small hover lifts or underline reveals for interactive elements
- Respect `prefers-reduced-motion`; disable continuous and staggered animation where requested

Avoid scattering unrelated micro-interactions across every element.

## Interaction and Accessibility

- Use semantic `header`, `nav`, `main`, `section`, and `footer` elements.
- Every image and meaningful video needs an accessible description or `aria-hidden` when decorative.
- Keep text contrast high against video and dark surfaces.
- All buttons and links need visible keyboard focus states.
- Mobile menu controls require an accessible label and should close after selecting a section.
- Do not rely on color alone to communicate live, active, or selected states.
- Preserve readable body text at all viewport sizes.

## Implementation Rules

- Continue using Next.js App Router and the existing component structure under `components/landing`.
- Use Tailwind semantic color classes such as `bg-background`, `text-foreground`, `border-border`, and `text-muted-foreground`.
- Keep the page composed of focused section components; do not consolidate the entire landing page into one file.
- Reuse existing shadcn primitives where an accessible control is needed.
- Keep the visual system within 3–5 dominant colors and no more than two type families in any new feature.
- Treat the existing landing page as the source of truth for spacing, tone, motion, and responsive behavior.

## Do / Don’t

### Do

- Use oversized editorial typography with precise spacing.
- Use monochrome surfaces and thin technical rules.
- Use spectral color as an intentional status signal.
- Make performance, uptime, latency, and deployment feel tangible.
- Keep interactions purposeful and accessible.

### Don’t

- Add purple gradient backgrounds or generic AI glow effects.
- Turn every section into a rounded card.
- Add decorative statistics without product meaning.
- Use emojis as icons.
- Introduce new fonts or unrelated visual styles.
- Sacrifice contrast or legibility for cinematic effects.

## Source Files

- `app/page.tsx` — page composition and section order
- `app/globals.css` — tokens, fonts, motion utilities, and base styles
- `app/layout.tsx` — font loading and metadata
- `components/landing/*` — focused landing page sections
- `components/ui/*` — reusable accessible primitives
- `public/images/*` — security and infrastructure imagery

Any future design changes should preserve the product’s dark technical editorial identity and the narrative progression from capability to deployment.
