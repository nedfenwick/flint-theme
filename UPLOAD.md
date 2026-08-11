# Flint theme — batch 2: the product page

Seven files. Same routine as before.

---

## Upload

In your `flint-theme` repo: **Add file → Upload files**, drag in these four
folders from the unzipped batch, commit.

```
assets/       flint-product.css
layout/       theme.liquid          (replaces batch 1's — loads the product CSS)
sections/     flint-main-product.liquid, flint-design-family-section.liquid
snippets/     flint-breadcrumb.liquid, flint-design-family.liquid
templates/    product.json
```

Then message me. I'll verify every file landed via the API before you look —
that's the step that was missing last time, and it's why two broken files sat
there silently.

---

## Then: product images

I created four sample products with full specification data, but Shopify's
connector doesn't let me upload images. Two minutes of dragging:

1. **Products → Alden Wall Light → Media**, drag in `product-alden-wall-light.webp`,
   then `card-bedroom.webp` as the second image.
2. Same for Elmore Pendant (`product-elmore-pendant.webp`, `card-kitchen.webp`),
   Marle Table Lamp (`product-marle-table-lamp.webp`, `card-bedroom.webp`),
   Hartley Picture Light (`product-hartley-picture-light.webp`, `card-hallway.webp`).

The second image is what the product card crossfades to on hover, so the order
matters. The images are in `flint-theme/assets/img/` in your working folder.

---

## What to look at

Open **Alden Wall Light** in the preview. It has four finishes, the full
specification, and all four "Good to know" answers.

- **Good to know** — the Cortex block. Four questions, always the same four,
  in plain English. This is the single biggest differentiator on the page.
- **The accordions** — every value reads from a metafield. Nothing is typed
  into the page.
- **Click through the finishes** — price, name and URL update without a reload.
- **Narrow the window** — the buy bar appears at the bottom once the gallery
  scrolls away.
- **The Alden family module** is empty because only one Alden exists. Add an
  Alden Pendant with the same Design family value and it populates itself.

---

## Known gaps, deliberately

- **Downloads accordion** says specification sheets are added as products are
  drawn. True — the generator comes in a later batch.
- **No line drawing** in the gallery yet, for the same reason.
- **Finish swatches are CSS gradients.** They must become cropped photographs
  of the real metal before launch (§25). The classes are already in place.
- **Delivery shows a despatch window, not a date.** A real date needs shipping
  configured, which is a later task.

---

## About the sample products

They are tagged `sample-data` so you can find them: search `tag:sample-data`
in Products. Every dimension, wattage and IP rating in them is **invented**.
They exist so the template can be built and judged against real structure.

Before anything goes live, every figure must be replaced with verified supplier
data. An invented IP rating on a live bathroom product is a safety and
compliance problem, not a typo.
