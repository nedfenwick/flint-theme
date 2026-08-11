# Flint theme — batch 5: audit fixes

Seven files. Three real fixes, four for repo parity.

---

## Upload

`flint-theme` repo → **Add file → Upload files** → drag the folders → commit.

```
layout/       theme.liquid                      (parity — already live)
sections/     flint-main-product.liquid         *** VAT fix
              flint-main-collection.liquid      *** accessibility fix
              flint-main-page-contact.liquid    *** usability fix
snippets/     flint-fonts.liquid                (new — do not use yet, see FONTS.md)
              flint-schema.liquid               (parity — already live)
templates/    page.contact.json                 (parity — already live)
```

The four parity files are already live on the store; they are here so your
GitHub repo stops drifting from what is actually running.

---

## The three fixes

**1. "Including VAT" removed from the product page.** You are not VAT
registered, so claiming it was a misrepresentation. It is now a checkbox in
the Product page section settings, off by default. Switch it on the day
registration comes through — nothing else needs to change.

**2. Price-range filter inputs had no accessible label.** They had visible
placeholders, which sighted users read fine and screen readers ignore. Both
now carry an `aria-label`.

**3. The contact form's topic select had no dropdown arrow.** I had set
`appearance: none` to strip the browser default and never replaced it, so it
looked like a text field. It now has a Knap chevron.

---

## Audit results

Everything else passed:

| Check | Result |
|---|---|
| Images have alt text | pass |
| Buttons have accessible names | pass |
| Focus styles present | pass |
| Reduced motion honoured | pass |
| Heading hierarchy, no level skips | pass |
| Colour contrast, all pairings | pass (verified numerically) |
| CSS split per template | pass — 42KB across 6 files |

**Deliberately not done:** a `<link rel="preload">` for the hero image. It sits
in the initial HTML with `fetchpriority="high"`, which the browser's preload
scanner picks up immediately. Adding a preload would mean hard-coding an image
path in the layout that goes stale the moment you change the hero. The real
LCP win is the fonts.

---

## Next: the fonts

See **FONTS.md**. Fifteen minutes, done once, worth about half a second.
