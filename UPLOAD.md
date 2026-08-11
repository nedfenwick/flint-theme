# Flint theme — batch 3: the collection page

Four files.

---

## Upload

`flint-theme` repo → **Add file → Upload files** → drag these four folders in
→ commit. Then tell me and I'll verify before you look.

```
assets/       flint-collection.css
layout/       theme.liquid           (replaces batch 2's)
sections/     flint-main-collection.liquid
templates/    collection.json
```

---

## Then: turn the filters on

The filters are Shopify's native storefront filtering, which needs one free
first-party app to configure. Without it the rail is empty — the page still
works, it just has nothing to filter by.

1. Install **Search & Discovery** (Shopify, free) from the App Store.
2. Open it → **Filters** → **Add filter**.
3. Add these, in this order:

   | Filter | Source | Why |
   |---|---|---|
   | Finish | Product option: Finish | How people coordinate a house |
   | Price | Price | Expected |
   | Room | Metafield: `flint.room_suitability` | Matches how renovators think |
   | Material | Metafield: `flint.materials` | Opal, ribbed, ceramic, linen |
   | IP rating | Metafield: `flint.ip_rating` | **Nobody in the mid-market offers this** |
   | Dimmable | Metafield: `flint.dimmable` | Solves a real post-purchase regret |
   | Bulb included | Metafield: `flint.bulb_included` | Removes a common surprise |
   | Width | Metafield: `flint.width_mm` | The one that matters for fitting |
   | Drop | Metafield: `flint.drop_max_mm` | Low ceilings, constantly asked |

The last four are the point. Filtering by IP rating, dimmability, width and
drop is the difference between a catalogue and something genuinely useful —
and it costs nothing but the setup, because the data is already in the
metafields.

---

## What to look at

Open **Wall Lights** in the preview. With one product in it the grid is
sparse, which is expected.

- **The intro** reads from the collection's Category introduction metafield,
  falling back to its description. Useful, not promotional.
- **The editorial break** sits after product 12 by default, so with four
  products you won't see it. Drop "Insert after N products" to 4 in the
  customiser if you want to check it renders.
- **Narrow the window** — the filter rail becomes a full-screen drawer with a
  sticky Apply button.
- **Sort defaults to the collection's own order**, not best-selling. These are
  merchandised, not automated.
- **Pagination, not infinite scroll** — 24 per page. Infinite scroll destroys
  the footer and makes an edited range feel endless.

---

## Still deliberately absent

No "quick add" on the cards. No star ratings. No sale badges. No "X left in
stock". If the grid feels quiet compared with competitors, that is the
intended difference, not an omission.
