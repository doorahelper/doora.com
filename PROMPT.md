# DOORA LANDING PAGE — BUILD FROM SCRATCH

Build a production-ready responsive landing page that matches the Figma design screenshots in `/design-reference/`. There is a mobile version and a desktop version — both must work from a single codebase.

## TECH REQUIREMENTS
- Single `index.html` file with all CSS and JS inline
- No frameworks, no React, no build step — this deploys directly to GitHub Pages
- Google Fonts: Inter (weights 400, 500, 600, 700)
- Mobile-first CSS with desktop breakpoint at 768px
- Must work on real iOS Safari and Android Chrome

## DESIGN SYSTEM
- Brand gradient: #F0A9D8 → #BB9AE4 → #53BCFF
- Dark hero gradient: #3D1A2F → #1E1440 → #0B2242
- Body text: #1A1A2E
- Muted text: #6B7280
- Borders: #E5E7EB
- Card radius: 8px, button radius: 6px
- Letter-spacing: -0.02em on headings
- Line-height: 1.15 headings, 1.6 body

## VISUAL ZONES (backgrounds, top to bottom)
1. Hero — dark gradient (#3D1A2F → #1E1440 → #0B2242)
2. Door cards — white #FFFFFF
3. Carousel — lavender #F8F6FB
4. Doora Card section — warm #FAF3F6
5. Trust band (data file card) — dark gradient (same as hero)
6. CTA — light #F8F9FB
Use 48px gradient fade transitions between zones, no hard edges.

## LAYOUT DIFFERENCES: MOBILE vs DESKTOP
- **Hero**: Mobile = stacked (headline, free for renters, trust ticker, avatar, chat, value props). Desktop = split layout (headline + trust info LEFT 50%, chat preview RIGHT 50%)
- **Door cards**: Both = side by side grid. Desktop max-width 700px centered
- **Carousel**: Mobile = swipe. Desktop = arrow buttons on sides, card max-width 520px centered
- **Doora Card section**: Mobile = stacked. Desktop = split layout (text + button LEFT, card visual RIGHT), max-width 960px
- **Trust band data card**: Mobile = centered card. Desktop = split layout (heading LEFT, card RIGHT), max-width 960px
- **CTA**: Both = centered, buttons side by side on desktop, stacked on mobile. Max-width 640px

## SECTIONS (top to bottom)

### 1. NAV BAR
- Fixed top, transparent on dark hero, backdrop-blur
- Left: hamburger icon (mobile) + "DOORA" text in white, font-weight 700, letter-spacing 0.1em, 18px. On desktop use the wordmark image from `/assets/doora-wordmark.png`
- Right: "Sign in" link, white, font-weight 500

### 2. HERO (dark gradient background)
- **Headline**: "Nobody explains renting. We do." — white, 32px mobile / 44px desktop, font-weight 700. "explains" has an animated wavy underline in #7AB4E0 that draws on page load.
- **"Free for renters"**: plain text below headline, 16px mobile / 18px desktop, font-weight 500, white at 60% opacity. NOT a pill, just text.
- **Trust ticker**: "BACKED BY" in 11px all-caps, letter-spacing 0.06em, white at 35% opacity. Then fixed vertical divider "|" (1px, white at 15%, 16px tall). Then scrolling marquee of names: REINSW · Ray White · Tenants' Union NSW · LJ Hooker · Shelter NSW · McGrath · Belle Property · Better Renting · Raine & Horne · Laing+Simmons · Evolve Housing · Cobden Hayson · Bresic Whitney · WIRE · PPD Real Estate · Stone Real Estate · Home in Place. Names 13px, font-weight 600, white at 60%. Continuous scroll left, 30s cycle.
- **Chat preview**: Avatar circle (gray #D1D5DB bg, white "C", 32px) with green dot (#22C55E, 8px). "Chris · Doora Helper" in 13px, font-weight 500, white at 70%.
  - Card with gradient border (brand gradient, 1px), white bg inside
  - Helper bubble: "Hi! Let's map your journey." — #F3F4F6 bg, dark text
  - User bubble: rotating messages (blue #007AFF bg, white text) — cycles every 5 seconds with typing dots before each
  - "Delivered" tag, typing dots, message input with send button
  - **CRITICAL**: Set chat message area to FIXED HEIGHT matching tallest message (3 lines) so container never shifts
- **Value props**: "Free · Human rental support · Your data, your control" — white at 50%, 13px
- Desktop: headline + free for renters + ticker on LEFT, chat preview on RIGHT, both vertically centered

### 3. DOOR CARDS (white background)
- Two cards side by side, grid, gap 12px mobile / 20px desktop
- Max-width 700px on desktop, centered
- Each card: white bg, 1px #E5E7EB border, 8px radius, 24px padding, text-align center
- Card 1: chat-icon.png (40px), "Free Renting Help" (16px bold), "A real person. Free." (13px gray), "Average reply: under 30 mins" (12px gray), "Message" button (blue #007AFF, white text, 6px radius, full-width)
- Card 2: card-icon.png (40px), "Create Doora Card" (16px bold), "One application you own." (13px gray), "Takes about 10 minutes" (12px gray), "Create" button (gradient, white text, 6px radius, full-width)
- Section: 24px space above from hero, 32px below

### 4. DOORA CARD SECTION (warm #FAF3F6 background)
- Heading: "You shouldn't have to prove yourself 20 times." — 28px mobile / 34px desktop, font-weight 700
- Copy: "One application. Every agency." + "You see who's viewed it." — 15px, #6B7280
- Button: "Get your Doora Card" — gradient bg, white text, 6px radius. Max-width 240px on desktop, left-aligned
- Doora Card mockup (HTML/CSS, not an image):
  - Gradient border (2px, brand gradient), 12px radius
  - Tilt: transform rotate(2deg)
  - Shadow: 0 8px 32px rgba(0,0,0,0.1)
  - Ghost card behind: same shape, offset 8px, opacity 0.15
  - Content: "DOORA CARD" label (11px caps), green "Ready" badge, "Liam B., Tash R. & Dev P." (18px bold), "Share house · 3 applicants" (13px gray), divider, three agency rows:
    - Green dot: "Ray White Newtown · Viewed 3h ago"
    - Blue dot: "LJ Hooker Marrickville · Sent yesterday"
    - Blue dot: "Laing + Simmons Randwick · Sent yesterday"
  - "Revoke access" link (blue, underlined)
- Desktop: split layout — text + button LEFT, card RIGHT

### 5. CAROUSEL (lavender #F8F6FB background)
- Card: white bg, 8px radius, shadow 0 2px 12px rgba(0,0,0,0.06), padding 32px
- "THINGS NOBODY TELLS RENTERS." label top-left, 11px caps, #6B7280
- Watermark number top-right ("01"-"05"), 48px, #E5E7EB, font-weight 700
- Left accent bar: 4px wide, full height, color varies per slide
- Divider below headline: 1px #E5E7EB
- Credibility tag: small pill with clock icon, gray
- Desktop: arrow buttons (40px circles, #F3F4F6, 1px border) on each side
- Dots: 5 dots, 8px, active = gradient bar 16px wide
- Below dots: "YOUR HELPER WALKS YOU THROUGH ALL OF IT." — 11px caps, #9CA3AF

5 slides:
1. Accent = full gradient. "The advertised rent isn't fixed." / "You can negotiate — at application, at renewal, and mid-tenancy." / "Applies in NSW, VIC, QLD"
2. Accent = #F0A9D8. "Your application gets 30 seconds." / "PMs don't read every word. They filter. Completeness is everything." / "Based on 2,400+ PM interviews"
3. Accent = #BB9AE4. "The condition report matters more than your lease." / "It decides every bond dispute. Most renters don't know it exists." / "Bond disputes · #1 renter issue"
4. Accent = #53BCFF. "You can break a lease without penalty." / "Hardship provisions exist in every state. Most renters don't know." / "Residential Tenancies Act"
5. Accent = #007AFF. "Your rental data is worth more than you think." / "Platforms sell renter analytics. Doora gives you control instead." / "Data sovereignty · your right"

Auto-advance 6s, pause on hover, swipe on mobile, min-height to prevent size jumping.

### 6. TRUST BAND — DATA FILE CARD (dark gradient background)
- **Mobile**: Centered card, max-width 360px
- **Desktop**: Split layout max-width 960px. LEFT: "Your data, your rules." (32px, font-weight 700, white 90%). Below: "You'd be surprised what other platforms keep." (16px, white 40%). RIGHT: the data file card, max-width 400px, right-aligned.
- Card: 1px white/10% border, 12px radius, padding 28px 24px, bg white at 3%
- "YOUR DATA FILE" header (10px caps, white 35%)
- Three rows with 1px dividers (white 8%):
  - "Renter profiles" (13px, white 45%) → "We don't build them" (13px, 600 weight, white 80%)
  - "Your information" → "Never sold. Never shared."
  - "When you're done" → "Everything is deleted" (brand gradient text)
- All values right-aligned within the card

### 7. CTA (light #F8F9FB background)
- "Get started — it's free." — 34px mobile / 42px desktop, font-weight 700
- "The step before the search." — 16px, #6B7280, font-weight 500
- "Free for renters. Always." — 13px, #9CA3AF
- Two buttons: "Message a Helper" (blue, chat SVG icon) + "Create Doora Card" (gradient, card SVG icon). Side by side desktop, stacked mobile.
- Divider (1px #E5E7EB, max-width 120px centered)
- Footer: "Privacy · Terms · Contact" — 12px, #9CA3AF

### 8. JAVASCRIPT
1. Chat rotation: 8 messages, 5s interval, typing dots transition
2. Trust ticker: CSS marquee, continuous, 30s cycle
3. Carousel: auto-advance 6s, swipe (touch events), arrow clicks, dot clicks, pause on hover
4. Nav: hidden on hero, shows with backdrop-blur on scroll
5. Underline animation: draws on page load via CSS animation (background-size 0% to 100%)

## CHAT MESSAGES (all 8)
1. "I keep getting rejected and I don't know what I'm doing wrong."
2. "We're moving from Melbourne — is Sydney really this hard?"
3. "I'm on Centrelink. Do agents even look at my application?"
4. "Single mum, two kids, no lease in my name before."
5. "My income's legit but it's across three ABNs. How do I show it?"
6. "We land in 5 weeks. We have nowhere to stay."
7. "Our rent just went up 30%. We have to move but where?"
8. "I've applied for 9 places this month. Not one callback."

## DEPLOYMENT
Create a fresh repo from scratch. Structure:
```
doora-landing-v8/
├── index.html
├── assets/
│   ├── doora-wordmark.png
│   ├── chat-icon.png
│   └── card-icon.png
├── design-reference/
│   └── (Figma screenshots go here)
└── README.md
```

Initialize git, create GitHub repo `doora-landing-v8` under `doorahelper`, push, enable GitHub Pages from main branch root.

## PIXEL MATCHING
Reference the design screenshots in `/design-reference/` for exact spacing, sizing, and proportions. Mobile is primary reference — desktop adapts. Match screenshots as closely as possible. If ambiguous, err on more whitespace and cleaner spacing.
