# Interstate Motorsport — BaT Local Partner landing page

Client: Interstate Motorsport, 109 Titus Mill Rd, Pennington NJ 08534 (AAN ticket 49401).
Site: interstatemotorsport.com, WordPress theme `aanWordpress` (All Auto Network, Bootstrap 4, jQuery).
Deliverable: a draft landing page for client approval before it goes live, then a port into the AAN theme.

## Brand carriers (client's, keep)
- Logo `brand-logo.svg` (white wordmark + car silhouette)
- Display: Staatliches (two-line headings: white line + green line). Text: Proxima Nova Regular (no bold cut on the site)
- Ground #141414, accent green #90c43d, green buttons with dark text
- Photography: their own gallery (wood floor, concrete wall), outdoor sets in front of the dark building with bull statues

## Files
- `bat-landing/index.html` — variant 1: process as a horizontal scroll reel (header + footer rebuilt from the live site, tidied)
- `bat-landing/index_v2.html` — variant 2: same page, process as vertical alternating photo reveals
- `bat-landing/assets/` — fonts, logos, processed photos
- `bat-landing/assets/source/fb/` — the 20 full-size Facebook picks the crops are made from (git-ignored)
- `bat-landing/HANDOFF.md` — notes for the AAN developer, including site-wide header/footer changes
- `bat-landing/CONTENT-LEDGER.md` — every claim and its source

## Feedback log
- 2026-11-05 · Header and footer come from the existing site; footer may be tidied, the map made live, header tidied lightly. Any header/footer change is site-wide and must be stated as such in the handoff.
- 2026-11-05 · Copy and type follow the current site so the page does not stand out: two-line Staatliches headings (white line + green line), plain direct copy reusing their own phrases, Proxima Nova buttons in Title Case. Small variations are welcome, a new voice is not.
- 2026-11-05 · Draft v1 scored 3/10, hero text composition 1/10. Banned: dash/line before eyebrow labels, radio-button circles in progress lists. Hero text must not float over the photo's subject. It needs a decided edge and no eyebrow that repeats the BaT badge.
- 2026-11-05 · v2 (framed prints, stepped grid, sticker) scored 2/10. Alex: the references all open with a BIG hero and are clean sites. Approved direction (v3): full-bleed darkened showroom hero, centered badge + two-line title + CTA; plain 3×2 process grid; one light section for rhythm (paper #f4f3ef, darker green #5b8a1e for accent on light); entrance slide-in motion; subtle blurred irregular green glows on the dark background.
- 2026-11-05 · CLIENT CHOSE LAYOUT #2 (vertical). Working file now `index_v2_2.html`: top CTA "Contact Us"; services menu ("How can we help you sell?") with the client's five services + Consignment; selecting one preselects it in a 3-step form (services → car → you), modelled on enthusiastspec.com/submit. Client wants to edit text/photos himself later: solve at the WordPress port, not in the draft.
- 2026-11-05 · Git: repo github.com/Sigovs/Interstate-Motorsport (public). Licensed Proxima Nova, raw FB downloads and the ticket PDF stay git-ignored.
- 2026-11-05 · Use the client's Facebook photos (facebook.com/INTERSTATEMOTORSPORT/photos); download only the picks actually used, not the whole album.
