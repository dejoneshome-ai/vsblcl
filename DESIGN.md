# Design

Visual system for VisibleCymru. Single self-contained `index.html` (no build step).

## Theme

Bright, warm and welcoming, unmistakably mid-Wales. A **warm off-white** is the dominant
surface with dark near-black text; the mid-Wales **green is an accent** (muted sage, dulled
down — never a drench), terracotta is the primary call-to-action, and gorse-gold is the
secondary highlight. A handful of deliberate green-accent moments give rhythm: the marquee
ribbon, the featured pricing tier, the launch-partner panel, and the "Made here" hills band.
The **hero is a full-bleed aerial photo** (`hero.jpg`) of the local landscape under a
neutral slate scrim, with a sky→fields gradient fallback until the file is added. Local
motifs: OS-map contour lines, hills, grazing sheep, a bilingual *Croeso* touch.

## Color

White-dominant, green as accent (hex tokens in `:root`).

| Token | Value | Role |
|---|---|---|
| `--bg` `--surface` `--surface-2` | `#F8F7F1` `#FFFFFF` `#F1EFE6` | warm off-white body, cards, alt bands |
| `--ink` `--ink-2` `--muted-2` | `#1B241E` `#515A52` `#6C7670` | text ramp on white |
| `--forest` `--forest-2` `--moss` | `#2C453B` `#334D42` `#3E5C4F` | **muted** sage-green accent blocks |
| `--green` `--green-deep` `--green-soft` | `#2E6B52` `#245A44` `#E8F0EA` | accent green text/icons + pale tint |
| `--clay` | `#DE6B41` | terracotta accent / illustration |
| `--clay-btn` | `#BE5029` | terracotta **button backgrounds** (white text, AA) |
| `--clay-text` | `#A0431B` | terracotta **text on white** (AA) |
| `--ochre` `--gold-text` | `#E7AC3E` `#976B12` | gorse gold — fills / gold text on white |
| `--cream` `--cream-2` | `#F6EFDF` `#CFDACD` | text on the green accent blocks |

Contrast verified AA+: ink 14.9:1 on bg, ink-2 6.7:1, green-accent 5.9:1 on white,
clay-text 5.5:1 on white, white/cream 9–10:1 on the muted green, ochre 5.1:1 on green,
white 4.6:1 on every terracotta button/CTA. Mid-tone `--clay` is never used for text or
labels — `--clay-btn` / `--clay-text` are.

## Hero photo

Drop a landscape aerial photo in as **`hero.jpg`** (≈2000px wide) at the repo root. It's
loaded as a CSS background on `.hero-photo` with a neutral slate scrim (`.hero-overlay`)
weighted left+top so the white headline and light nav stay legible over a bright sky. Until
the file exists, a sky→fields gradient stands in. Reduced-motion needs nothing special —
it's a still image, not video.

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
