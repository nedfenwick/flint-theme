# Self-hosting the fonts

The single biggest performance win left. Google Fonts costs a DNS lookup, a
TLS handshake and a render-blocking request before any text appears —
roughly half a second on 4G.

Fifteen minutes, and you only do it once.

---

## 1. Download four files

Go to **gwfh.mranftl.com** (Google Webfonts Helper). It serves woff2 directly,
which fonts.google.com does not.

**Newsreader**
- Charsets: `latin`, `latin-ext`
- Styles: `200, 300, 400, 500` and `italic`
- Download the woff2 files

**Inter**
- Charsets: `latin`, `latin-ext`
- Styles: `300, 400, 500, 600`
- Download the woff2 files

If it offers variable versions, take those — one file covers every weight.

## 2. Rename them

The snippet expects exactly these names:

```
newsreader-latin.woff2
newsreader-latin-italic.woff2
inter-latin.woff2
inter-latin-ext.woff2
```

## 3. Upload

Drop all four into `assets/` in your `flint-theme` repo and commit.

## 4. Switch over

In `layout/theme.liquid`, delete these four lines:

```liquid
<link rel="preconnect" href="https://fonts.googleapis.com">
<link rel="preconnect" href="https://fonts.gstatic.com" crossorigin>
<link rel="stylesheet" href="https://fonts.googleapis.com/css2?family=Newsreader...">
```

and put this in their place:

```liquid
{% render 'flint-fonts' %}
```

Tell me when it is done and I will check the payload and re-run Lighthouse.

---

## Check it worked

Open the site, DevTools → Network → filter `Font`. You should see the woff2
files coming from `cdn.shopify.com`, not `fonts.gstatic.com`, and the total
should be under 140KB.

If text flashes in Georgia before switching, that is `font-display: swap`
doing its job — it is correct, and better than invisible text.
