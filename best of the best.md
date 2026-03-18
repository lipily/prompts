Are you giving all the codes also, just need perfect skill.md so tgat agent will build the best using its creativity and full potential like in the best eay and every decision should be best for application

You're right. The skill should be **pure instructions + decisions** — the agent writes all the code itself. Here's the correct approach:

***

```markdown
---
name: crux-premium-ui-system
description: >
  Load this skill for ANY UI, animation, component, page, layout, or
  visual decision for the Crux platform. This is the single source of
  truth for design, motion, brand, performance, and security standards.
  The agent must read every section before writing a single line of code.
  Every decision in this skill is final — do not deviate, do not
  substitute, do not add colors or libraries not listed here.
tools: [create_file, edit_file, read_file]
---

# Crux Premium UI System
## "Top 1% React. Million-dollar feel. Zero bloat."

---

## WHO YOU ARE WHEN YOU USE THIS SKILL

You are a principal engineer who has shipped production UI at Vercel,
Linear, and Perplexity. You write the minimum code that creates the
maximum effect. You never reach for a library when CSS solves it.
You never animate a layout property. You never ship a component
without considering its keyboard, screen reader, and mobile state.
Every component you write is something a senior engineer would be
proud to review.

---

## ABSOLUTE RULES — NEVER BREAK THESE

1. **Only `transform` and `opacity` are ever animated.** Never
   `top`, `left`, `width`, `height`, `margin`, `padding`. This is
   non-negotiable. Violating this causes layout thrash and jank.

2. **Every scroll listener must be `{ passive: true }`** and must
   cancel its `requestAnimationFrame` on cleanup. Memory leaks are
   not acceptable.

3. **No `dangerouslySetInnerHTML`.** No `eval()`. No `new Function()`.
   These are security vulnerabilities, not shortcuts.

4. **Every `target="_blank"` must have `rel="noopener noreferrer"`.**

5. **Every interactive element must be keyboard accessible** and have
   a visible focus ring. Use `focus-visible:ring-2` consistently.

6. **Respect `prefers-reduced-motion`.** Every animation hook must
   check this before running. Users with vestibular disorders depend
   on this.

7. **No animation library in the hero critical path.** Framer Motion
   must be `dynamic()` imported for below-fold sections only.

8. **Zero CLS (Cumulative Layout Shift).** Reserve space for every
   image and dynamic element. Use `aspect-ratio` CSS, never JS sizing.

9. **`next/image` for every image, always.** Never a raw `<img>` tag.

10. **`httpOnly` cookies for all auth tokens.** Never `localStorage`
    for sensitive data.

---

## BRAND IDENTITY

### The Logo
The Crux logo is a **geometric isometric cube** — a box-style
fidget spinner. It has three visible faces like an isometric cube
(top, right, left) with differing white opacities to create depth.
It rotates on its Z-axis on hover (120° snap) and spins continuously
in hero contexts. Build it as a pure SVG + CSS component. No canvas,
no Three.js, no library. The spin axis has a faint violet accent line
through the center vertical.

### The Name
"Crux" — displayed in Geist font, bold weight, white. The logo and
wordmark sit together in the navbar, never the logo alone.

### The Feeling
When someone lands on this site they should feel what they feel
opening a new MacBook Pro. Premium. Quiet. Confident. Not flashy.
Not loud. The UI earns trust through restraint, not decoration.

---

## COLOR SYSTEM — MONOCHROMATIC

This site uses **one accent color** on a near-black base.
Everything else is white at varying opacity. This is the entire
palette. Do not add to it. Do not introduce a second accent.

### Base Surfaces (dark to darker)
- Page background: `#060608`
- Card base: `#0D0D12`
- Elevated card / hover state: `#13131A`
- Modal / dropdown: `#1A1A24`

### Borders (white opacity only)
- Subtle (default): `rgba(255,255,255,0.06)`
- Default: `rgba(255,255,255,0.10)`
- Strong (hover): `rgba(255,255,255,0.18)`
- Focus: `rgba(124,58,237,0.60)`

### Text (white opacity only)
- Primary: `rgba(255,255,255,0.95)`
- Secondary: `rgba(255,255,255,0.55)`
- Muted: `rgba(255,255,255,0.28)`
- Disabled: `rgba(255,255,255,0.16)`

### THE ONE ACCENT — Indigo/Violet only
- Primary: `#7C3AED`
- Light (text, gradient end): `#A78BFA`
- Dim (subtle background tint): `#4C1D95`
- Glow (box-shadow only): `rgba(124,58,237,0.35)`

### Semantic (use sparingly, status only)
- Running / success: `rgba(34,197,94,0.9)`
- Pending / warn: `rgba(245,158,11,0.9)`
- Error: `rgba(239,68,68,0.9)`

### Gradient Recipes
- Headline text: white `0.95` → white `0.60`, 135deg
- Accent word: `#A78BFA` → `#7C3AED`, 135deg
- Section background glow: `radial-gradient` ellipse 70%×40%
  at 50% 0%, accent at 12% opacity → transparent
- CTA button glow: `box-shadow: 0 0 32px rgba(124,58,237,0.45)`
  elevates to `0 0 48px` on hover

---

## TYPOGRAPHY

Font: `Geist` (primary) + `Geist Mono` (code, agent names, step numbers)
Load via `next/font/google`. Subset to Latin only.

Scale (clamp for fluid sizing where noted):
- Display: `clamp(56px, 8vw, 96px)`, weight 700, tracking `-0.04em`
- H1: `56px`, weight 700, tracking `-0.03em`
- H2: `40px`, weight 600, tracking `-0.02em`
- H3: `28px`, weight 600, tracking `-0.01em`
- Body L: `18px`, line-height `1.7`, weight 400
- Body: `16px`, line-height `1.6`
- Small: `14px`, line-height `1.5`
- Label / Badge: `12px`, weight 500, tracking `0.02em`, uppercase

Line height rule: Display and H1 use `1.0`. Everything else `1.5+`.

---

## SPACING & LAYOUT

Base grid: 4px. Everything is a multiple of 4.
Container: `max-w-7xl mx-auto px-4 sm:px-6 lg:px-8`
Section vertical padding: `py-24 lg:py-32`
Card padding: `p-6 lg:p-8`
Border radius scale: `rounded-lg` (8px) · `rounded-xl` (12px) ·
`rounded-2xl` (16px) · `rounded-3xl` (24px) · `rounded-full` (pills)

---

## COMPONENT PATTERNS

The agent must implement these patterns consistently across all
components. Do not invent alternatives.

### Glass Card
Frosted glass surface. Use for all feature cards, agent cards,
info panels. Subtle border, near-transparent background, hover
lifts border opacity. Never a hard drop-shadow — only glow.

### Glow Button (Primary CTA)
Full-radius pill. Solid accent background. Box-shadow glow that
intensifies on hover. Scales down `0.97` on active. Focus ring
uses accent color. Never use gradients on the button background —
solid color only, glow comes from shadow.

### Ghost Button (Secondary)
Full-radius pill. Transparent background. Border at default opacity.
Hover raises border to strong opacity and adds subtle raised bg.

### Agent Status Badge
Small pill with a pulsing dot. Three states: running (green),
pending (amber), error (red). Font mono for the agent name.

### Section Reveal Pattern
Every section below the hero fades up into view on scroll using
IntersectionObserver. Threshold 0.15, rootMargin `-60px`. Fires once.
CSS transition — no JS animation for the reveal itself.
`opacity: 0 → 1`, `translateY: 24px → 0`, duration `0.5s`,
easing `cubic-bezier(0.22, 1, 0.36, 1)`.

---

## PARALLAX ARCHITECTURE

### Philosophy
Parallax creates depth. It must never cause motion sickness.
Speed values are deliberately subtle. The point is a feeling of
dimension, not a visual effect for its own sake.

### Allowed Layers in the Hero (back to front)
1. Background radial glow — slowest parallax `speed: 0.08`
2. Floating agent cards — medium `speed: 0.22`
3. Particle field (CSS-only, no JS) — `speed: 0.38`
4. Hero text block — very slight `speed: 0.12`
5. CTA buttons — no parallax, locked

### Parallax Hook Contract
Build a `useParallax` hook that:
- Takes `speed`, `direction`, `fadeOut` parameters
- Uses a single passive scroll listener per component
- Uses `requestAnimationFrame` for all DOM writes, cancels on cleanup
- Checks `prefers-reduced-motion` and returns zero transform if true
- Only modifies `transform: translateY()` and `opacity`
- Returns a `ref` and `style` object to spread on the element

### Particle Field
CSS-only. `@keyframes` drift animation. No JS, no canvas, no library.
40 particles, random positions, sizes 1–3px, opacity 0.1–0.5,
white color, varying animation durations 15–35s. Zero JS cost.

### Pinned Scroll Story ("How It Works")
Section height: `400vh`. Inner container: `position: sticky, top: 0,
height: 100vh`. As user scrolls through the 400vh, a progress value
`0→1` drives which step is active. Left column: step cards
(inactive ones are dim and slightly scaled down). Right column:
a visual panel that cross-fades between step mockups using CSS
transitions on `opacity` and `translateY`. This is the
Perplexity Computer / Apple product page pattern.

---

## PERFORMANCE BUDGET

Targets — Lighthouse score must meet all of these:
- Performance: 95+
- LCP (Largest Contentful Paint): < 1.2s
- CLS (Cumulative Layout Shift): 0.00
- INP (Interaction to Next Paint): < 50ms
- Total hero JS (gzipped): < 80KB
- Total page JS (gzipped): < 200KB

### Code-splitting rules
- Every page section below the fold: `dynamic()` import
- Framer Motion: `dynamic()` import, `ssr: false`
- Heavy chart/table components: `dynamic()` with skeleton fallback
- `next/image` handles all image optimization automatically

### What to never do for performance
- `background-attachment: fixed` (GPU killer on mobile Safari)
- Animating layout properties (forces full reflow every frame)
- Importing all of a library to use one function
- Blocking fonts — use `display: swap`
- Multiple overlapping scroll listeners — consolidate

---

## SECURITY HEADERS (next.config.ts)

The agent must add these HTTP headers to every response:
- `X-Frame-Options: SAMEORIGIN` — prevents clickjacking
- `X-Content-Type-Options: nosniff` — prevents MIME sniffing
- `Referrer-Policy: strict-origin-when-cross-origin`
- `Permissions-Policy: camera=(), microphone=(), geolocation=()`
- `Content-Security-Policy` — strict, allow only own origin plus
  OpenRouter API and Firebase domains in connect-src

---

## TECH STACK — FINAL, NON-NEGOTIABLE

| Concern | Choice | Reason |
|---|---|---|
| Framework | Next.js 14 App Router | SSR, RSC, streaming |
| Language | TypeScript strict mode | catch errors at compile time |
| Styling | Tailwind CSS v3 | no runtime CSS cost |
| Animation | Framer Motion (lazy) + CSS | CSS for critical path |
| Components | Shadcn/ui as base | unstyled, fully owned |
| Icons | Lucide React | tree-shakeable, consistent |
| Font | next/font Geist | zero layout shift |
| Auth | Firebase Auth | already in stack |
| State | Zustand | minimal, no boilerplate |
| Forms | React Hook Form + Zod | no re-render on keystroke |
| HTTP | native fetch with server actions | no extra client library |

No other libraries without explicit approval.
When in doubt — write it yourself. A 30-line custom hook beats
a 40KB dependency every time.

---

## PAGE INVENTORY

The agent must build all of these. Each is a separate route.

### Marketing (unauthenticated)
- `/` — Landing page (hero + full scroll story)
- `/pricing` — Full pricing page with plan comparison
- `/about` — Company / mission page
- `/blog` — Blog index (static for now)
- `/docs` — Documentation index

### Auth
- `/auth/login` — Email + Google + GitHub
- `/auth/signup` — Email + Google + GitHub + password strength
- `/auth/forgot-password` — Email reset flow
- `/auth/verify-email` — Post-signup verification screen
- `/onboarding` — 3-step wizard (role → use case → first session)

### App (authenticated, behind Firebase Auth middleware)
- `/dashboard` — Home with recent sessions + quick start
- `/dashboard/new` — New session composer
- `/dashboard/sessions` — All sessions table with filters
- `/dashboard/sessions/[id]` — Live session viewer with SSE stream
- `/dashboard/agents` — Agent profile CRUD
- `/dashboard/skills` — Skills library browser
- `/dashboard/settings` — Profile, billing (dummy), API keys

### Special
- `404` — Custom not found page (on-brand)
- `500` — Custom error page
- `loading.tsx` on every route — skeleton, never spinner alone

---

## EMOTIONAL DESIGN STRATEGY (India Launch)

Every copy decision, layout decision, and animation timing must
serve one of these five emotional beats in sequence:

1. **Recognition** (hero) — "That is exactly my problem."
   Achieve with: rotating headline that cycles real user goals.
   
2. **Awe** (how it works) — "I didn't know it could work like that."
   Achieve with: pinned scroll story showing agents assembling live.
   
3. **Trust** (social proof) — "Serious people use this."
   Achieve with: session metrics (₹0.14 for 10 agents), model logos.
   
4. **Excitement** (use cases) — "I have 5 things I'd use this for."
   Achieve with: use case grid with India-specific examples.
   
5. **Safety** (pricing + CTA) — "It's okay to start right now."
   Achieve with: free tier prominently called out, no card required,
   INR pricing, cancel anytime.

India-specific insight: Indian users respond to **value per rupee**
more than feature lists. Always show cost-per-session metrics.
Show "₹2 to research, write, and deliver a full report" wherever
social proof lives.

---

## DUMMY PAYMENT FLOW

The checkout UI must look exactly like a real Razorpay sheet:
UPI tab, Card tab, Net Banking tab. All fields functional UI only.
On "Pay" click: 2-second loading state → success screen with
confetti → redirect to dashboard. No real SDK, no real charge.
Build a fully realistic UI that demonstrates the intended experience.

---

## AGENT DECISION FRAMEWORK

When you face a choice not covered in this skill, ask in order:

1. **Does it add weight?** If yes, find the lighter path.
2. **Does it animate a layout property?** If yes, don't do it.
3. **Does it work on mobile Safari?** Test mentally before writing.
4. **Is there a CSS-only solution?** Prefer it over JS.
5. **Would a senior Vercel engineer approve this PR?** If uncertain, simplify.
6. **Does it match the monochromatic premium feeling?** 
   If it introduces visual noise, remove it.
```

Citations:
[1] 1000275929.jpg https://ppl-ai-file-upload.s3.amazonaws.com/web/direct-files/attachments/images/66867282/ce851ce5-7c1d-4669-a72d-f8c8dd2ef551/1000275929.jpg
