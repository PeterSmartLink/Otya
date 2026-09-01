# Next AI provider strategy

Next should not depend on one model vendor.

## Goals

- Keep local Otya features independent of online AI.
- Use the cheapest reliable provider for ordinary requests.
- Route harder reasoning, agentic, coding, or multimodal requests to stronger models only when needed.
- Never expose provider API keys in the Android app, public repository, logs, or user-visible responses.
- Keep provider failures and quota exhaustion recoverable.
- Treat development/trial endpoints differently from production endpoints.

## Current baseline

The Otya AI Worker already supports multiple models through Cloudflare Workers AI, including an NVIDIA Nemotron model. Cloudflare remains the default provider for the beta because it is already integrated and has a Free-plan allowance.

## NVIDIA NIM

NVIDIA NIM can be added as an optional server-side provider for development and beta evaluation.

Important licensing/operations rule: NVIDIA Developer Program hosted NIM endpoints are for prototyping, research, development, testing, and evaluation. Do not treat the free hosted endpoints as Otya's permanent production inference service for real end-users. Production use must move to an approved production-capable NVIDIA/partner/self-hosted route with suitable commercial terms.

Suggested evaluation models as of September 2026:

- `nvidia/nemotron-3.5-lightning-30b-a3b` — fast agentic/general reasoning candidate.
- `deepseek-ai/deepseek-v4-flash-0731` — long-context reasoning/coding candidate.
- `deepseek-ai/deepseek-v4-pro-0813` — stronger agentic/coding candidate where available.
- multimodal models should be evaluated separately rather than becoming the default text model.

Model IDs are configuration, not product promises. They may change without changing the public Next identity.

## Routing policy

1. **Fast/general** — use the low-cost Cloudflare default.
2. **Otya help** — retrieve current Otya knowledge first, then use a low-cost model.
3. **Hard reasoning** — route to a stronger allowed model when quota and provider policy permit.
4. **Owner/admin work** — use a stronger model only inside the owner permission boundary; never expose admin tools to normal users.
5. **Provider failure/quota** — try an approved fallback; if all online inference is unavailable, fail quickly and keep local Otya features working.

## Provider boundary

The Android client calls only the Otya AI backend. It never chooses arbitrary upstream endpoints and never receives upstream credentials.

The backend provider adapter owns:

- endpoint selection;
- API authentication;
- model allow-listing;
- timeout and retry behavior;
- streaming normalization;
- quota/cost telemetry;
- provider-specific error normalization;
- production-vs-prototype policy.

## Knowledge is not model training

Otya product knowledge should come from a small verified instruction layer plus retrieval of current Help/Trust/product facts. Do not keep adding the whole product manual to every prompt and do not retrain a model for every Otya update.

## Production gate

Before any provider becomes production-default:

- confirm commercial/production terms;
- measure time-to-first-token and completion latency from Uganda and representative user networks;
- measure failure rate and quota behavior;
- verify streaming, tool calling, safety, and multilingual quality;
- compare cost per useful request;
- verify privacy/data-processing disclosures;
- keep a tested fallback provider;
- obtain owner approval for the production routing change.
