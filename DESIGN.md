# Design

Visual system for VisibleCymru. Single self-contained `index.html` (no build step).

## Theme

Dark, editorial, grounded — "Slate & Sage", evolved. A slate near-black base (with a
faint sage undertone) lit by warm terracotta and amber, with deep sage as a second
surface world for the Direct Booking System, the final CTA and the Welsh-hills band.
Physical reference: mid-Wales at dusk — slate roofs, bracken, gorse, hearth light.
Committed colour strategy; warmth carried by accent + type + copy, not by a tinted body.

## Color

OKLCH-reasoned, expressed as hex tokens (`:root`).

| Token | Value | Role |
|---|---|---|
| `--bg` | `#0A0D0E` | body — slate near-black |
| `--surface` `--card` `--card-2` | `#12171A` `#161C1F` `#1C2429` | raised surfaces |
| `--sage-deep` `--sage` `--sage-hi` | `#0B201C` `#123028` `#1B463B` | sage surface world |
| `--ink` `--soft` `--muted` | `#F4EFE5` `#CDC6B6` `#9AA69E` | warm cream text ramp |
| `--terra` `--terra-hi` | `#E6613A` `#FB7C52` | primary accent / CTA; bright variant for text-on-dark |
| `--amber` `--amber-deep` | `#EBAE3E` `#CB932E` | secondary highlight |
| `--on-accent` | `#1C0E07` | dark ink on terracotta/amber buttons |

Contrast verified: ink 17:1, soft 11.5:1, terra-hi 7.5:1, terra 5.7:1, on-accent-on-terra
5.5:1 — all AA+. Use `--terra-hi` (not `--terra`) for small terracotta text.

## Typography

**Single family: Bricolage Grotesque** (opsz 12–96, wght 400–800) — the existing,
distinctive brand identity; kept and pushed harder on optical-size + weight contrast
rather than paired with a reflex serif. Body 1.62 line-height (raised for light-on-dark).
Display: `clamp(38px,5.2vw,62px)`, letter-spacing −0.032em. Headings `text-wrap:balance`,
prose `text-wrap:pretty`, measure capped ~66ch. Tabular figures on prices/calculator.

## Motion

Ease-out only — `--ease` = `cubic-bezier(.22,1,.36,1)`, `--ease-soft` = ease-out-cubic.
No bounce/overshoot (the old calendar-pin overshoot was removed). Headline word-rise,
IntersectionObserver scroll reveals (with a 2.6s failsafe so nothing ships blank),
animated count-up in the OTA calculator, hill parallax, magnetic CTAs (fine pointer only).
Full `prefers-reduced-motion` block disables all and shows final states.

## Signature components

- **Snapshot demo** — phone mockup that plays search → local-results for the visitor's name.
- **OTA commission calculator** — two sliders (rate, bookings/mo) → live £ lost vs kept,
  animated, `aria-live` headline. 15% commission constant.
- **Direct Booking System mockup** — availability calendar with booked/available/selected
  states, "0% commission" badge, "confirm & pay direct".
- **Launch-partner panel** — 2-of-5 filled slots, honest capacity scarcity.
- **Welsh-hills band** — layered SVG hills with scroll parallax and a soft sun.

## Layout

`.wrap` max-width 1120–1140px, 24px gutters. Full-bleed section wrappers (`.leak`,
`.dbs`, `.band`) break out of the container for their own colour worlds. Breakpoints:
1024 / 920 / 640 / 380. No repeated uppercase eyebrows — light sentence-case `.index-cue`
wayfinding on a few sections only. Cards used only where they're the right affordance
(pricing ladder, FAQ); features are dividered lists, not card grids.
