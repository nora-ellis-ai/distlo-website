# Distlo — Website

**Live site:** [distlo.in](https://distlo.in)  
**Hosting:** GitHub Pages (free)  
**Repo:** github.com/nora-ellis-ai/distlo-website

---

## What This Is

The official website for Distlo — an AI-assisted, human-led LinkedIn content repurposing service. Built as a single-file static site hosted on GitHub Pages.

---

## Tech Stack

- Single file: `index.html` (HTML + CSS + JS — no frameworks, no dependencies)
- Fonts: Google Fonts (Fraunces + Plus Jakarta Sans)
- Form: Formspree (endpoint `xgopgkwb`) → submissions to `hello@distlo.in`
- Hosting: GitHub Pages via custom domain `distlo.in`
- DNS/HTTPS: Managed via domain registrar pointing to GitHub Pages

---

## Page Structure

Sections in order:

1. **Nav** — Logo + theme toggle + "Get Free Sample" CTA
2. **Hero** — Headline, subtext, primary CTA (geo-aware price), ghost CTA
3. **Stats Strip** — 5+ outputs / 3 days / 1 input / 0 calls
4. **Deliverables** — 4 cards: 5 posts / 10 hooks / 3 CTAs / 1 carousel
5. **How It Works** — 4-step process (Send → Extract → Receive → Post)
6. **Visual Proof** — Phone mockup + proof points for target niches
7. **Pain Points** — 4 rows addressing common objections
8. **SIGNAL Framework** — 6 animated rows (S/I/G/N/A/L) with scroll-in animation
9. **Pricing** — 3 cards: Starter / Standard / Monthly Retainer (geo-aware)
10. **Contact** — Formspree form + process mini-steps
11. **Footer** — Logo + email + domain

---

## Geo-Tagged Pricing

Visitor country is detected via `ipapi.co/json` (free tier, 1000 req/day, no API key required).

Pricing updates automatically on page load for 5 elements:
- Hero CTA button text
- Pricing card: Starter
- Pricing card: Standard
- Pricing card: Monthly Retainer
- Form dropdown options (Starter / Standard / Retainer)
- Currency badge (shown for non-India visitors only)

**Currency map:**

| Country | Starter | Standard | Retainer |
|---------|---------|----------|----------|
| India (IN) | ₹2,999 | ₹4,999 | ₹20K+ |
| UAE (AE) | AED 199 | AED 349 | AED 1,299/mo |
| Singapore (SG) | SGD 79 | SGD 129 | SGD 499/mo |
| UK (GB) | £49 | £79 | £299/mo |
| All others | $49 | $79 | $299/mo |

India visitors see no change. Badge is hidden for India, visible for all other countries.

To add a new country, add one entry to the `PRICING` object in the `<script>` block at the bottom of `index.html`:

```javascript
CA: { starter: 'CAD 69', standard: 'CAD 109', retainer: 'CAD 399', flag: '🇨🇦', label: 'Prices in Canadian Dollars (CAD)' },
```

---

## Contact Form

- **Provider:** Formspree
- **Endpoint:** `https://formspree.io/f/xgopgkwb`
- **Domain restriction:** distlo.in only (configured in Formspree dashboard)
- **Submissions go to:** hello@distlo.in
- **Fields:** Name, Email, Role (dropdown), Pack interest (geo-aware dropdown), Message (optional)

---

## Design Tokens

Brand colours defined as CSS variables in `:root`:

```css
--navy: #0A1628
--blue: #1E6FFF
--blue-hover: #1458D4
--gold: #C9A84C
--gold-light: #E5C76B
```

Supports dark mode (default) and light mode. Theme preference saved to `localStorage`. Respects system preference if no saved preference exists.

---

## Fonts

- **Headings:** Fraunces (serif, variable — optical size 9–144)
- **Body:** Plus Jakarta Sans (sans-serif, weights 300–800)

---

## The SIGNAL Framework Section

Six animated rows (S / I / G / N / A / L) with scroll-triggered slide-in animation. Animation fires once when the section enters the viewport. Hover state on each row triggers a blue border and slight X-translate. The letter column bounces on hover.

---

## Deployment

Any push to `main` triggers an automatic GitHub Pages rebuild. Live within 2–3 minutes.

**To update the site:**

1. Edit `index.html`
2. Commit with a clear message (see commit history for conventions)
3. Push to `main`
4. Verify at distlo.in after 2–3 minutes

---

## Email

All contact routes go through Zoho Mail:

- `hello@distlo.in` — primary inbox (Formspree submissions, general contact)
- `legal@distlo.in` — alias (legal correspondence)
- `support@distlo.in` — alias (client support)

---

## Commit History Conventions

```
Add [feature] — short description
Fix [bug] — short description
Update [section] — short description
Remove [element] — short description
```

---

## Status

| Item | Status |
|------|--------|
| Site live | ✅ |
| HTTPS | ✅ |
| Formspree active | ✅ |
| Geo pricing | ✅ Live (April 2026) |
| Google Search Console | ✅ Indexed |
| Razorpay payment link | Pending activation |
| Onboarding form | Build on first client |

---

*Distlo — Turn one idea into a week of content.*  
*hello@distlo.in · distlo.in*
