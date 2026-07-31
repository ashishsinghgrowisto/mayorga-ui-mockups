# Mayorga Coffee — Extracted Brand & Design System

Source: `mayorgacoffee.com` (Shopify, Dawn-derived theme `t/132`)
Extracted: 29 Jul 2026 · via computed styles, CSS custom properties and `@font-face` rules on the live storefront
Viewports audited: 1440×900 desktop · 390×844 mobile
Pages audited: Home `/` · PLP `/collections/all-coffee` · PDP `/products/cubanoroast`

---

## 1. Colour palette

### Core brand colours (theme variables)

| Token | Hex | RGB | Role |
|---|---|---|---|
| `--color-background` | `#E2D8C2` | 226,216,194 | Page background — warm cream. The dominant surface across all templates. |
| `--color-foreground` | `#6E3728` | 110,55,40 | All body copy, headings, icons, borders. Coffee brown. |
| `--color-button` / `--color-link` | `#A73439` | 167,52,57 | Primary CTA fill, links, eyebrow rules, badges, active dots. Brick red. |
| `--yellow` | `#F8B332` | 248,179,50 | Header band only. Also used as accent in packaging. |
| `--tan` | `#F1ECE9` | 241,236,233 | Drawer / overlay surfaces (menu, cart, filter, search). |
| `--color-background-contrast` | `#B9A16C` | 185,161,108 | Secondary contrast surface. |
| `--white` | `#FFFFFF` | 255,255,255 | Button text, footer text, input fills. |
| `--black` | `#121212` | 18,18,18 | PDP `h1` only; shadow base. |

### Supporting colours

| Token | Hex | Role |
|---|---|---|
| `--gray` | `#D0D0D0` | Disabled states |
| `--darkgray` | `#7D7D7D` | Muted meta text |
| Star rating | `#FFA600` | Judge.me review stars (`--jdgm-star-color`) |
| Review secondary | `#E2D8C2` | `--jdgm-secondary-color` |
| Accordion panel | `~#EDE5D6` | PDP accordion fill (cream, slightly warmer than page) |

### Applied colour combinations

- **Page:** `#E2D8C2` background + `#6E3728` text
- **Announcement bar:** `#6E3728` background + `#FFFFFF` text
- **Header:** `#F8B332` background + `#6E3728` text and icons
- **Footer:** `#6E3728` background + `#FFFFFF` text
- **Primary button:** `#A73439` fill, `#FFFFFF` text, no border visible
- **Secondary button:** transparent fill, `#A73439` 1px border, `#A73439` text
- **Variant pill (selected):** `#6E3728` fill, `#E2D8C2` text
- **Variant pill (unselected):** transparent fill, `#6E3728` 0.67px border, `#6E3728` text
- **Product badge (PDP certifications):** `rgba(167,52,57,.14)` fill, `#A73439` border + text
- **Sold-out badge:** `#A73439` fill, `#FFFFFF` text
- **Hero text over imagery:** `#E2D8C2` on a dark gradient scrim

### Focus / accessibility states

```
--focused-base-outline: .2rem solid rgba(110,55,40,.5);
--focused-base-outline-offset: .3rem;
--focused-base-box-shadow: 0 0 0 .3rem rgb(226,216,194),
                           0 0 .5rem .4rem rgba(110,55,40,.3);
```

---

## 2. Typography

### Font families

| Family | Weights loaded | Usage |
|---|---|---|
| **Londrina Solid** (Google Fonts) | 400, 900 | Display. All headings, eyebrows, variant group legends, footer headings, trust-badge titles, FAQ questions. Always **uppercase**. |
| **Nunito Sans** (Shopify-hosted) | 400, 700 (+ italics 400/700) | Body. Paragraphs, nav, buttons, product card titles, prices, accordion summaries, PDP `h1`. |
| Acumin Pro Cond Bold, Gibson Book, Gibson Semibold | — | Legacy files still loaded but not applied to current templates. |

Theme variables report both `--font-heading-family` and `--font-body-family` as `"Nunito Sans", sans-serif`; **Londrina Solid is applied via `custom.css` overrides on heading classes**, which is why the theme setting and rendered output disagree. Anyone rebuilding this should treat Londrina Solid as the real display face.

### Type scale

| Element | Desktop | Mobile | Family / weight | Transform |
|---|---|---|---|---|
| Hero `h1` (`.banner__heading.h1`) | 60px / 66px | 42px / 46.2px | Londrina 400 | uppercase |
| Section `h2` | 42px / 46.2px | 34px / 37.4px | Londrina 400 | uppercase |
| Drawer heading | 28px / 30.8px | 28px / 30.8px | Londrina 400 | uppercase |
| Variant group legend (SIZE / GRIND / QUANTITY) | 28px | 28px | Londrina **900** | uppercase |
| Hero eyebrow (`.banner__eyebrow`) | 18px | 18px | Londrina 400 | uppercase |
| PDP `h1` | 42px / 46.2px | 34px | **Nunito Sans 700**, colour `#121212` | none |
| Product card title | 20px / 22px | 20px / 22px | Nunito 700 | none |
| PDP price | 22px | 22px | Nunito 700 | none |
| Body / paragraph | 16px / 24px | 16px / 24px | Nunito 400 | none |
| Nav link | 16px | — | Nunito 400 | none |
| Button label | 15px / 18px | 15px / 18px | Nunito 600 | uppercase |
| Accordion summary | 16px | 16px | Nunito 700 | uppercase |
| Roast tag (`DARK ROAST`) | 14px | 14px | Nunito **800** | uppercase |
| Trust-badge title | 12px | 12px | Londrina 400 | uppercase |
| Caption / meta | 12px | 12px | Nunito 400 | none |
| Badge (Sold out) | 12px | 12px | Nunito 400 | none |

### Letter-spacing — the signature detail

Almost everything carries **`letter-spacing: 0.6px`**, inherited from `body`. Exceptions:

- Buttons, badges, trust-badge titles, variant pills: **`1px`**
- Variant legends: **`0.4px`**
- Product badges: **`0.6px`**

Line height: `1.1` multiplier on all Londrina headings; `1.5` (24px on 16px) on body.
`--font-heading-scale` and `--font-body-scale` are both `1.0` — no global type scaling applied.

---

## 3. Spacing, grid & layout

| Token | Value |
|---|---|
| `--page-width` | `120rem` → **1200px** max content width |
| Page gutter (desktop) | 40px |
| Page gutter (mobile) | 30px |
| Grid gap — desktop | 32px (`--grid-desktop-horizontal-spacing` / `vertical`) |
| Grid gap — mobile | 16px (`--grid-mobile-horizontal-spacing` / `vertical`) |
| Section padding — desktop | 64px top/bottom (48px on tighter sections) |
| Section padding — mobile | 48px top/bottom (24px on tighter sections) |
| `--header-height` | 94px |

### Header

| | Desktop | Mobile |
|---|---|---|
| Height | 94px | 56px |
| Padding | `12px 40px` | `6px 30px` |
| Grid | `147.5px | 1fr | auto` → `"heading navigation icons"` | `32px | 1fr | 144px` → `"left-icons heading icons"` |
| Column gap | 20px | 8px |
| Logo | 140 × 55px, left-aligned | 73 × 29px, centre-aligned |
| Icon hit area | 44 × 44px | 44 × 44px |
| Behaviour | `sticky-header` — announcement bar scrolls away, yellow band pins to top | same |

Announcement bar: `#6E3728`, ~46px desktop / ~38px mobile, centred single line.
Header icon order (right): Search → Account → Wishlist (Swym) → Cart. On mobile, Account and Wishlist are dropped from the visible row.

### Product grid

| | Desktop | Mobile |
|---|---|---|
| Columns | 4 | 2 |
| Gap | 32px | 16px |
| Card width @1200px | ~273–277px | ~228px |
| Card height | ~464–476px | ~417px |
| Media ratio | 1:1 (`--ratio-percent: 100%`) | 1:1 |
| Text alignment | centre (`--product-card-text-alignment: center`) | centre |
| Card radius / border / shadow | 0 / 0 / none | same |

Carousels (Best Sellers, See What's Brewing, Our Specialty Coffee, related products) are flex sliders showing 4 desktop / 2 mobile with prev/next caret buttons flanking a dot counter, plus a `1 / of N` label.

### PDP layout

| | Desktop | Mobile |
|---|---|---|
| Split | Media 55% / Info 45% (`max-width: 45%`) | stacked |
| Info padding | `0 0 0 50px` | 0 |
| Media items | 10 (stacked column, 32px gap) | swipe gallery |
| Sticky ATC bar | yes — thumb, title, variant, price, ADD TO CART + BUY NOW | yes |

---

## 4. Components

### Buttons

```
height:            47px
padding:           0 30px
border-radius:     23px          /* full pill — note: --buttons-radius is 6px and is overridden */
font:              600 15px/18px Nunito Sans
letter-spacing:    1px
text-transform:    uppercase
border-width:      1px
box-shadow:        none (--buttons-shadow-opacity: 0.0)
```

- **Primary:** `#A73439` fill / white label
- **Secondary:** transparent fill / `#A73439` border + label
- On product cards the button stretches to the card width (max ~262px)
- Sold-out state renders as a disabled `NOTIFY ME` button

### Inputs

```
--inputs-radius:         6px
--inputs-border-width:   1px
--inputs-border-opacity: 0.55
--inputs-shadow-opacity: 0.0
```
Quantity stepper: 140 × 44px, `border-radius: 8px`, `0.67px solid rgba(110,55,40,.22)`, minus / input / plus.
Newsletter input: 52px tall, 6px radius, 1px white border on the brown footer, inline arrow submit.

### Badges & pills

| Component | Spec |
|---|---|
| Sold-out badge | `#A73439` fill, white text, 12px, `1px` tracking, padding `5px 13px 6px`, radius `40px` |
| PDP certification badge | 11px **900** Nunito, `0.6px` tracking, padding `4px 11px`, radius `20px`, `rgba(167,52,57,.14)` fill, `0.67px solid #A73439` |
| Variant pill | padding `10px 20px`, radius `6px`, 14px / `1px` tracking, `0.67px` border; selected = brown fill + cream text |
| `--badge-corner-radius` | `4.0rem` (40px) |

### Eyebrow + rule pattern

Repeated across hero slides and the PLP collection header:

```
<p class="eyebrow">SUMMER STARTS HERE</p>   ← Londrina 18px uppercase
<hr>                                        ← 80 × 2px, #A73439, margin 0
<h2 class="h1">BRIGHT MORNINGS, ICED AFTERNOONS</h2>
```

### PDP roast scale

Four coffee-bean SVGs (31 × 41px) labelled LIGHT / MEDIUM / DARK / EXTRA DARK. Bean fills lighten-to-darken; the active bean carries a `1px` brown box outline and full-opacity label (inactive labels sit at ~55% opacity). Selected value repeats below as plain text (`Dark Roast`). Display-only — not an interactive filter.

### PDP trust badge row

Four centred icon + title + subtitle cells above the fold-out, separated from the buy block by a hairline rule:

| Icon | Title (Londrina 12px) | Subtitle (12px) |
|---|---|---|
| Leaf | 100% ARABICA | Shade Grown |
| House | FAMILY OWNED | Since 1997 |
| Shield | TESTED | Mold & Mycotoxins |
| Truck | FREE SHIPPING | on orders $45+ |

### Free-shipping progress bar

`rgba(255,255,255,.5)` fill, `8px` radius, `10px 12px` padding, 16px copy: *"You're $45.00 away from FREE shipping 🚚"*. Appears both on the PDP (between the plan selector and the buy row) and in the cart drawer. Threshold: **$45**.

### Drawers & overlays

```
width:            300–400px (--swym-storefront-layout-side-drawer-width: 300px)
background:       #F1ECE9
border-width:     1px @ 0.1 opacity
shadow:           none (--drawer-shadow-opacity: 0.0)
transition:       .3s cubic-bezier(0,0,.3,1)
```
Menu drawer slides from the left with nested disclosure submenus; cart drawer slides from the right; filter drawer (PLP) slides from the left with `<details>` facet groups.

### Motion tokens

```
--duration-short: .1s   --duration-default: .2s   --duration-medium: .3s
--duration-long: .5s    --duration-extra-long: .6s  --duration-extended: 3s
--ease-out-slow: cubic-bezier(0, 0, .3, 1)
--animation-fade-in:  fadeIn .6s cubic-bezier(0,0,.3,1)
--animation-slide-in: slideIn .6s cubic-bezier(0,0,.3,1) forwards
```
Sections use `scroll-trigger animate--slide-in` / `animate--fade-in` on entry. Product card media has a `media--hover-effect` scale transform.

---

## 5. Imagery

- **Product shots:** every bag photographed dead-centre on a cream/kraft paper texture backdrop, 1:1, transparent-feel edges (`media--transparent`). Consistent enough that the grid reads as a single system.
- **Lifestyle / hero:** warm, sun-lit, saturated Latin American settings — terracotta, textiles, straw, farm and origin portraiture. Real farmers and family, not stock studio.
- **Video:** UGC-style vertical social clips in "See What's Brewing" (Shopify-hosted MP4 + poster frame), plus a YouTube brand film in "Coffee with Purpose".
- **Decorative:** a repeating woven-textile `pattern.png` strip (~25px desktop / 28px mobile, 1.94% aspect) used as a full-bleed divider between sections.
- **Founder signature PNG** closes the "Coffee with Purpose" block.
- Delivery: Shopify CDN with `format=webp&quality=75`, `srcset` at 165 / 360 / 533 / 720 / 940 / 1066w, `loading="lazy"` below the fold.

---

## 6. Voice & content patterns

- **Bilingual pride.** Spanish is woven in unglossed and un-italicised: *Orgullo Latino*, *Familia Mayorga*, *Buenos Días*, *Muy Macho*, *con orgullo*, *¡Con Orgullo Latino!*
- **Proof over adjectives.** Claims are specific and checkable: 100% organic, specialty grade, direct trade, tested for mold and mycotoxins, family owned since 1997, no middlemen.
- **Farmer-first framing.** Benefit statements lead with the grower, not the drinker.
- **Headline construction:** short, declarative, uppercase, often a two-part rhythm — *"Bright Mornings, Iced Afternoons"*, *"Rooted in Latin America"*, *"Coffee with Purpose"*, *"Organic Coffee That Supports Real People"*.
- **Eyebrow → rule → headline → one-line support → single CTA.** Used on nearly every promotional block.
- **CTAs** are short, uppercase, action-first: SHOP SUMMER COFFEE · VIEW COLLECTION · SUBSCRIBE & SAVE 10% · LEARN OUR STORY · ADD TO CART.
- **Product naming** blends origin and culture: place-based single origins (Perú Amazonas, Guatemala La Hermosa, Nicaragua 25 de Marzo) alongside culturally named blends (Cubano Roast, Muy Macho, Mayan Blend, Artesano Blend, Dulce de Leche).
- Roast level is treated as the primary product attribute — it sits on every card, under every title, and drives the main PLP filter.

---

## 7. Information architecture

**Primary nav:** Shop (mega: Coffee / Coffee by Roast / Coffee by Country / Chia Seeds & Beans / Coffee Trio's & Gifts) · Subscriptions · Orgullo Latino Blog · About (mega: Our Story / Guides / Help)

**Home section order:** Hero slideshow (3) → Rich text mission → Best Sellers carousel → Recently viewed → See What's Brewing (UGC video carousel) → pattern divider → Build Your Coffee Subscription → Gifts for Coffee Lovers → Coffee with Purpose (video + signature) → Our Specialty Coffee carousel

**PLP section order:** Breadcrumb → eyebrow + H1 + intro copy → filter/sort toolbar (Filter button, product count, Sort by select) → 4-up grid → pagination → pattern divider → subscription block → FAQ accordion ("Questions", 9 items) → Authentic Latin Heritage rich text

**PDP section order:** Breadcrumb → certification badges → H1 → price → shipping note → rating → roast tag → accordions (Description / Origins / Tasting Profile) → roast scale → Size → Grind → subscription widget → Quantity → free-shipping bar → ADD TO CART + BUY NOW → store pickup → trust badges → pattern divider → Try Our Best Sellers → subscription block → reviews → Authentic Latin Heritage

**Footer:** brand + Contact Us · Browse (6 links) · Info (6 policy links) · newsletter · 4 social icons · 7 payment marks · copyright. Menu columns collapse into `<details>` accordions on mobile.

**Sort options:** Featured · Most relevant · Best selling · Alphabetically A-Z / Z-A · Price low→high / high→low · Date old→new / new→old

---

## 8. Ready-to-use CSS token block

```css
:root{
  /* colour */
  --cream:#E2D8C2;  --brown:#6E3728;  --red:#A73439;
  --yellow:#F8B332;  --tan:#F1ECE9;   --contrast:#B9A16C;
  --star:#FFA600;    --white:#FFFFFF; --black:#121212;
  --gray:#D0D0D0;    --darkgray:#7D7D7D;

  /* type */
  --font-display:"Londrina Solid",sans-serif;
  --font-body:"Nunito Sans",sans-serif;
  --ls-base:.6px;  --ls-ui:1px;

  /* geometry */
  --page-max:1200px;
  --gutter-d:40px;  --gutter-m:30px;
  --gap-d:32px;     --gap-m:16px;
  --btn-radius:23px; --btn-h:47px;
  --radius:6px;      --radius-lg:8px;  --radius-pill:40px;
  --hdr-h-d:94px;    --hdr-h-m:56px;
  --free-ship-threshold:45;

  /* motion */
  --ease:cubic-bezier(0,0,.3,1);
  --d-fast:.2s; --d-med:.3s; --d-slow:.6s;
}
```

---

## 9. Notes for whoever rebuilds this

1. **Theme variables lie about the heading font.** `--font-heading-family` reports Nunito Sans; Londrina Solid is layered on via `custom.css`. Build from rendered output, not settings.
2. **Button radius is also overridden.** `--buttons-radius: 6px` is the theme value; the rendered pill is `23px`. Same story for `--product-card-corner-radius: 0` (which *is* accurate).
3. **`0.6px` letter-spacing is inherited from `body`** and is doing a lot of the brand's visual work. Drop it and the site stops looking like itself.
4. Two heading weights matter: Londrina **400** for section headings, Londrina **900** for PDP variant legends. Using one for both is the most common way to get this wrong.
5. The PDP `h1` deliberately breaks the display-font rule — it is Nunito Sans 700 in near-black `#121212`, not brown Londrina.
6. Third-party apps in the stack contribute their own tokens and should be treated as out of scope for the brand system: Judge.me (reviews), Swym (wishlist), Recharge (subscriptions), Klaviyo (email capture), Instafeed, HubSpot, Restock Rocket.
