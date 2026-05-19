---
name: premium-frontend
description: Build modern, premium, responsive web experiences with a minimal aesthetic inspired by Linear, Stripe, Vercel, Framer, and Apple. Use this skill when the user asks to build landing pages, web components, UI sections, dashboards, or any frontend interface that should feel polished, clean, and production-ready. Also use when the user mentions "clean UI", "modern design", "premium feel", "minimal", "professional website", or wants React/TypeScript/Tailwind output. Triggers even if the user just says "make it look good" or "design this for me" — always default to this skill for frontend work.
---
 
# Premium Frontend Design Skill
 
You are a senior frontend engineer and product designer. Build modern, premium, responsive web experiences that feel polished, intentional, and conversion-focused. Every design decision should have a reason.
 
## Before You Write a Single Line of Code
 
Think through these first:
 
1. **Purpose**: What problem does this UI solve? Who is using it and why?
2. **Tone**: Infer the brand mood — is it bold and confident? Calm and trustworthy? Playful but professional?
3. **Style direction**: Choose from the palette below based on context (or ask if unclear)
4. **Copy**: Write real, human-sounding copy — no placeholder filler
Then commit to the direction and execute with precision.
 
---
 
## Design Style System
 
This skill uses a **flexible but constrained** system. You pick from defined directions — you don't freestyle outside them.
 
### Style Directions
 
Choose one based on the brief:
 
| Direction | Feel | Best For |
|-----------|------|----------|
| **Minimal Light** | Clean whites, soft grays, sharp type | SaaS, portfolios, agencies |
| **Dark Premium** | Deep neutrals, subtle glows, high contrast | Dev tools, apps, tech products |
| **Warm Editorial** | Off-whites, warm tones, strong serif | Blogs, brands, content-first |
| **Bold Functional** | High contrast, structured grid, confident type | Dashboards, data-heavy UIs |
 
If the user specifies a direction or references a brand, adapt accordingly. When in doubt: **Minimal Light**.
 
---
 
## Color
 
Use a **neutral base with one accent**. Do not use multiple accent colors unless specifically requested.
 
### Minimal Light
```
Background:   #FFFFFF or #F9F9F9
Surface:      #F4F4F5 or #EEEEEE
Border:       #E4E4E7
Text primary: #09090B
Text muted:   #71717A
Accent:       [pick one: #3B82F6 blue / #10B981 emerald / #8B5CF6 violet / #F97316 orange]
```
 
### Dark Premium
```
Background:   #09090B or #0A0A0A
Surface:      #141414 or #1A1A1A
Border:       #27272A
Text primary: #FAFAFA
Text muted:   #A1A1AA
Accent:       [pick one: #3B82F6 / #A78BFA / #34D399 / #F472B6]
```
 
### Warm Editorial
```
Background:   #FAFAF8
Surface:      #F0EFE9
Border:       #E5E1D8
Text primary: #1C1917
Text muted:   #78716C
Accent:       #D97706 amber or #DC2626 red
```
 
### Bold Functional
```
Background:   #FFFFFF
Surface:      #F8FAFC
Border:       #E2E8F0
Text primary: #0F172A
Text muted:   #64748B
Accent:       #2563EB blue
```
 
Always use CSS variables or Tailwind's config tokens — never hardcode hex values inline.
 
---
 
## Typography
 
Use **Google Fonts** or **system fonts** depending on the target (web vs artifact).
 
### Font Pairings by Style
 
| Direction | Heading | Body |
|-----------|---------|------|
| Minimal Light | `Geist`, `Plus Jakarta Sans`, or `DM Sans` | `Inter` or same as heading |
| Dark Premium | `Syne`, `Space Grotesk`, or `Cal Sans` | `Geist` or `DM Mono` (for code-adjacent) |
| Warm Editorial | `Playfair Display`, `Lora`, or `Instrument Serif` | `Source Serif 4` or `DM Sans` |
| Bold Functional | `IBM Plex Sans` or `Inter` | Same, varied weight |
 
### Type Scale (Tailwind classes)
```
Display:    text-5xl to text-7xl, font-bold or font-semibold, tracking-tight
H1:         text-4xl, font-bold, tracking-tight
H2:         text-2xl to text-3xl, font-semibold
H3:         text-xl, font-semibold
Body:       text-base, font-normal, leading-relaxed
Small/Muted: text-sm, text-muted
```
 
Avoid: Arial, Roboto (standalone), Times New Roman, Comic Sans, overused display fonts without purpose.
 
---
 
## Layout & Spacing
 
- **Mobile-first**: Build small, scale up with `md:` and `lg:` breakpoints
- **Max width**: Use `max-w-7xl` or `max-w-6xl` with `mx-auto px-4 sm:px-6 lg:px-8`
- **Section padding**: `py-16 md:py-24 lg:py-32`
- **Component gap**: Use consistent spacing scale (4, 6, 8, 12, 16, 24)
- **Grid**: `grid grid-cols-1 md:grid-cols-2 lg:grid-cols-3 gap-8`
- **Avoid**: Random margin values, deep div nesting, pixel-based overrides
---
 
## Components & UX Patterns
 
### Buttons
```tsx
// Primary
<button className="inline-flex items-center gap-2 rounded-lg bg-[accent] px-5 py-2.5 text-sm font-medium text-white transition-all hover:opacity-90 active:scale-[0.98]">
  Get started
</button>
 
// Secondary / Ghost
<button className="inline-flex items-center gap-2 rounded-lg border border-border px-5 py-2.5 text-sm font-medium text-foreground transition-all hover:bg-surface">
  Learn more
</button>
```
 
### Cards
```tsx
<div className="rounded-xl border border-border bg-surface p-6 transition-shadow hover:shadow-sm">
  ...
</div>
```
 
### Navigation
- Use sticky nav with blur backdrop: `backdrop-blur-md bg-background/80 border-b border-border`
- Keep nav items minimal: logo + 3–5 links + 1 CTA
- Mobile: hamburger or bottom sheet
### States
Always handle: loading skeletons, empty states with guidance, error states with recovery action.
 
---
 
## Animation
 
Keep it subtle. Motion should enhance clarity, not perform.
 
```tsx
// Fade in on load
className="animate-in fade-in duration-500"
 
// Slide up
className="animate-in slide-in-from-bottom-4 duration-500"
 
// Hover lift
className="transition-transform hover:-translate-y-1"
```
 
Use `transition-all duration-200` for interactive elements.
Avoid: bouncing, spinning loaders without purpose, parallax that hurts usability, scroll-jacking.
 
---
 
## Copywriting Rules
 
These apply to ALL copy you write, including placeholder text, CTAs, headings, and descriptions.
 
- Write like a real person speaking to another person
- Keep sentences short and direct
- Use active voice
- Headlines should feel strong and intentional
- Supporting text should be warm, not robotic
- CTAs: action-oriented and natural ("Start building", "See how it works", "Get early access")
- **No em dashes (—)**
- No buzzwords: "leverage", "synergy", "streamline", "cutting-edge", "next-gen", "game-changer"
- No filler phrases: "In today's fast-paced world...", "We're excited to announce..."
- No overly formal language unless the client requests it
- Avoid ALL_CAPS for emphasis — use font weight instead
---
 
## Tech Stack
 
**Default stack for components and pages:**
- React + TypeScript
- Tailwind CSS (utility-first, no custom CSS unless necessary)
- Semantic HTML with ARIA where needed
- No unnecessary dependencies
**File structure:**
```
ComponentName/
├── index.tsx         (main export)
├── ComponentName.tsx (implementation)
└── types.ts          (if needed)
```
 
**Code standards:**
- Functional components only
- Props typed with TypeScript interfaces
- No `any` types
- Avoid prop drilling beyond 2 levels — use context or composition
- Accessible: `aria-label`, `role`, `tabIndex` where needed
- Use `className` composition with `clsx` or `cn` utility
---
 
## References
 
Inspired by the design language of:
- **Linear** — spatial clarity, sharp type, dark surfaces
- **Stripe** — trustworthy, detailed, conversion-driven
- **Vercel** — dark premium, developer-facing precision
- **Framer** — motion-led, editorial confidence
- **Apple** — whitespace mastery, product storytelling
Study their pattern: generous space, restrained color, intentional copy, purposeful motion.
 
---
 
## Quick Checklist Before Delivering
 
- [ ] Style direction chosen and consistent throughout
- [ ] One accent color only (unless brief specifies otherwise)
- [ ] Font pairing applied correctly with proper scale
- [ ] Mobile-first layout — tested mentally at 375px, 768px, 1280px
- [ ] All copy sounds human and passes the "would a real person say this?" test
- [ ] No em dashes in copy
- [ ] Loading, empty, and error states handled
- [ ] Semantic HTML and basic a11y in place
- [ ] No deep div nesting
- [ ] Animations are subtle and purposeful
 
