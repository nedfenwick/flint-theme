# Flint theme — batch 4: everything that was left

Thirteen files. This completes the storefront: cart, search, content pages,
the Journal, and 404.

---

## Upload

`flint-theme` repo → **Add file → Upload files** → drag these four folders in
→ commit. Then tell me and I'll verify.

```
assets/       flint-pages.css
layout/       theme.liquid                (replaces batch 3's)
sections/     flint-main-cart.liquid, flint-main-search.liquid,
              flint-main-page.liquid, flint-main-blog.liquid,
              flint-main-article.liquid, flint-404.liquid
templates/    cart.json, search.json, page.json,
              blog.json, article.json, 404.json
```

The header and the /collections page are already live — I pushed those
directly when I fixed the navigation, so they aren't in this batch.

---

## Already done in your store

I created all of this while building, so the links resolve the moment you
upload:

**Pages** — About, Trade, Finish samples, Delivery, Returns, Guarantee,
Installation, Contact. All written, all in Flint voice, all published.

**Journal** — the blog, plus the first three guides:
How high should wall lights be? · Lighting a kitchen island ·
Bathroom IP ratings, explained plainly.

**Menus** — Footer Trade and Footer Journal, so those two columns fill in.

---

## Two minutes in the customiser

Three things I can't set from here, because they live in the theme's own
settings rather than in your store's data:

1. **Header → utility links.** Set the three URLs:
   Trade → `/pages/trade` · Finish samples → `/pages/finish-samples` ·
   About → `/pages/about`
2. **Footer → Trade column → Menu** → choose *Footer Trade*.
   **Footer → Journal column → Menu** → choose *Footer Journal*.
3. **Product grid** on the homepage → choose *New this season*.

---

## What to look at

- **The Journal.** `/blogs/journal` — three real guides. Open "How high should
  wall lights be?" and note the standfirst answers the question in two
  sentences, and the "In short" box near the top. That box is what gets
  screenshotted and shared.
- **The cart.** Add something. No upsells, no free-delivery progress bar, no
  urgency. Its job is to get out of the way.
- **Delivery and Returns.** Written to be read, not to be defensible. "If it is
  not right, send it back within 30 days and we will refund it in full."
- **404.** Try any nonsense URL. Quiet and useful — a wrong turn isn't an
  occasion for a joke.

---

## After this batch

Dawn's CSS now only loads on customer account pages and the password page.
Everything else is Flint. The remaining Phase 1 work is not templates:

- Commerce setup — payments, shipping, VAT, notification emails
- SEO and analytics — structured data, GA4, Search Console, Merchant Center
- Performance and accessibility audit — including self-hosting the fonts
- Replacing every placeholder image with real photography
- Replacing the invented sample specification data with verified supplier data
