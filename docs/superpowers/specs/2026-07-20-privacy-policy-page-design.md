# Privacy Policy Page — Design

## Context

anti-clockwise-web is a static site (plain HTML/JS, no build step, deployed on Cloudflare Pages) for Anti-Clockwise, LLC. It has two products, **Knower of Things** (companion app for *Things in Rings*) and **ES:BOTSE Companion** (campaign keeper), both free on iOS and Android. Neither app requires accounts or syncs data to a server — game/campaign state is stored locally on-device. Both apps use Google Firebase (Crashlytics + Analytics) for stability/usage data and Google AdMob for ads. Neither app is directed at children under 13.

No privacy policy currently exists anywhere in the repo. App store listings (Apple App Store Connect, Google Play Console) require a reachable privacy policy URL, and this page will serve that purpose in addition to covering the website itself.

## Scope

One combined privacy policy page covering:
- The website (anti-clockwise.com)
- Knower of Things
- ES:BOTSE Companion

Not in scope: separate per-app policies, a Terms of Service page, cookie-consent banners (no cookies are used — this is a static site with no site-side tracking).

## File & Structure

- New file: `Privacy.dc.html`, sibling to `About.dc.html`, `Consulting.dc.html`, `Contact.dc.html`, `Products.dc.html`.
- Follows the same `.dc.html` shape as existing pages: `<script src="./support.js">`, `<x-dc>` wrapper, `<helmet>` with the same font links and base `<style>`, same nav markup, same footer markup.
- No changes to `support.js` or the `dc-runtime` build are needed — this page uses only static markup plus the shared nav/footer/font/color conventions already used elsewhere, not a new dynamic `Component`/props block.

## Navigation

- **Not** added to the primary top nav (Products / Consulting / About / Contact stays as-is).
- Added as a "Privacy" link in the footer link row on **all five pages** (the four existing pages plus the new `Privacy.dc.html`), consistent with the convention of legal pages living in the footer rather than primary nav.

## Visual style

Reuses the site's existing palette and type (`Bricolage Grotesque` for headings, `Public Sans` for body, `#2b2118`/`#5c4d3d`/`#a08a6e` text tones, `#f7f1e6` background, `#d9542b` accent, `#fffdf8` card background). Because this page is long-form text rather than a marketing layout, content is presented as stacked heading/paragraph blocks inside a single centered content column (not the card/grid layouts used on Home/Products), matching the max-width and padding conventions of the other inner pages (e.g. Contact's `max-width:1200px` container, `56px` horizontal padding).

## Content outline

1. **Title + effective date** — "Privacy Policy", effective July 20, 2026.
2. **Intro** — who "we" are, what this policy covers (site + both apps).
3. **Information we collect**
   - Nothing required to use the apps — no account/sign-in.
   - Automatically collected: device/diagnostic and crash data via **Firebase Crashlytics**; usage/analytics events via **Firebase Analytics**.
   - Advertising: device advertising identifiers via **Google AdMob**, used for ad delivery, frequency capping, and measurement.
   - Locally stored, never transmitted to us: game/campaign data (card history, XP tracking, campaign saves) — lives on-device only, cleared on uninstall.
   - Info you send us directly: if you email `hello@anti-clockwise.com` or use the Contact page, we receive whatever you send.
4. **How we use information** — app stability/bug fixing, understanding feature usage, ad delivery/measurement, responding to inquiries.
5. **Third-party services** — names Google Firebase and Google AdMob explicitly, links to Google's privacy policy for further detail on what those SDKs collect.
6. **Sharing & sale of data** — we don't sell personal data; data is shared only with the service providers named above (Google) as needed to operate crash reporting/analytics/ads.
7. **Your choices** — device-level ad tracking controls (iOS App Tracking Transparency, Android ad personalization opt-out), uninstalling the app removes locally stored game data.
8. **Children's privacy** — general-audience apps, not directed at children under 13, no knowing collection of children's data.
9. **Data retention** — locally stored game data persists until the user clears it or uninstalls; analytics/crash data retained per Firebase's standard retention windows.
10. **Security** — reasonable safeguards used; no method of transmission/storage is 100% secure.
11. **Changes to this policy** — we'll update the effective date and post changes here.
12. **Contact** — `hello@anti-clockwise.com`.

## Out of scope / explicit non-goals

- No cookie banner or consent-management tooling (no cookies used by the static site itself).
- No GDPR-specific data-subject-request tooling — handled via the existing contact email, mentioned in the "Your choices" section.
- No changes to `dc-runtime` source or `support.js`.
