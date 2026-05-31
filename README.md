# 🍺 Beer Tasting Scorecard

**AppADay #023 — 2026-05-30 — Category: G**

Rate beers one at a time on four attributes with large tap-friendly sliders. Built for group tastings on the go — bus tours, tap rooms, homebrew club events.

## What It Does

Enter beers by brewery and beer name, then score each one on Appearance, Aroma, Taste, and Finish (1–10). Add optional tasting notes per beer. At the end of a session, see a ranked podium with medal standings. All sessions are saved to a persistent log with full rankings viewable any time.

Optionally enter a Claude API key in Settings to get an AI-generated style brief — ABV range, flavor profile, and sensory notes — for any beer before or while you score it.

## How to Use

1. Tap ⚙️ to set your Session Name and (optionally) your Claude API key — both persist in localStorage
2. On the home screen, enter a Brewery and Beer Name and tap ＋ to queue it up — repeat for each beer
3. Tap **Begin Tasting** to start scoring one beer at a time
4. On each scoring card, optionally tap **Look up this beer with Claude** for a style brief
5. Adjust the four sliders and add tasting notes, then tap **Next Beer** or **See Results**
6. Use **✕ Cancel This Beer** on any card to remove that beer and return to the queue
7. At results, tap **Copy Link** to share the beer list with others on the same session
8. Tap **📋 Log** any time to review past sessions and full rankings

## Technical Notes

- Single-file vanilla HTML/CSS/JS — no build steps, no dependencies beyond Google Fonts
- Claude API called directly from the browser using `anthropic-dangerous-direct-browser-access: true` header
- API key stored in `localStorage` under `beertasting_settings_v1` — never committed, never in source
- Session log stored in `localStorage` under `beertasting_log_v1`, capped at 50 sessions
- Cross-device beer list sharing via base64-encoded URL query param (`?session=...`)
- Fonts: Playfair Display + DM Sans via Google Fonts CDN

## Definition of Complete

- [x] Functional — scores beers, saves sessions, renders rankings without errors
- [x] Single purpose — one job: score beers during a tasting session
- [x] Mobile friendly — oversized tap targets, single-column layout, 375px viewport tested
- [x] Visually polished — dark malt/amber craft aesthetic, intentional typography and spacing
- [x] Published — live GitHub Pages URL, numbered and named
