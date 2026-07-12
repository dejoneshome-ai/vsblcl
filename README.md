# VisibleCymru

Marketing site for **VisibleCymru** — helping mid-Wales places to stay (B&Bs,
self-catering, farm stays, guesthouses and small hotels) get **found online** and
**booked direct**, with no commission handed to Booking.com or Airbnb.

A single self-contained `index.html` — no build step, no framework, no dependencies.
Just open it, or serve the folder.

## What's on the page

- **Free visibility snapshot** — an interactive demo that plays out what a guest sees
  when they search your name on Google, Maps and Facebook.
- **OTA commission calculator** — slide in your nightly rate and monthly bookings and
  see, live, what you lose to the OTAs each year versus what you'd keep direct.
- **Direct Booking System** — the named product: real-time availability calendar,
  secure card payments, mobile-first guest flow, zero OTA commission.
- **The service ladder** — free Snapshot → £75 Visibility Package → £395 Website, with
  the Direct Booking System as the next step or a standalone add-on.
- **Launch-partner** places, an about section, FAQ and contact.

## Design

The visual system (Slate & Sage palette, typography, motion, components) is documented
in [`DESIGN.md`](DESIGN.md); the strategic brief (users, purpose, principles,
accessibility) in [`PRODUCT.md`](PRODUCT.md). Built to WCAG AA, fully responsive
(375 / 768 / 1024 / 1440), with full `prefers-reduced-motion` support.

## Run it

```bash
# just open the file
open index.html        # macOS
xdg-open index.html    # Linux

# or serve the folder
python3 -m http.server 8000   # then visit http://localhost:8000
```

## Files

| File | Purpose |
|------|---------|
| `index.html` | The site — all HTML, CSS and JS inline |
| `dylan.jpg` | Founder photo (about section) |
| `og.png` | Social-share preview image |
| `visiblelocal.html` | Redirect stub for the old VisibleLocal URL |

> **Deploying to a real domain:** the social-share (`og:`) and canonical URLs in
> `index.html` still point at the placeholder `vocal-blancmange-3d3b47.netlify.app`.
> Swap those for your own domain (e.g. `https://visiblecymru.cymru`) when it's live.
