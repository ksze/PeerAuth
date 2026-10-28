# Product

<!-- impeccable:product-schema 1 -->

## Platform

web

## Users

Any two people — family, friends, colleagues — who want to verify each other's identity over phone or video calls. The threat they are defending against is AI deepfake impersonation (a scammer foraging a loved one's face and voice to, e.g., extract a ransom payment). Confirmed by k_sze 2026-10-28.

## Product Purpose

PeerAuth lets two people set up a shared TOTP secret entirely in the browser: each enters their name, the page generates two QR codes (one per person) plus a base32 manual-entry fallback, and each person scans theirs into a standard authenticator app. In any later phone or video call, both parties read the current 6-digit code; matching codes give the caller confidence the other person is real. Success = a non-technical pair can complete setup in one sitting and actually use the codes during a suspicious call.

## Positioning

Repurposes standards-based TOTP — the same secret/QR/app mechanism people already use for logins — as a peer-to-peer personal identity-verification channel between any pair of persons. No server, no accounts, no signup, nothing leaves the browser. A neighboring product could copy the idea but not the "it's just the TOTP already in your pocket, set up in one minute on one shared screen" mechanism.

## Operating Context

- Setup: two people sit at the same computer and open the page together.
- Verification: later, over phone or video, reading codes aloud.
- Deployed free on GitHub Pages: https://ksze.github.io/PeerAuth/ (repo: https://github.com/ksze/PeerAuth).
- Public discussion exists on Hacker News (https://news.ycombinator.com/item?id=42942854).

## Capabilities and Constraints

- Purely client-side: no server, no accounts, no data leaves the browser (binding).
- Free static hosting on GitHub Pages (binding).
- Trilingual UI — English, German, Simplified Chinese — with browser-language detection and a manual switcher (binding).
- Standard TOTP parameters: SHA1, 6 digits, 30 s period, issuer "PeerAuth", base32 manual-entry fallback; compatible with standard authenticator apps (Authy, Google Authenticator, Microsoft Authenticator, 腾讯身份验证器).
- Security boundary stated in copy: the scheme depends on both phones being secure; a stolen, unlocked phone defeats it.
- WCAG 2.1 AA accessibility target (binding, added 2026-10-28).
- Undecided product facts (do not invent answers): language preference is not persisted across visits; only one shared secret exists per generated pair; no dark mode has been decided.

## Brand Commitments

- Name: "PeerAuth"; used as the TOTP issuer string.
- Icon (chosen 2026-10-28, variant A): QR finder squares + white checkmark on a #0d6efd rounded square. Master SVG at `img/icon.svg`; simplified 16 px variant at `design-candidates/peerauth-icon-a-16.svg`; favicon PNGs at `img/favicon-32.png`, `img/favicon-16.png`, `img/apple-touch-icon.png`.
- No wordmark exists yet ("PeerAuth" is set in Bootstrap's default type).
- k_sze describes PeerAuth as a personal project (not a commercial product) and notes the app itself does not use AI.

## Evidence on Hand

- Live page: https://ksze.github.io/PeerAuth/
- Source: https://github.com/ksze/PeerAuth
- Hacker News discussion: https://news.ycombinator.com/item?id=42942854
- Threat references cited in copy: OmniHuman-1 (ByteDance paper + X discussion).
- Absences future work must not fabricate: no testimonials, no user counts, no security audit, no press coverage.

## Product Principles

- Show the mechanism, don't claim trust: QR codes and a live OTP on screen make the scheme self-evident.
- Zero-friction setup: two names and one click; the only install is an authenticator app the user likely already has.
- Honest about limits: the phone-compromise caveat is part of the product's credibility, not fine print.
- Works for everyone: plain language, three languages, WCAG 2.1 AA.

## Accessibility & Inclusion

WCAG 2.1 AA target (confirmed 2026-10-28). Trilingual EN / DE / zh-CN is a first-class requirement, not an afterthought.
