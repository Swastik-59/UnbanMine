# Awwwards-Level Design & Motion System

> A build specification for Claude Code, Antigravity, Cursor agents, or similar coding agents.
> **Goal:** produce a site that feels art-directed, cinematic, intentional, fast, usable, and technically polished at the level of strong Awwwards-winning work, without degenerating into a pile of random GSAP effects.

---

## 0. Non-Negotiable Objective

Do **not** interpret “Awwwards-level” as “add more animations.”

The target is a coherent system combining:

1. Art direction
2. Strong typography
3. Distinctive layout composition
4. Clear visual hierarchy
5. Storytelling through scroll
6. Purposeful motion
7. Responsive interaction
8. High-quality microinteractions
9. Optional WebGL / 3D where it adds real value
10. Fast loading and stable rendering
11. Accessibility and reduced-motion support
12. Clean implementation that preserves all existing functionality

Awwwards' own site categories and inspiration library repeatedly surface patterns such as animation, fullscreen layouts, horizontal layouts, infinite scrolling, interaction design, microinteractions, parallax, responsive design, storytelling, transitions, typography, unusual navigation, video and WebGL. Awwwards examples also explicitly showcase GSAP + WebGL + Three.js combinations, horizontal/parallax scrolling, scroll distortion, page transitions, menus, hover effects and title animation.

Reference material:
- https://www.awwwards.com/websites/sites_of_the_day/
- https://www.awwwards.com/sites/brontide
- https://www.awwwards.com/inspiration/slider-drag-and-drop-with-distortion-studio-dot-2
- https://www.awwwards.com/inspiration/page-detail-house-of-dreamers

---

# 1. Agent Operating Rules

## 1.1 Inspect before editing

Before changing code:

- Inspect the entire project structure.
- Identify framework, router, styling system, component architecture, data layer, API layer and animation system.
- Identify every existing page and major component.
- Identify existing design tokens.
- Identify all current interactions.
- Identify any known fragile backend/API logic.
- Identify current performance bottlenecks.
- Read the installed skill files listed in Section 2.
- Do not replace working architecture just because another approach looks more fashionable.

## 1.2 Preserve functionality

Visual work must not silently break:

- authentication
- routing
- API calls
- database access
- forms
- validation
- state management
- analytics
- payments
- uploads
- CRUD flows
- existing business logic
- SEO metadata
- existing integrations

Animation is decoration. Product functionality remains the priority.

## 1.3 Establish a baseline

Before implementation, capture:

- current build status
- current lint/type-check status
- current test status
- current Lighthouse/performance state when available
- screenshots of key routes
- responsive behavior at representative widths

Every major visual iteration must be compared against the baseline.

## 1.4 Never “Vibe-Code” the design

Do not:

- randomly add gradients
- randomly add glassmorphism
- animate every element
- use huge rounded cards everywhere
- use generic purple/blue gradients without a visual reason
- use excessive shadows
- use floating blobs because the page feels empty
- add WebGL only because it sounds impressive
- copy a template structure and merely replace colors
- hide weak product hierarchy beneath motion

Every visual decision needs a reason tied to hierarchy, brand, content, interaction or storytelling.

## 1.5 Work in systems, not isolated tricks

Create reusable primitives for:

- typography
- section layouts
- container sizing
- spacing
- reveal animations
- split-text animations
- parallax
- pinned sections
- horizontal scrolling
- cursor states
- magnetic interactions
- image reveals
- page transitions
- loaders
- hover states
- reduced-motion behavior

Do not duplicate motion code across components unless the effect is genuinely unique.

---

# 2. Installed Skill System

The repository already contains these skills under `.agents/skills`.

## 2.1 Required skill inspection

Read the relevant `SKILL.md` files before implementation. Use the skills as implementation references, not as decoration.

### Browser / security / QA

- `agent-browser`
- `agent-security-audit`
- `playwright-testing`
- `web-perf`

Use these for inspection, automated interaction checks, security regression checks, and performance validation.

### Design / frontend

- `anti-ui-slop`
- `better-colors`
- `better-typography`
- `design-taste-frontend`
- `frontend-design`
- `ui-design`
- `ui-radar`
- `ui-ux-concept-implementation`
- `unslop`
- `unslop-ui`

Use these to challenge generic layouts, establish visual direction, improve typography/color, refine interaction quality, and prevent “AI-generated” visual patterns.

### Motion / animation

- `hyperframes-animation`
- `improve-animations`
- `motion`

Use these for motion architecture, timing, sequencing, easing, interaction design and animation polish.

### 3D / spatial visuals

- `threejs`

Use only when 3D, WebGL or spatial interaction materially improves the experience.

### Framework / code quality

- `nextjs`
- `react-best-practices`

Use these to preserve framework conventions, rendering strategy, component quality and maintainability.

### Documentation / project hygiene

- `crafting-effective-readmes`
- `indexing-readme`

Update documentation if the design system, architecture or setup materially changes.

### Discovery

- `find-skills`

Use when the current skill set is missing a specialized capability needed for the design goal.

### Backend/data skills

- `fastapi`
- `postgres-best-practices`
- `security-guidance`

Do not unnecessarily touch backend code. Use these if visual work requires related API/data changes.

## 2.2 Skill usage policy

The agent should:

1. Read all relevant skills before starting.
2. Build a skill-to-task mapping.
3. Use multiple skills together when the task crosses domains.
4. Prefer existing repository skill guidance over inventing new conventions.
5. Run QA skills after the design pass.
6. Use `find-skills` rather than inventing a missing workflow.

---

# 3. Awwwards-Level Design Definition

## 3.1 Design pillars

The site should feel:

- art-directed
- editorial
- cinematic
- responsive
- tactile
- deliberate
- confident
- slightly unexpected
- visually memorable
- easy to navigate despite the experimentation

The site should **not** feel:

- template-driven
- SaaS-generic
- over-carded
- over-rounded
- animation-heavy without hierarchy
- visually noisy
- slow
- inaccessible

---

# 4. Art Direction Before CSS

Before writing detailed styles, define:

## 4.1 Visual concept

Document:

- central visual idea
- brand personality
- emotional tone
- visual metaphor
- photography/illustration/3D direction
- interaction metaphor
- motion personality

Example structure:

```text
CONCEPT
  ↓
Visual metaphor
  ↓
Typography
  ↓
Layout language
  ↓
Motion language
  ↓
Interaction language
```

Do not let technology define the visual identity.

---

# 5. Layout System

## 5.1 Use composition, not endless cards

Favor:

- asymmetric layouts
- editorial grids
- full-bleed media
- intentional negative space
- overlapping layers
- oversized type
- variable section heights
- edge-to-edge sections
- image/text tension
- controlled alignment breaks

Avoid:

```text
Card
Card
Card
Card
Card
```

when the content can be expressed more strongly through composition.

## 5.2 Hero composition

The hero should immediately establish:

- identity
- hierarchy
- motion language
- product/value proposition
- visual hook

Possible structure:

```text
┌────────────────────────────────────────┐
│ NAV                                    │
│                                        │
│        MASSIVE DISPLAY TYPE             │
│                                        │
│                 [visual]               │
│                                        │
│ metadata                CTA / cue      │
└────────────────────────────────────────┘
```

The hero should generally feel like a scene, not just a header.

## 5.3 Fullscreen sections

Use `min-height: 100svh` where appropriate, but do not force every section to exactly one viewport height.

Use full-screen sections for moments of emphasis:

- hero
- major story beat
- product reveal
- key visual transition
- CTA/finale

---

# 6. Typography System

Typography is a primary design instrument.

## 6.1 Create explicit type roles

Define tokens for:

- display
- display compact
- headline
- subheadline
- body
- label
- metadata
- navigation
- captions

## 6.2 Typography behaviors

Support:

- oversized titles
- tight/controlled tracking
- variable font weights where appropriate
- mixed serif/sans combinations where justified
- staggered line reveals
- word reveals
- character reveals
- masked line reveals
- responsive type scaling with `clamp()`

Do not animate text solely because it can be animated.

## 6.3 Line control

For scroll-based line reveals, wrap text intentionally so animation remains stable across breakpoints.

Do not build motion around fragile manually inserted `<br>` tags unless art direction requires fixed line breaks.

---

# 7. Color System

## 7.1 Prefer constrained palettes

Start with:

- primary background
- primary foreground
- secondary foreground
- one strong accent
- optional supporting accent

Awwwards examples often demonstrate disciplined, limited color systems rather than a kitchen-sink palette.

## 7.2 Dynamic color

Color transitions may be tied to sections or scroll position when they improve storytelling.

Examples:

```text
Section A → light
Section B → dark
Section C → accent
Section D → light
```

Do this deliberately, not every few pixels.

---

# 8. Texture & Depth

Use subtle:

- film grain
- noise
- texture overlays
- gradients
- blur
- displacement
- lighting effects
- soft masks

Texture must remain subtle enough not to compromise readability or performance.

A small amount of texture can reduce sterile digital flatness. A large amount merely makes the website look like it fell into Photoshop.

---

# 9. Motion Design System

## 9.1 Motion principles

Motion must answer one of five questions:

1. What is entering?
2. What is leaving?
3. What is reacting?
4. What is transforming?
5. Where should the user's attention go?

If an animation answers none of these, remove it.

## 9.2 Motion hierarchy

### Level 1: Microinteraction

Duration target: ~120–350ms

Use for:

- button hover
- icon movement
- cursor reactions
- small state transitions

### Level 2: Component transition

Duration target: ~350–800ms

Use for:

- image reveals
- cards entering
- menus
- modal transitions
- section elements

### Level 3: Cinematic transition

Duration target: ~700–1500ms or scroll-controlled

Use for:

- page transitions
- hero reveals
- major visual transformations
- section choreography

Do not hardcode these values blindly. Tune based on visual rhythm.

---

# 10. Easing System

Prefer a small family of consistent easings.

Typical roles:

```text
standard UI       → easeOut / power-like
soft entrance     → smooth easeOut
physical motion   → spring-like
dramatic reveal   → custom cubic-bezier
scroll scrub      → usually direct/proportional
```

Do not use a different easing for every element.

Motion should have a recognizable personality.

---

# 11. On-Scroll Animation System

This is the core of the requested Awwwards-style behavior.

## 11.1 Scroll reveal

Basic pattern:

```text
before viewport
opacity: 0
transform: translateY(40-100px)

enter viewport
opacity: 1
transform: translateY(0)
```

Enhance with:

- stagger
- clip-path
- mask reveal
- blur-to-sharp
- scale normalization

Use reveals selectively. Every element should not animate independently.

## 11.2 Scrub-based animation

Tie animation progress directly to scroll position.

```js
scrollTrigger: {
  trigger: section,
  start: "top top",
  end: "bottom top",
  scrub: true,
}
```

Use for:

- image scale
- image position
- typography movement
- object rotation
- camera motion
- progress indicators
- visual transformations

Scrub should feel physically connected to user input.

## 11.3 Pinned storytelling

Pattern:

```text
scroll
  ↓
section reaches viewport
  ↓
section pins
  ↓
content transforms while pinned
  ↓
section releases
```

Use for:

- product stories
- feature explanations
- case studies
- visual narratives
- chapter-based storytelling

Do not pin everything.

## 11.4 Parallax

Use different motion rates for layers:

```text
background  → 0.2–0.4x
midground   → 0.5–0.8x
foreground  → 1.0x
```

Tune visually rather than adhering rigidly to numbers.

## 11.5 Image scale-through-scroll

```text
100% → 105% → 115% → 125%
```

Use to create cinematic tension.

## 11.6 Horizontal scrolling

A vertical wheel gesture may control a horizontal story.

Use when horizontal composition meaningfully improves:

- portfolios
- galleries
- case studies
- timelines
- product variants

Do not use horizontal scrolling simply because it looks fashionable.

## 11.7 Scroll-linked typography

Possible effects:

- line-by-line reveal
- character reveal
- tracking expansion
- scale transformation
- opacity crossfade
- horizontal drift
- vertical drift
- mask reveal
- blur-to-sharp
- color transition

Keep text readable throughout the interaction.

---

# 12. Text Animation Patterns

Implement reusable utilities/components for:

## 12.1 Word reveal

```text
HELLO
WORLD
FROM
STUDIO
```

Each word enters with a subtle stagger.

## 12.2 Character reveal

Use sparingly for hero moments, editorial titles and experimental branding.

## 12.3 Line-mask reveal

Preferred for large headings.

Conceptually:

```text
overflow: hidden
line translated below mask
→ animate to baseline
```

## 12.4 Blur-to-sharp

```text
blur(12px) → blur(0)
opacity 0 → 1
```

Use in controlled amounts.

## 12.5 Scramble / decode

Use for:

- labels
- metadata
- navigation transitions
- experimental branding

Do not use it for long paragraphs.

---

# 13. Image Motion System

Use reusable image states:

- reveal-from-mask
- scale-on-scroll
- parallax image
- hover zoom
- hover pan
- clip-path expansion
- distortion
- displacement
- grayscale-to-color
- blur-to-sharp

## 13.1 Image reveal

Preferred techniques:

- clip-path
- transform wrapper
- mask
- SVG mask when justified

The image itself should remain composited efficiently whenever possible.

---

# 14. Cursor System

Implement a single global cursor controller.

Possible states:

```text
DEFAULT
LINK
VIEW
DRAG
OPEN
IMAGE
VIDEO
TEXT
DISABLED
```

Example:

```text
DEFAULT → small dot
LINK    → enlarged circle
VIEW    → circle + "VIEW"
DRAG    → "DRAG"
IMAGE   → contextual label
```

## 14.1 Inertia

Cursor movement should have slight interpolation rather than snapping directly.

## 14.2 Magnetic interactions

Buttons and important controls may subtly follow the pointer.

Do not make large interactive displacement that harms usability.

## 14.3 Mobile

Disable custom cursor systems on touch devices.

---

# 15. Hover Interaction System

Every interactive object should have an intentional hover/focus state.

Examples:

- image zoom
- image pan
- underline travel
- icon movement
- label morph
- cursor state change
- background shift
- subtle scale
- magnetic response
- color inversion

Hover should never be the only indication of interactivity. Preserve keyboard focus states.

---

# 16. Navigation

Possible high-end patterns:

- compact fixed nav
- transparent nav over hero
- full-screen overlay menu
- animated menu icon
- project-preview navigation
- section indicator
- circular navigation
- scroll-aware navigation

## 16.1 Full-screen menu choreography

Recommended sequence:

```text
menu click
  ↓
background transition
  ↓
menu container enters
  ↓
navigation links stagger
  ↓
secondary metadata enters
```

Close in the reverse order or through a deliberate transition.

## 16.2 Navigation must remain usable

Motion must never make basic navigation slow or confusing.

---

# 17. Page Transitions

Treat route changes as part of the experience.

Possible patterns:

- curtain wipe
- clip-path expansion
- scale transition
- color field transition
- liquid-like transition
- masked image transition
- shared-element transition

The transition must:

1. begin instantly after intent
2. provide feedback
3. avoid blocking navigation unnecessarily
4. respect reduced motion
5. fail safely if route loading is slow

Do not create long “cinematic” transitions that make users wait.

---

# 18. Loading Experience

Create a lightweight loader only when necessary.

Potential sequence:

```text
brand mark
  ↓
progress / visual feedback
  ↓
hero enters
  ↓
loader exits
```

Never make a fake 0–100% loading animation that does not correspond to actual readiness just to look fancy.

---

# 19. WebGL / Three.js Policy

## 19.1 Use WebGL when it adds a visual capability unavailable through normal DOM/CSS.

Good use cases:

- 3D product visualization
- shader-based image distortion
- liquid effects
- displacement
- particle systems
- interactive environments
- camera-controlled scenes
- advanced scroll distortion

Bad use cases:

- replacing a simple gradient
- replacing a basic image
- decorative particles with no conceptual purpose
- 3D objects that create more distraction than meaning

## 19.2 Three.js implementation

When using React:

- prefer React Three Fiber when appropriate
- isolate the canvas
- lazy-load heavy 3D routes/components
- avoid re-rendering the whole React tree on every frame
- use refs and frame loops for animation
- dispose of assets correctly
- cap pixel ratio appropriately
- avoid unnecessarily large textures
- test on mid-range mobile hardware

## 19.3 WebGL fallback

Provide a non-WebGL or low-motion fallback when feasible.

---

# 20. Video

Use cinematic video for:

- hero storytelling
- product demonstration
- background atmosphere
- visual case studies

Optional scroll-linked video behavior:

```text
scroll position
      ↓
video timeline
```

But prioritize:

- compressed assets
- poster images
- lazy loading
- mobile variants
- autoplay policy compliance
- reduced-motion alternatives

---

# 21. Sound

Sound is optional.

Never force autoplay audio on users.

When used:

- keep default audio off
- clearly indicate controls
- use subtle interaction sounds
- respect device and user settings

Sound should support the brand experience, not announce that the developer discovered headphones.

---

# 22. Storytelling Architecture

The site should have a narrative.

Recommended model:

```text
HOOK
  ↓
CONTEXT
  ↓
DISCOVERY
  ↓
INTERACTION
  ↓
TRANSFORMATION
  ↓
PROOF
  ↓
CTA / FINALE
```

Each major section should have a reason for existing.

Avoid generic:

```text
Hero
Features
Features
Features
Testimonials
CTA
Footer
```

unless the product genuinely requires it.

---

# 23. Section Choreography

Each section should define:

```yaml
section:
  purpose: "what the section communicates"
  entry: "how it appears"
  focal_point: "what gets attention first"
  scroll_behavior: "reveal | scrub | pin | horizontal | static"
  interaction: "hover | drag | click | cursor | none"
  exit: "how the section hands off to the next"
```

This turns animation into an authored system instead of component-level improvisation.

---

# 24. Motion Choreography Example

A strong sequence could look like:

```text
PAGE LOAD
  ↓
logo enters
  ↓
hero title line reveal
  ↓
hero media scales into place
  ↓
small metadata appears

SCROLL
  ↓
hero media subtly zooms
  ↓
headline drifts
  ↓
next section overlaps

SECTION 2
  ↓
pinned container
  ↓
feature 01 enters
  ↓
feature 02 replaces it
  ↓
feature 03 replaces it
  ↓
section releases

GALLERY
  ↓
horizontal scroll
  ↓
images parallax independently
  ↓
hover reveals project information

CTA
  ↓
large typography
  ↓
background transition
  ↓
magnetic button
  ↓
page transition on click
```

---

# 25. Responsive Design

Awwwards-style desktop design must not be blindly collapsed onto mobile.

Create separate interaction strategies for:

- desktop
- tablet
- mobile

## 25.1 Desktop

Can support:

- custom cursor
- hover
- large parallax
- pinned sections
- horizontal scenes
- WebGL

## 25.2 Tablet

Reduce:

- motion distance
- heavy WebGL
- hover-dependent interactions
- extreme horizontal movement

## 25.3 Mobile

Prioritize:

- readability
- tap targets
- short motion distances
- touch interaction
- performance

Common mobile substitutions:

```text
custom cursor → none
horizontal scroll scene → vertical story
heavy WebGL → static/video fallback
large parallax → subtle transform
hover reveal → tap/focus state
```

---

# 26. Accessibility & Reduced Motion

Must support:

```css
@media (prefers-reduced-motion: reduce) {
  /* minimize non-essential movement */
}
```

Reduced-motion mode should:

- disable large parallax
- disable decorative cursor animation
- simplify page transitions
- reduce scrub distance
- avoid rapid sequencing
- keep content and navigation fully available

Also ensure:

- visible keyboard focus
- readable contrast
- semantic headings
- alt text
- reduced flashing
- accessible controls
- touch-friendly targets

---

# 27. Performance Rules

Motion is not permission to destroy performance.

## 27.1 Keep main-thread work low

Prefer:

- transforms
- opacity
- GPU-friendly compositing
- requestAnimationFrame only when needed
- GSAP timelines rather than dozens of independent listeners

Avoid:

- layout-triggering animation where unnecessary
- continuous `getBoundingClientRect()` loops
- scroll listeners doing heavy work every frame
- React state updates on every animation frame
- unnecessary DOM duplication

## 27.2 Use modern browser APIs and animation libraries correctly

- use passive input listeners when appropriate
- prefer IntersectionObserver for simple visibility triggers
- use GSAP ScrollTrigger for coordinated scroll systems
- use `will-change` sparingly
- lazy-load heavy media
- optimize images
- use responsive image sizes
- compress video
- split large bundles
- lazy-load 3D

## 27.3 WebGL performance

Monitor:

- devicePixelRatio
- draw calls
- texture memory
- shader complexity
- post-processing
- object counts
- animation loop cost

Do not render a 4K texture on a 360px phone because humanity has suffered enough.

---

# 28. Performance Budget

Before calling the work finished, target:

- no obvious scroll jank
- stable interaction at 60fps on capable desktop hardware
- acceptable fallback on mid-range mobile
- no unnecessary blocking JS
- no huge unused dependencies
- no heavy 3D on first paint unless absolutely necessary
- images sized for their display dimensions
- no cumulative layout jumps caused by animation/loading

Measure instead of guessing.

---

# 29. Anti-Slop Quality Gate

Run an explicit visual critique pass.

Ask:

### Typography
- Is the type hierarchy memorable?
- Is spacing intentional?
- Are line lengths controlled?

### Layout
- Is composition distinctive?
- Are there unnecessary cards?
- Is whitespace intentional?

### Color
- Is the palette coherent?
- Are accents meaningful?

### Motion
- Is every major animation purposeful?
- Do animations share a timing language?
- Are transitions too long?

### Interaction
- Does the interface react to the user?
- Are hover/focus states clear?
- Does the cursor enhance rather than distract?

### Brand
- Does this look like a specific brand or a generic AI-generated portfolio?

### Restraint
- What is the first thing that should be removed?
- What is the second thing that should be reduced?

The goal is **high density of intentional decisions**, not high density of effects.

---

# 30. Design Taste Checklist

Before finalizing:

- remove 20% of unnecessary decoration
- strengthen the strongest visual idea
- make type larger when the concept supports it
- reduce accidental symmetry
- remove redundant cards
- unify border radii
- unify shadows
- unify animation easing
- unify spacing scale
- ensure controls look related
- ensure imagery follows one art direction
- ensure icons belong to the same family
- make every section visibly intentional

---

# 31. Component Architecture

Recommended reusable primitives:

```text
/components
  /motion
    Reveal.tsx
    SplitText.tsx
    Parallax.tsx
    PinSection.tsx
    HorizontalScroll.tsx
    ImageReveal.tsx
    Magnetic.tsx
    PageTransition.tsx
    ScrollProgress.tsx
    Stagger.tsx
    TextScramble.tsx

  /interaction
    CustomCursor.tsx
    CursorProvider.tsx
    HoverMedia.tsx
    MagneticButton.tsx

  /layout
    Container.tsx
    FullBleed.tsx
    Section.tsx
    EditorialGrid.tsx

  /visual
    Grain.tsx
    NoiseOverlay.tsx
    WebGLCanvas.tsx
    VideoHero.tsx
```

Adapt names to the existing architecture instead of forcing a rewrite.

---

# 32. Motion API Design

Prefer declarative configuration when possible.

Example:

```ts
const motion = {
  reveal: {
    y: 64,
    duration: 0.9,
    ease: "power3.out",
  },
  stagger: 0.08,
};
```

Or:

```tsx
<Reveal variant="title">
  <h1>...</h1>
</Reveal>
```

Centralize:

- durations
- easings
- default scroll thresholds
- stagger values
- breakpoints
- reduced-motion logic

---

# 33. ScrollTrigger Rules

When using GSAP:

- avoid creating duplicate triggers on rerender
- scope animations correctly
- clean up on component unmount
- use `gsap.context()` or equivalent lifecycle-safe patterns
- refresh after dynamic content changes when necessary
- avoid deeply nested pinning unless tested carefully
- use `invalidateOnRefresh` where appropriate
- test resize behavior
- test route transitions

Every scroll animation must survive:

- resize
- route navigation
- slow loading
- mobile layout changes
- browser back/forward navigation

---

# 34. Lenis / Smooth Scrolling

If the project uses a smooth-scroll system:

- integrate it once globally
- do not create independent smooth-scroll instances per section
- synchronize it with GSAP where required
- ensure normal browser accessibility behavior is preserved
- verify keyboard/page navigation still works
- disable or reduce smoothness on low-power/mobile contexts when beneficial

Smooth scrolling should make the site feel controlled, not trapped inside a CSS swamp.

---

# 35. WebGL Interaction Patterns

Potential reusable effects:

## 35.1 Image displacement

Pointer or scroll changes a shader displacement field.

## 35.2 RGB shift

Use subtly on hover or transitions.

## 35.3 Liquid distortion

Use for premium hero/case-study moments.

## 35.4 Particle field

Use only when the particles represent a concept or provide meaningful depth.

## 35.5 3D camera movement

Map:

```text
scroll → camera position
pointer → camera rotation
section progress → scene state
```

Keep camera movement smooth and bounded.

---

# 36. Data / Content Architecture

Motion should be driven by content structure where practical.

For project/gallery sections, define data such as:

```ts
{
  title,
  category,
  image,
  video,
  description,
  href,
  theme,
  index,
}
```

Then render through a reusable presentation system.

Do not hardcode every card separately.

---

# 37. SEO & Semantics

Experimental visuals must not compromise:

- heading hierarchy
- document landmarks
- metadata
- Open Graph
- canonical URLs
- crawlable content
- meaningful links
- accessible buttons

Keep the semantic HTML layer strong beneath the visual layer.

---

# 38. Testing Strategy

Use the installed `playwright-testing` skill.

Test at minimum:

### Functional
- all navigation links
- all CTAs
- forms
- route transitions
- interactive controls
- API-driven content

### Visual
- desktop hero
- desktop long-scroll
- mobile hero
- mobile long-scroll
- menu open/close
- hover states
- page transitions

### Motion
- scroll through every animated section
- reverse scroll
- fast scroll
- slow scroll
- resize while animation is active
- browser back/forward
- reduced-motion mode

### Performance
- cold load
- cached load
- mid-range desktop
- mid-range mobile
- WebGL fallback

---

# 39. Agent QA Loop

Use this loop repeatedly:

```text
BUILD
  ↓
RUN
  ↓
SCREENSHOT / RECORD
  ↓
CRITIQUE
  ↓
FIX HIERARCHY
  ↓
FIX MOTION
  ↓
FIX PERFORMANCE
  ↓
TEST
  ↓
REPEAT
```

Do not stop after the first successful build.

---

# 40. Screenshot-Based Visual Review

For each major route, review:

1. first viewport
2. mid-page section
3. major animation moment
4. mobile first viewport
5. mobile content section
6. navigation open state
7. final CTA/footer

Look for:

- accidental clipping
- text collisions
- awkward whitespace
- broken image aspect ratios
- animation jumps
- over-dense sections
- generic-looking UI
- alignment inconsistencies
- poor contrast
- sticky/pinned bugs

---

# 41. Browser Breakpoint Matrix

At minimum inspect:

```text
360 × 800
390 × 844
768 × 1024
1024 × 768
1280 × 800
1440 × 900
1920 × 1080
```

Do not assume one desktop breakpoint is enough.

---

# 42. Interaction Matrix

Every interactive element should specify:

```text
DEFAULT
HOVER
FOCUS
ACTIVE
DISABLED
TOUCH
REDUCED MOTION
```

Every motion component should specify:

```text
DESKTOP
TABLET
MOBILE
REDUCED MOTION
FALLBACK
```

---

# 43. Completion Criteria

The agent must not declare the work finished until all are true:

### Design
- [ ] visual concept is coherent
- [ ] typography is deliberate
- [ ] layout is distinctive
- [ ] palette is constrained
- [ ] imagery follows one art direction
- [ ] hierarchy is clear

### Motion
- [ ] hero has intentional entrance motion
- [ ] major sections have meaningful scroll behavior
- [ ] scroll reveals are staged
- [ ] at least one strong scrub/pinned narrative moment exists where appropriate
- [ ] at least one memorable microinteraction exists
- [ ] cursor behavior is intentional on desktop when appropriate
- [ ] navigation has polished state transitions
- [ ] route transitions are polished where routes justify them

### Interaction
- [ ] buttons have hover/focus/active states
- [ ] links have clear responses
- [ ] media interactions are intentional
- [ ] touch behavior is correct

### Responsive
- [ ] desktop is intentionally art-directed
- [ ] mobile is intentionally designed, not merely collapsed
- [ ] heavy effects have sensible mobile fallbacks

### Accessibility
- [ ] reduced motion works
- [ ] keyboard interaction works
- [ ] focus styles are visible
- [ ] semantic structure is correct
- [ ] contrast is acceptable

### Performance
- [ ] no obvious scroll jank
- [ ] no unnecessary animation loops
- [ ] media optimized
- [ ] WebGL lazy-loaded or appropriately scoped
- [ ] no large performance regressions

### Quality
- [ ] no broken functionality
- [ ] no console errors
- [ ] no hydration warnings where applicable
- [ ] no duplicate event listeners
- [ ] no memory leaks from animation cleanup
- [ ] tests pass
- [ ] build passes

---

# 44. Recommended Build Order

Do not start by adding random effects.

## Phase 1 — Reconnaissance

- inspect repository
- inspect existing UI
- inspect all skill files
- inspect routes/components
- identify constraints
- capture baseline screenshots

## Phase 2 — Art Direction

Define:

- concept
- typography
- color
- imagery
- layout language
- motion language

## Phase 3 — Foundation

Implement:

- design tokens
- layout system
- typography system
- responsive primitives
- visual primitives

## Phase 4 — Hero

Build the highest-impact visual scene first.

## Phase 5 — Core Scroll Story

Implement:

- reveal system
- parallax
- scrub
- pinned storytelling
- section transitions

## Phase 6 — Interaction Layer

Implement:

- cursor
- magnetic elements
- hover states
- menu animation
- image interactions

## Phase 7 — Advanced Visuals

Only now add:

- WebGL
- Three.js
- shader effects
- video scrubbing
- complex transitions

## Phase 8 — Mobile

Create deliberate mobile behavior, not a desktop downgrade.

## Phase 9 — Performance & Accessibility

Run:

- performance pass
- reduced-motion pass
- keyboard pass
- mobile hardware pass

## Phase 10 — Slop Removal

Use:

- `anti-ui-slop`
- `unslop`
- `unslop-ui`
- `ui-radar`
- `design-taste-frontend`

Critique and remove generic patterns.

## Phase 11 — QA

Use:

- `playwright-testing`
- `web-perf`
- `agent-security-audit`
- `react-best-practices`
- `nextjs`

## Phase 12 — Final Polish

Do three focused passes:

1. hierarchy
2. motion
3. performance

Do not attempt all three at once.

---

# 45. Priority Order

When time is limited, optimize in this order:

```text
1. visual concept
2. typography
3. hero
4. layout composition
5. scroll storytelling
6. core interactions
7. responsive behavior
8. performance
9. WebGL / advanced effects
10. decorative polish
```

This prevents spending six hours polishing a cursor while the page still looks like a bootcamp dashboard.

---

# 46. Minimum “Awwwards-Style” Feature Set

A strong implementation should usually contain some combination of:

- oversized typography
- editorial/asymmetric composition
- cinematic hero
- staged reveal animations
- scroll-linked motion
- parallax depth
- one pinned storytelling section
- one strong image/media transformation
- polished hover states
- contextual cursor on desktop
- animated navigation/menu
- page transitions where justified
- texture/grain where appropriate
- responsive mobile motion strategy
- reduced-motion mode
- strong performance discipline

Not every site needs every effect.

---

# 47. What “Winning-Level” Means

The output should not merely resemble an award site in screenshots.

It should behave like a coherent designed object.

The user should be able to feel:

```text
I know where to look.
        ↓
I understand what this is.
        ↓
The interface responds to me.
        ↓
The scroll reveals something.
        ↓
The motion supports the story.
        ↓
The final interaction feels memorable.
```

The strongest result is not the one with the most effects.

It is the one where the **design, motion, content, interaction and technology feel like they were conceived together.**

---

# 48. Final Agent Instruction

Before finishing, explicitly answer these questions in your internal implementation notes:

1. What is the site's central visual concept?
2. What makes the hero memorable?
3. What is the primary scroll narrative?
4. Which animation is the signature interaction?
5. Which interactions are micro-level polish?
6. Where is WebGL/3D justified, if anywhere?
7. What changes on mobile?
8. What happens with reduced motion?
9. What performance risks were introduced?
10. What generic/AI-looking patterns were removed?
11. What existing product functionality was preserved?
12. What was tested after the redesign?

If the answers are vague, the design is not finished.

---

# 49. Source & Inspiration Notes

Awwwards references used to shape this specification include:

- Awwwards Sites of the Day / element taxonomy: https://www.awwwards.com/websites/sites_of_the_day/
- Brontide SOTD, highlighting scroll interaction, horizontal parallax navigation, 3D, WebGL, transitions and animation: https://www.awwwards.com/sites/brontide
- Studio DOT interaction example, showing GSAP + WebGL + Three.js, scroll distortion, domain scrolling, button hover, menu animation, case-study layouts and title animation: https://www.awwwards.com/inspiration/slider-drag-and-drop-with-distortion-studio-dot-2
- House of Dreamers page detail, showing WebGL + GSAP, mouse fluid effect, main menu and page transitions: https://www.awwwards.com/inspiration/page-detail-house-of-dreamers

Use these sources for inspiration and pattern analysis, not for copying a specific site's visual identity.
