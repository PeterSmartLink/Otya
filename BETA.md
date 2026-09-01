# Otya beta

Otya beta is a controlled validation stage for the first public release. It is not a promise that every planned idea is complete.

## Purpose

The beta exists to prove that Otya's current core experience is reliable on real Android devices and that its public account, support, legal, update and communication surfaces are ready for real users.

## Included in beta

The beta should validate the existing product only:

- local music and video discovery and playback;
- background playback, media controls and Now Playing behavior;
- Library, playlists, history and files;
- Transfer on supported local-network scenarios;
- Private lock and restore behavior;
- Otya account sign-in, registration, recovery and security flows;
- Google sign-in where enabled;
- Next request/streaming behavior and graceful failure when online services are unavailable;
- Online Music behavior that is already supported;
- notifications and deep-link/open behavior;
- update checking and architecture-correct downloads;
- Help, Privacy, Terms, account deletion and support links;
- accessibility, permissions and common lifecycle states such as cold start, background/foreground, calls and Picture-in-Picture where applicable.

## Not beta scope

Do not delay the beta for future concepts that are not required for the current product contract. Examples include new platform expansion, new media ecosystems, new social features, new AI capabilities, new developer APIs or other feature expansion that has not already been accepted into the v1 contract.

## Evidence levels

A change is not considered complete just because code exists.

1. **Coded** — source change exists.
2. **CI validated** — automated tests/analyzer/build checks pass.
3. **Built** — the intended Android artifact exists and its signing/integrity checks pass.
4. **Device accepted** — the behavior is reproduced and accepted on real target hardware.
5. **Released** — the approved artifact and public documentation are actually published.

Public claims must match the highest evidence level reached.

## Beta entry gate

Before inviting external beta testers:

- current reliability PRs are reviewed and integrated safely;
- signed beta artifact is reproducible;
- account/auth recovery works end to end;
- Privacy and Terms match the real service/data behavior;
- external account-deletion path exists where required;
- public Help, Privacy, Terms and download links resolve correctly;
- crash/startup regressions are not present on target devices;
- core local playback remains usable when online services are unavailable.

## Beta exit gate

Production should wait until:

- blocker and data-loss defects are resolved;
- authentication, updates, Next, Transfer, Private, notifications and playback pass agreed device acceptance;
- release signing and architecture selection are verified;
- Play listing/data disclosures match the product;
- support and incident communication paths are ready;
- there is a rollback/recovery path for a bad release;
- known limitations are documented rather than hidden.

## Reporting beta problems

A useful beta report includes:

- Otya version and build number;
- device model and Android version;
- what the tester was trying to do;
- exact steps that reproduce the problem;
- expected behavior;
- actual behavior;
- screenshot/screen recording or sanitized logs when useful.

Do not include passwords, OTPs, access tokens, signing information, private media or other sensitive data in public reports.

## Communication

During beta, public wording should say **Otya beta**, **testing**, **validation**, **available to testers**, or similar factual language. Do not call a beta build production-ready or generally available until the production acceptance gate has actually passed.
