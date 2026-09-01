# Otya

Otya is a media-first product by PeterSmart Link. This repository is the public hub for information and automation that is safe to expose publicly.

## Public surfaces

- Product: https://petersmartlink.com
- Help and documentation: https://petersmartlink.com/docs
- Privacy: https://petersmartlink.com/privacy
- Terms: https://petersmartlink.com/terms
- Download: https://petersmartlink.com/download/otya-player
- News: [Otya News](news/)

## Latest update

- [Otya 1.0 enters final reliability validation — 1 September 2026](news/2026-09-01-final-reliability-validation.md)

## Operating documents

- [Beta scope and acceptance](BETA.md)
- [AI operating model](AI_OPERATING_MODEL.md)
- [User-side Next](USER_SIDE_NEXT.md)
- [AI provider strategy](AI_PROVIDER_STRATEGY.md)
- [Public automation policy](PUBLIC_AUTOMATION.md)
- [Developer and communication channels](DEVELOPER_CHANNELS.md)
- [Public Postman collection](postman/Otya-Public.postman_collection.json)

## What belongs here

This repository may contain:

- public product and developer-facing documentation;
- public release and service-health checks;
- safe API examples that contain no credentials or private user data;
- links to official Otya support, security and community surfaces;
- public GitHub Actions that operate only on information safe to expose.

## What does not belong here

Do not commit or print:

- production credentials, API keys, signing material, tokens or service-account files;
- private source code copied here only to obtain public-runner minutes;
- internal infrastructure inventories, private endpoints or administrative procedures;
- user data, crash payloads, private logs or account-recovery material.

If Otya's application or server repositories become private later, this repository can remain public as the stable product/developer hub. Public workflows must continue to operate only on public inputs unless a separately reviewed security design explicitly permits otherwise.

## Product naming

- **Otya** — product
- **Next** — Otya assistant
- **PeterSmart Link** — company/operator

Legacy all-caps `OTYA` identifiers may remain in compatibility-sensitive code or historical records, but public product copy should use **Otya**.

## Release status

Otya v1 is still under acceptance. A successful CI build is not the same as a released or physically device-tested build.

## Security

Please report security issues privately through the official Otya/PeterSmart Link support or security channel. Do not publish secrets, tokens, exploit details or user data in a public issue.
