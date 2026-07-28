# Key Master — public site

The public pages for the Key Master iOS app. This repo is deliberately separate from
the app's source repo, which is private: GitHub Pages does not serve private repos on
a free plan, and the fix for that is a separate public repo for the public pages, not
making the app source public.

Served by GitHub Pages from the `main` branch, root directory.

## What each page is for

| File | Purpose |
| --- | --- |
| `index.html` | Landing page. Doubles as the property an affiliate-network application reviews. |
| `privacy.html` | **Required by App Store Connect.** The app requests microphone access, so a reachable privacy policy URL is mandatory to submit. |
| `support.html` | **Required by App Store Connect** as the Support URL. |
| `affiliate-disclosure.html` | Not required by Apple. Present because the app links to retailers, and because a disclosure page strengthens an affiliate-network application. |

## Editing

Plain static HTML with one shared `style.css` — no build step, no dependencies, no
external requests. Edit, commit, push; Pages redeploys in about a minute.

Content changes need no App Store review. The URLs registered in App Store Connect
stay the same, so the contact email, FAQ answers and disclosure status can all be
revised at any time, including while a build is in review.

## Things to keep true

- **The privacy policy must not overstate or understate what the app does.** It is
  written to match `PrivacyInfo.xcprivacy` in the app repo, which declares no
  tracking, no tracking domains and zero collected data types. If the app ever gains
  analytics, a backend, or any data collection, this page must be updated *before*
  that version ships.
- **The affiliate disclosure states that no program is currently joined.** That is
  true while `AffiliateProgram.styles` in `GearRecommendations.swift` is empty. When a
  program is added there, update this page in the same change.
