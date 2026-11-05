# Handoff: BaT Local Partner page (Interstate Motorsport)

AAN ticket 49401 · Draft prepared 2026-11-05 · Status: **waiting for client approval**

Draft: `bat-landing/index.html`. It is one self-contained page with the header and footer rebuilt from the live site. Assets are in `bat-landing/assets/`.

---

## ⚠ Site-wide changes (header and footer)

The header and footer in the draft are **not page-local**. They are the live site's header and footer, tidied. If the client approves them, they change on **every page** of interstatemotorsport.com: they live in the `aanWordpress` theme's `header.php` / `footer.php`.

If the client approves only the BaT page, keep the current header and footer site-wide and port only the page body. The only header change you still need is the new menu item (point 1 below).

### Header changes
1. **New menu item:** Services → **Bring a Trailer** (first in the dropdown). Add it in WP Menus (`header-menu`).
2. Utility row: dropped the typed `|` separators. Each item now has its own icon and spacing. "My Collection | 00" became "My Collection" (the counter can stay if the theme fills it).
3. Nav type: 15px uppercase, letter-spacing .05em, `white-space: nowrap`. Fixes "Service Department" and "About Us" breaking onto two lines at wide widths.
4. Hover and active states: a green underline that grows from the left. The active section is green.
5. Dropdowns open on hover **and** on click/keyboard (`aria-expanded`, Esc closes).
6. Scroll state: transparent over the hero, solid `#141414` with a hairline once scrolled. The utility row collapses. This matches the existing `shrink addbg` behaviour.
7. Mobile (<1200px, same as the theme's `xl` breakpoint): logo, call button, menu button. The full-screen menu has accordion submenus and 44px touch targets.

### Footer changes
1. **Live map:** replaces the static `map.jpg`. It is a Google Maps embed (no API key) of "Interstate Motorsport, 109 Titus Mill Rd". Dark styling comes from a CSS filter on the iframe:
   `filter: invert(.9) hue-rotate(180deg) saturate(.55) contrast(.9)`.
   Embed URL: `https://maps.google.com/maps?q=Interstate%20Motorsport%2C%20109%20Titus%20Mill%20Rd%2C%20Pennington%2C%20NJ%2008534&z=13&output=embed`
2. Columns: Visit (address + Get directions), Call, Follow (IG / FB / YT), Buy (Inventory, Sold Inventory, Financing), Sell & store (Bring a Trailer, Consignment, Storage).
3. **Removed `footer-bg.png`** (two cut-out car renders under the copyright). They were low-resolution cut-outs with no ground under them, and they ended the page on decoration. To restore: re-add the image after the copyright bar. A comment in the draft marks the spot.
4. **Footer contact form (`insertForm('footer-contact', 'contacts_vdp')`):** left out of the draft footer, because the BaT page has its own form and two forms on one page compete. **Decision needed:** keep it site-wide and hide it only on the BaT page template, or drop it everywhere. Recommended: keep it on other pages and hide it on BaT.
5. Copyright bar: © · Sitemap · Privacy Policy · Powered by All Auto Network. Same content, aligned on one line.

### Bug found on the live site (fix regardless)
`/wp-content/themes/aanWordpress/assets/fonts/ProximaNova-Regular.woff2` returns a **404 HTML page**. Browsers reject it with "OTS parsing error" and fall back to the `.woff`. Either upload the real woff2 file or remove the woff2 line from the `@font-face` rule. The draft uses the `.woff`.

---

## The BaT page itself

**Suggested URL:** `/bring-a-trailer/`
**Suggested title:** `Bring a Trailer Local Partner in New Jersey | Interstate Motorsport`
**Meta description:** in the draft `<head>`.

### Sections
The page reuses two ideas already on the homepage: photos in a white "print" frame with a round sticker on the corner, and the darkened-photo section background.
1. **Hero:** darkened showroom background. H1 "Sell your car on / Bring a Trailer" on the left. On the right, a framed print of the doors-up showroom row. The BaT Local Partner badge (black version, on a round off-white sticker) sits on the print's corner. Two CTAs ("Submit Your Vehicle" anchors to the form; Call).
2. **Process, "Our BaT process / from keys to sold":** six framed prints in a 3-column layout that steps down. Each has a large green numeral, a title and one line of copy. No JS, no animation.
3. **Why sell with Interstate:** darkened-photo band with four large facts (2003 · 10,000+ · 26,000 sq ft · NJ licensed dealer) and the BaT profile link.
4. **Submit your vehicle (form):** two steps, in the pattern of the homepage "Get my offer" widget (counter "01 / 02", "Continue to final step"). See below.
5. **Program note:** BaT badge, independence line, link to `bringatrailer.com/local-partners/`.

### Form → AAN form system
Step 1, the car: year*, make*, model*, mileage, location*, description. Step 2, you: first name*, last name*, email*, phone*, photos (multiple file upload). Field set taken from the OTTO Car Club and KarPark reference forms. The two-step pattern matches the site's own "Get my offer" form, and Enthusiast Spec's /submit is also multi-step.
- Check whether the AAN form handler supports **file uploads**. If it does not, drop the photos field and change the helper text to "send photos to [email]".
- Recipient: Interstate's sales inbox (confirm address).
- The draft's front-end validation, error summary and success state can stay. Replace the draft success text ("not connected yet") with the real confirmation.

### Assets
- Photos: `assets/img/*.jpg` (all from Interstate's own Facebook). Upload to `/wp-content/uploads/bat/`.
- BaT logos: `assets/img/BaTLocalPartnerLogo2025white.png` / `black.png`. Use them unmodified.
- Fonts: the theme already loads Staatliches and Proxima Nova, so nothing new is needed.
- Tokens used: `#141414` ground, `#90c43d` accent (same as the theme), `#1b1b1b` raised surface, `#0e0e0e` sunk band.

### Before go-live: pending from the client
1. Confirm the six steps: what is included in the BaT package and what is extra (storage, detail, photography, transport).
2. **BaT member profile URL** for "See our auctions on Bring a Trailer". It is currently a placeholder with a yellow "Link pending" tag.
3. Form recipient email, and whether file upload is possible.

See `CONTENT-LEDGER.md` for every claim, its source and its status.
