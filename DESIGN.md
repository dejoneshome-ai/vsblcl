# Design

Visual system for VisibleCymru. Single self-contained `index.html` (no build step).

## Theme

Bold, warm and unmistakably mid-Wales. A **deep sage-forest drench** (the colour of the
Cambrian hills) is the dominant surface, lifted by warm cream, terracotta and gorse-gold,
with warm-charcoal for the moody "problem" moments and warm-**cream paper** sections for
the two focal moments (the Direct Booking System and the founder story) so they feel
bright and welcoming. Local motifs throughout: OS-map contour lines, layered hills, a few
grazing sheep, and a bilingual *Croeso* touch. Committed / full-palette strategy — the
warmth is carried by colour, illustration and copy, never by a timid near-white body.

## Color

Full palette, art-directed per section (hex tokens in `:root`).

| Token | Value | Role |
|---|---|---|
| `--forest` `--forest-2` `--moss` | `#173229` `#1D3E33` `#2B5647` | body + raised forest surfaces |
| `--char` | `#191712` | warm charcoal — OTA-leak section, footer |
| `--paper` `--paper-2` | `#F6EFDF` `#EFE6D2` | warm cream sections (booking, about) & cards |
| `--cream` `--cream-2` `--cream-3` | `#F6EFDF` `#D3DBCB` `#9FB2A5` | text ramp on dark |
| `--ink` `--ink-2` | `#211E17` `#5A5445` | text on paper |
| `--clay` | `#DE6B41` | terracotta accent / illustration |
| `--clay-btn` | `#BE5029` | deeper terracotta — **button backgrounds** (white text, AA) |
| `--clay-text` | `#A0431B` | dark terracotta — **terracotta text on cream** (AA) |
| `--clay-hi` | `#F0855C` | bright terracotta — text on dark, hover |
| `--ochre` `--ochre-deep` | `#E7AC3E` `#C58E2A` | gorse gold — secondary highlight |
| `--sage` `--sage-soft` | `#6FA089` `#9DBFAE` | sage — contour lines, hills |

Contrast verified AA+: cream 12:1 on forest, clay-hi 5.4:1 on forest, ochre 6.8:1 on
forest, ink 14.5:1 on paper, clay-text 5.5:1 on paper, white 4.6–4.8:1 on every terracotta
button/feature/CTA surface. Mid-tone `--clay` is **never** used for text or button labels —
that's what `--clay-btn` / `--clay-text` are for.

## Typography

**Single family: Bricolage Grotesque** (opsz 12–96, wght 400–800) — the committed brand
identity, pushed to a big, friendly display weight (`clamp(42px,6vw,74px)`,
letter-spacing −0.035em). Body 1.62 line-height. Headings `text-wrap:balance`, prose
`pretty`, measure capped ~66ch, tabular figures on money.

## Motion

Ease-out only (`--ease` = `cubic-bezier(.22,1,.36,1)`), no bounce/overshoot. Headline
word-rise, scroll reveals (2.6s failsafe so nothing ships blank), floating booking cards,
animated count-up in the calculator, hills parallax, magnetic CTAs (fine-pointer only).
Full `prefers-reduced-motion` block disables all and shows final states.

## Section rhythm & signature components

Deliberate light/dark cadence: forest hero → charcoal OTA-leak → **cream** Direct Booking
→ forest snapshot/ladder/how/launch/who → **cream** About → forest hills band → forest
FAQ → terracotta CTA → charcoal footer. Wavy SVG `paper-edge` transitions between worlds.

- **Hero** — forest-drenched, booking calendar card as the visual (0% commission), *Croeso*.
- **OTA calculator** — sliders (nightly rate up to **£1,500**, bookings/mo) → live £ lost vs
  kept, animated, `aria-live`. 15% commission constant.
- **Direct Booking System** — the star, on cream paper: feature list + booking mockup.
- **Free snapshot** — the relocated interactive phone demo (free tier of the ladder).
- **Launch partner** — honest 2-of-5 capacity scarcity.
- **Hills band** — layered SVG hills, parallax, soft sun, grazing sheep.

## Layout

`.wrap` max-width 1160px, 26px gutters. Full-bleed section wrappers own their colour
worlds. Breakpoints 1024 / 920 / 640 / 400. Nav collapses to call + CTA below 920.
No repeated uppercase eyebrows — sentence-case kickers used as light wayfinding.
