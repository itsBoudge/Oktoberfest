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

## Hero

Scaled back from the earlier layered parallax to a simple static hero:
`public/images/hero/desktop-hero.jpg` on screens >720px, `mobile-hero.jpg`
below that, swapped via a `<picture>` element in `Hero.astro`. No JS, no
scroll listeners.

Venue/date/CTAs live in their own dark section right below the hero
(`EventBar.astro`), not overlaid on the photo — includes the Oktoberfest
wordmark lockup (`public/images/brand/oktoberfest-logo.webp`).

## Bands / lineup

`Bands.astro` — background image at `public/images/bands/bands-bg.jpg`,
headliner called out separately from the support acts. Update the
`supportActs` array and `headliner` const at the top of that file as the
lineup firms up.

## Content that's carried over as placeholders

- **Sponsorship tiers/pricing** — same 7 levels as 2025, confirmed current.
- **Impact stats** ($100K+ raised, 1,500+ attendees, 18 orgs) — 2025 numbers,
  reused until you send updated ones.
- **Board member referral list** — confirmed current names.

## Fonts

- Display: **Rye** (Google Fonts) — vintage tavern/woodtype feel for
  headlines, echoes the poster's blackletter without being illegible at
  body sizes.
- Body: **Work Sans**
- Labels/data (prices, dates, form labels): **JetBrains Mono** — gives the
  ticket-stub/ledger feel to the sponsorship tier cards.

Colors are all sampled directly from `poster_concept.png`, not invented —
see the token comments at the top of `src/styles/global.css`.
