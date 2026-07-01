# NB Oktoberfest 2026 — Landing Page

Astro + Formspree. Static build, deploys anywhere (Vercel recommended, matches
your existing workflow).

## Run it locally

```bash
npm install
npm run dev
```

Opens at http://localhost:4321

## Before this goes live, you need to:

1. **Formspree ID** — in `src/components/SponsorForm.astro`, replace
   `YOUR_FORM_ID` with your real Formspree form ID (paid plan needed for the
   logo file upload field to work).

2. **Eventbrite link** — in `src/components/Tickets.astro`, set
   `eventbriteUrl` to your Eventbrite event URL and flip `ticketsLive` to
   `true`. Until then it shows a "Tickets Coming Soon" state.

3. **Domain** — point wherever you're hosting (Vercel CLI, same as your other
   projects) at the domain you land on.

## About the hero parallax

This is true multi-object parallax, built from the 13 isolated layer
exports (`public/images/layers/`) — wood background, sun, clouds, ocean,
lighthouse, boat, birds, mermaid, keg, stein-and-barley, the "20 Years of
Cheers" ribbon, the SCBA badge, and the Oktoberfest wordmark lockup. Each
one is independently positioned and scrolls at its own `data-speed` in
`Hero.astro` — background elements barely move, foreground elements
(mermaid, keg) drift fastest, giving real depth instead of flat strips.

Positioning is done with percentage `top/left/right/bottom` + `max-width`,
so it holds together across desktop widths but isn't pixel-perfect at
every viewport — if something looks off at your actual screen size, the
values to nudge are right at the top of each `.layer-*` rule in
`Hero.astro`.

Mobile (≤720px) always shows the flat `full-poster.jpg` with no parallax,
per your call to keep mobile simple.

## Content that's carried over as placeholders

- **Sponsorship tiers/pricing** — same 7 levels as 2025, confirmed current.
- **Impact stats** ($100K+ raised, 1,500+ attendees, 18 orgs) — 2025 numbers,
  reused until you send updated ones.
- **Board member referral list** — same 18 names from the 2025 Jotform.

## Fonts

- Display: **Rye** (Google Fonts) — vintage tavern/woodtype feel for
  headlines, echoes the poster's blackletter without being illegible at
  body sizes.
- Body: **Work Sans**
- Labels/data (prices, dates, form labels): **JetBrains Mono** — gives the
  ticket-stub/ledger feel to the sponsorship tier cards.

Colors are all sampled directly from `poster_concept.png`, not invented —
see the token comments at the top of `src/styles/global.css`.
