# Claude Code Handoff — RouteTick app + website

Paste this file as `CLAUDE.md` at the root of each repo (or into the first message of the Claude Code session). It is the operating brief for whoever manages RouteTick's code from here on.

## Who / what
- **Owner:** Jess Jackson (JJackson90@icloud.com; support@routetick.com for users). Reviews everything before App Store submission. Prefers module-by-module builds: build → compile → fix → next.
- **Product:** RouteTick — native iOS job ticketing + route optimization for solo contractors. Live since Sep 10, 2026. App Store id 6807180353. Pro $4.99/mo · $49.99/yr, 7-day trial, Small Business Program. Second app on the developer account (Savor is the other — don't touch it).
- **Brand:** v2, Nov 2026. Source of truth = `RouteTick Brand & Marketing/01-Brand-Guidelines/`. Signature elements: the Route Tick mark and the **tick-dot** over the i in the wordmark. Palette, type and tokens are in `brand-tokens.json` / `.css` / `Brand.swift`. Voice: blunt, contractor-first, anti-bloat, price out loud.

## Repos
| Repo | What | Deploy |
|---|---|---|
| `routetick-website` (GitHub Pages, `main`) | `index.html` single page + `privacy.html` + `terms.html` | Push to `main` = live at routetick.com |
| iOS app repo (Xcode project; SwiftUI + SwiftData, MVVM) | App source | Archive → TestFlight → App Store Connect |

## First week — in this order
1. **Website Brand v2** — follow `04-Website-Update-Plan.md` step list exactly. One PR, squash-merge. Verify favicon, OG image, dark mode, Plausible events, Smart App Banner on an iPhone.
2. **App Store Connect refresh** — new icon, screenshots, copy from `03-Marketing/copy/app-store-listing.md`, promotional text, 3 custom product pages, campaign links per placement (list in `05-Marketing-Plan.md` §5). Submit metadata-only changes first (no build needed).
3. **App 1.1** — follow `06-App-Phase-2-Roadmap.md`. Modules in order: (a) `VersionedSchema` V2 + migration, (b) `DailyRoute.orderedJobIDs` + `RouteViewModel.move`, (c) Route tab `List` reorder UI + drag handle + Edit button, (d) map/polyline rebind, (e) Optimize-overwrite confirm + Undo, (f) `Brand.swift` + icon set + paywall restyle, (g) review prompt, (h) analytics counters, (i) What's New sheet. Compile after each. TestFlight to Jess after (e) and again after (i).
4. **Release** — bump to 1.1 (build 1), What's New text from the listing doc, attach IAPs to the version (lesson from the Sep 3 rejection: subscriptions must be attached and the paywall must show title/length/price + Privacy + EULA links), submit. Post the "Drag the stops. Done." clip on release day.

## Standing rules
- Never change pricing, legal pages, or the privacy nutrition label without Jess's explicit OK.
- No third-party SDKs without listing what data they collect; update App Privacy if added.
- Keep the solo app lean — team/dispatch features go to the Teams backlog, not this app.
- Every CTA that leads to the App Store carries a campaign link / `data-event` so it can be attributed.
- Commit messages: imperative, one feature per commit. PR descriptions list what Jess should test on device.
- When blocked on an Apple-side setting (Connect, agreements, certificates), stop and tell Jess exactly which screen and which toggle — don't guess around it.

## Ongoing (weekly)
- Sunday: pull App Store Connect analytics (impressions → page views → downloads → trials → paid, by source) + Plausible + Metricool into the one-page funnel; flag the weakest step.
- Watch support@routetick.com (forwarded to the connected Gmail); reply within 24 h as Jess, log feature requests to the roadmap doc.
- Keep `06-App-Phase-2-Roadmap.md` current as the backlog; check items off, add user asks with the date and source.

## Definition of "handed over"
Website on Brand v2 · store page refreshed with attribution links · 1.1 in review · weekly funnel report running · this file in both repos.
