# CarsXE

<!-- API-EVANGELIST-PROVENANCE:BEGIN -->
> ### About this repository
>
> **This is not our API.** This repository is an independent, third-party profile of a company's
> **publicly available** API surface, maintained by [API Evangelist](https://apievangelist.com).
> API Evangelist does not operate, host, resell, or support this company's APIs, and is not
> affiliated with or endorsed by the company unless stated on the profile.
>
> **Where the information came from.** Everything here is assembled from material a member of the
> public can reach with a browser and no credentials — the company's own website, developer portal
> and documentation, the specifications it publishes for public use (OpenAPI, AsyncAPI, JSON Schema,
> `apis.json`, `llms.txt` and similar), its public repositories, and its public status, pricing and
> changelog pages. **Nothing here is obtained by breaching a system, defeating an access control, or
> using credentials of any kind.**
>
> **The rating is an independent assessment.** The Kin Score and Agent Readiness rating are
> independently calculated scores of a company's *public* API artifacts, produced by API Evangelist
> against a published rubric. They are not certifications, endorsements, security assessments, or
> audits, and they score published artifacts — not the quality, safety, or security of the software.
>
> **Corrections, re-scores, and removal are free.** No partnership, contract, or purchase is
> required, and you do not need to justify the request.
>
> - **Something wrong?** Open an issue on this repository, or email
>   [info@apievangelist.com](mailto:info@apievangelist.com).
> - **Published something new?** Ask for a re-score and we will re-run the rating.
> - **Want the listing taken down?** Say so and we will honor it. The profile is reduced to your
>   company name, a factual description, and a link to your own site, and the company is recorded as
>   **unrated** — never scored zero for having asked.
>
> **Response times.** Acknowledgement within **one business day**; removal or restriction within
> **two business days**; corrections and re-scores within **five business days**.
>
> **Not from the company, and here with a question?** You are welcome here — we would rather be the
> front line and point you the right way than have a good report go nowhere. What this repository
> can answer is narrow, though, so it is worth knowing who you are actually looking for:
>
> - **A question about how the API works, an account, billing, or a bug in the service** — that is
>   the company's own support, not us. We profile this API; we do not operate it and cannot see
>   your account.
> - **A bug in an open-source project we only catalog** — file it on that project's own repository.
>   This has happened with a real and correct bug report that reached us instead of the people who
>   could fix it, which helped nobody.
> - **Anything about this listing itself** — the description, the tags, the rating, a missing or
>   wrong artifact — is ours. Open an issue here.
> - **Not sure, or something general about API Evangelist or APIs.io** — open an issue on the
>   [APIs.io Inbox](https://github.com/api-search/inbox) and we will route it.
>
> **This repository contains no software, and we will never ask you to download anything.** There is
> no build, release, installer, or binary here — only text and machine-readable API descriptions, so
> there is nothing here that can be "corrupt" or need "repairing". Any issue, comment, or email
> claiming otherwise and offering a download link is not from us and is hostile. Do not follow the
> link; it is a lure. Report it to GitHub and, if you like, tell us at
> [info@apievangelist.com](mailto:info@apievangelist.com) so we can take it down.
>
> **On a security or compliance team?** Email
> [info@apievangelist.com](mailto:info@apievangelist.com) with *security* in the subject line and
> you will get a person, not a form. We will tell you exactly which public URLs this profile was
> built from so your team can see the same surface we did, and we will take the listing down on
> request while you work through it.
>
> Full detail: **[Where this data comes from](https://apievangelist.com/about/where-our-data-comes-from)**
<!-- API-EVANGELIST-PROVENANCE:END -->

CarsXE is a B2B vehicle data API platform operated by PiWaves, LLC, offering VIN decoding, vehicle specifications, market value estimates, vehicle history, vehicle imagery, license plate decoding and recognition, VIN OCR, OBD fault-code decoding, international VIN decoding, lien and theft screening, year/make/model lookup and single-VIN or 10,000-VIN batch recall checks. A single OpenAPI 3.1 contract covering 21 operations is published at api.carsxe.com/openapi.json, alongside a remote MCP server, an RFC 9727 api-catalog, an llms.txt index, first-party SDKs for eight languages, and a CLI. Designed for automotive marketplaces, dealerships, insurance, lending, fleet, parking and claims platforms that need programmatic access to rich, current vehicle data.

**Areas:** Automotive · Vehicles · VIN · Vehicle Data · License Plate · OCR · Automobiles · Recalls · Market Value · Vehicle History · MCP · Agents

## CarsXE on APIs.io

Everything profiled for CarsXE is published on APIs.io rather than in this repository. Start at the provider page — **[apis.io/providers/carsxe/](https://apis.io/providers/carsxe/)** — or go straight to one of the APIs or properties below.

### APIs (21)

- [CarsXE Vehicle Specifications API](https://apis.io/apis/carsxe/vehicle-specifications-api/) — VIN decoding and comprehensive vehicle specification lookup. Returns year, make, model, trim, engine, drivetrain, body style, and detailed feature and…
- [CarsXE Vehicle Market Value API](https://apis.io/apis/carsxe/vehicle-market-value-api/) — Returns market value estimates (retail, wholesale, trade-in) for new and used vehicles by VIN, informed by millions of historical vehicle sales.
- [CarsXE Vehicle Images API](https://apis.io/apis/carsxe/vehicle-images-api/) — Retrieves high-quality photos of vehicles by year, make, model (and optional trim / color / background-transparency options) for use in marketplaces, dealer…
- [CarsXE VIN OCR API](https://apis.io/apis/carsxe/vin-ocr-api/) — OCR endpoint that extracts a VIN string from an image of a VIN plate, windshield, or document, enabling mobile-first vehicle-onboarding and inspection…
- [CarsXE Vehicle Plate Decoder API](https://apis.io/apis/carsxe/vehicle-plate-decoder-api/) — Decodes vehicle information from a license plate plus state/province, returning make, model, year, and VIN where available.
- [CarsXE Vehicle Plate Recognition API](https://apis.io/apis/carsxe/vehicle-plate-recognition-api/) — Image-to-text OCR for license plates. Paired with the Plate Decoder, enables full vehicle lookup starting from a plate image, supporting parking,…
- [CarsXE Vehicle History API](https://apis.io/apis/carsxe/vehicle-history-api/) — Raw vehicle-history data endpoint returning title records, accident history, odometer readings, service history, and salvage/lemon flags for a given VIN.
- [CarsXE Vehicle Recalls API](https://apis.io/apis/carsxe/vehicle-recalls-api/) — Returns safety-recall and campaign data for a given VIN, sourced from manufacturer and NHTSA data, for use in inspection, compliance, and pre-purchase…
- [CarsXE International VIN Decoder API](https://apis.io/apis/carsxe/international-vin-decoder-api/) — VIN decoding for non-US vehicles, returning make, model, year, and market-specific trim/spec data for international markets.
- [CarsXE OBD Codes Decoder API](https://apis.io/apis/carsxe/obd-codes-decoder-api/) — Matches an OBD-II diagnostic trouble code (DTC) to a human-readable vehicle fault description for use in service, maintenance, and connected-car applications.
- [CarsXE Specifications API](https://apis.io/apis/carsxe/carsxe-specifications-api/) — VIN decoding for North American and international vehicles — 2 operations (getVehicleSpecs, getInternationalVinDecoder) returning year, make, model, trim,…
- [CarsXE Market Value API](https://apis.io/apis/carsxe/carsxe-market-value-api/) — Vehicle market valuation — 2 operations (getMarketValue v1, getMarketValueV2) returning wholesale, retail and trade-in figures by VIN, with optional state,…
- [CarsXE Recalls API](https://apis.io/apis/carsxe/carsxe-recalls-api/) — Safety recall lookup — 6 operations covering single-VIN recalls, recalls by year/make/model, and the asynchronous Recalls Batch surface (submit up to 10,000…
- [CarsXE History API](https://apis.io/apis/carsxe/carsxe-history-api/) — Vehicle history reporting — 1 operation (getVehicleHistory) returning title records, junk and salvage events, insurance records, odometer readings and brand…
- [CarsXE Images API](https://apis.io/apis/carsxe/carsxe-images-api/) — Vehicle imagery search — 1 operation (getVehicleImages) returning photo links, thumbnails, sources and dimensions filtered by make, model, year, trim,…
- [CarsXE Recognition API](https://apis.io/apis/carsxe/carsxe-recognition-api/) — Image recognition — 2 operations (recognizePlate, vinOcr) that read a license plate or a VIN out of a supplied image URL or base64 payload, returning…
- [CarsXE Year Make Model API](https://apis.io/apis/carsxe/carsxe-year-make-model-api/) — Vehicle lookup without a VIN — 3 operations (getYearMakeModel, getYearMakeModelOptions, decodeObdCode) returning trims, features and option packages by…
- [CarsXE Lien & Theft API](https://apis.io/apis/carsxe/carsxe-lien-theft-api/) — Encumbrance and theft screening — 1 operation (getLienTheft) returning active lien holders, theft reports and recovery status for a VIN, for lenders and…
- [CarsXE Auth API](https://apis.io/apis/carsxe/carsxe-auth-api/) — API key validation — 1 operation (validateKey) against /v1/auth/validate, the endpoint the CarsXE authentication guide documents for confirming that a key…
- [CarsXE MCP Server](https://apis.io/apis/carsxe/carsxe-mcp-server/) — Remote Model Context Protocol server exposing the CarsXE vehicle-data endpoints as 12 named agent tools over streamable HTTP, authenticated with an…
- [CarsXE Plate Decoder API](https://apis.io/apis/carsxe/carsxe-plate-decoder-api/) — Decode license plates into vehicle data

### Published properties

Each property below is a page on APIs.io carrying the machine-readable artifact and what it says.

#### AsyncAPI (1)

Event-driven and webhook contracts.

- [Carsxe Recalls Batch Webhooks](https://apis.io/asyncapis/carsxe/carsxe-recalls-batch-webhooks/)

#### MCP servers (1)

Model Context Protocol servers that expose the API to agents.

- [carsxe](https://apis.io/servers/carsxe/carsxe/)

#### Agentic access (1)

Which operations an agent can call, which act, and which need a human in the loop.

- [Carsxe Agentic Access](https://apis.io/agentic-access/carsxe/carsxe-agentic-access/)

#### JSON-LD (1)

Linked-data contexts for the provider's vocabulary.

- [Carsxe Context](https://apis.io/jsonld/carsxe/carsxe-context/)

#### Collections (6)

Postman and Open Collection request collections.

- [CarsXE Vehicle Data API](https://apis.io/collections/carsxe/open-carsxe/)
- [CarsXE Vehicle Data Auth API](https://apis.io/collections/carsxe/open-carsxe-auth-api/)
- [CarsXE Vehicle Data Auth Market Value API](https://apis.io/collections/carsxe/open-carsxe-market-value-api/)
- [CarsXE Vehicle Data Auth Plate API](https://apis.io/collections/carsxe/open-carsxe-plate-api/)
- [CarsXE Vehicle Data Auth Recalls API](https://apis.io/collections/carsxe/open-carsxe-recalls-api/)
- [CarsXE Vehicle Data Auth Specifications API](https://apis.io/collections/carsxe/open-carsxe-specifications-api/)

#### Overlays (20)

OpenAPI overlays, including conversational phrasing for each operation.

- [Carsxe Auth Api Overlay](https://apis.io/overlays/carsxe/carsxe-auth-api-overlay/)
- [Carsxe Auth Api Phrasing Overlay](https://apis.io/overlays/carsxe/carsxe-auth-api-phrasing-overlay/)
- [Carsxe History Api Overlay](https://apis.io/overlays/carsxe/carsxe-history-api-overlay/)
- [Carsxe History Api Phrasing Overlay](https://apis.io/overlays/carsxe/carsxe-history-api-phrasing-overlay/)
- [Carsxe Images Api Overlay](https://apis.io/overlays/carsxe/carsxe-images-api-overlay/)
- [Carsxe Images Api Phrasing Overlay](https://apis.io/overlays/carsxe/carsxe-images-api-phrasing-overlay/)
- [Carsxe Lien Theft Api Overlay](https://apis.io/overlays/carsxe/carsxe-lien-theft-api-overlay/)
- [Carsxe Lien Theft Api Phrasing Overlay](https://apis.io/overlays/carsxe/carsxe-lien-theft-api-phrasing-overlay/)
- [Carsxe Market Value Api Overlay](https://apis.io/overlays/carsxe/carsxe-market-value-api-overlay/)
- [Carsxe Market Value Api Phrasing Overlay](https://apis.io/overlays/carsxe/carsxe-market-value-api-phrasing-overlay/)
- [Carsxe Plate Api Overlay](https://apis.io/overlays/carsxe/carsxe-plate-api-overlay/)
- [Carsxe Plate Decoder Api Phrasing Overlay](https://apis.io/overlays/carsxe/carsxe-plate-decoder-api-phrasing-overlay/)
- [Carsxe Recalls Api Overlay](https://apis.io/overlays/carsxe/carsxe-recalls-api-overlay/)
- [Carsxe Recalls Api Phrasing Overlay](https://apis.io/overlays/carsxe/carsxe-recalls-api-phrasing-overlay/)
- [Carsxe Recognition Api Overlay](https://apis.io/overlays/carsxe/carsxe-recognition-api-overlay/)
- [Carsxe Recognition Api Phrasing Overlay](https://apis.io/overlays/carsxe/carsxe-recognition-api-phrasing-overlay/)
- [Carsxe Specifications Api Overlay](https://apis.io/overlays/carsxe/carsxe-specifications-api-overlay/)
- [Carsxe Specifications Api Phrasing Overlay](https://apis.io/overlays/carsxe/carsxe-specifications-api-phrasing-overlay/)
- [Carsxe Year Make Model Api Overlay](https://apis.io/overlays/carsxe/carsxe-year-make-model-api-overlay/)
- [Carsxe Year Make Model Api Phrasing Overlay](https://apis.io/overlays/carsxe/carsxe-year-make-model-api-phrasing-overlay/)

#### Security (3)

Authentication, trust centre, and vulnerability disclosure.

- [Carsxe Authentication](https://apis.io/security/carsxe/carsxe-authentication/)
- [Carsxe Domain Security](https://apis.io/security/carsxe/carsxe-domain-security/)
- [Carsxe Trust Center](https://apis.io/security/carsxe/carsxe-trust-center/)

#### Plans and pricing (1)

Published plans, tiers and prices.

- [Carsxe Plans Pricing](https://apis.io/plans/carsxe/carsxe-plans-pricing/)

#### Rate limits (1)

Published request limits.

- [Carsxe Rate Limits](https://apis.io/rate-limits/carsxe/carsxe-rate-limits/)

#### FinOps (1)

What the API costs to run, by operation.

- [Carsxe Finops](https://apis.io/finops/carsxe/carsxe-finops/)

## Where to find this API

Links to the company's own pages. This repository publishes no copy of their specifications — the canonical document is theirs and lives at the URLs below.

- [Website](https://carsxe.com/)
- [Documentation](https://carsxe.com/docs)
- [Getting started](https://carsxe.com/docs/quickstart)
- [API reference](https://carsxe.com/docs/v1)
- [Pricing](https://carsxe.com/pricing)
- [Sign up](https://carsxe.com/register)
- [Support](https://carsxe.com/support)
- [Blog](https://carsxe.com/blog)
- [Compliance](https://carsxe.com/trust)
- [Terms of service](https://carsxe.com/terms-and-conditions)
- [Privacy policy](https://carsxe.com/privacy-policy)
- [GitHub](https://github.com/carsxe)
- [Status](https://carsxe.com/status)

## API Evangelist rating

**Kin Score 72.4** — exemplar · rubric 0.25.0 · scored 2026-10-23

| Facet | Score |
|---|---|
| Discoverability | 85.0 |
| Contract quality | 62.4 |
| Contract governance | 31.8 |
| Operational transparency | 65.8 |
| Developer ergonomics | 80.4 |
| Access clarity | 92.1 |

**Agent readiness 69.1** — agent-ready (gated down from agent-native)

| Agent-readiness dimension | Result |
|---|---|
| Spec Presence | yes |
| Agentic Access | derived (partial credit) |
| Reversibility Documented | documented (partial credit) |
| MCP Server | verified |
| Auth Clarity | served (partial credit) |
| Idempotency | documented (partial credit) |
| Error Semantics | verified |
| OpenAPI Examples | verified |
| Rate Limit Signal | documented (partial credit) |
| Event Surface Described | yes |
| Agent Skills | derived (partial credit) |
| Well Known Catalog | yes |
| Consent Identity | — |
| Agent Card | — |
| Dry Run Mode | — |
| Delegated Identity | served (partial credit) |
| Protected Resource Metadata | verified |
| Dynamic Client Registration | yes |
| Agentic Commerce | — |
| Pagination Ratio | na |
| Operation Distinctiveness | distinct |

**Regulatory alignment 29.4** — Horizontal (data, software, accessibility, platform)

The rubric is published at [github.com/api-evangelist/kin-score](https://github.com/api-evangelist/kin-score). The per-check breakdown behind these numbers — which checks were earned, partial or missed — along with score history and how this provider compares to its peers, is available at [apis.io/providers/carsxe/](https://apis.io/providers/carsxe/).

## How this profile is made

API Evangelist profiles a company's public API surface the way a developer would find it: the website, developer portal and documentation, the specifications it publishes, its public repositories, and its pricing, status and changelog pages. From that it derives the properties above — contracts split per API, workflows, schemas, collections, governance rules, plans and rate limits — and scores them against the published [Kin Score rubric](https://github.com/api-evangelist/kin-score).

The artifacts are published on [APIs.io](https://apis.io), not in this repository. This repository is the public record for CarsXE: the place to say something is wrong, missing or out of date, and to ask for a re-score or a removal.

## Open an issue

- **Something about this listing** — a wrong description, a missing API, a stale artifact or a question about the rating: [open an issue on this repository](https://github.com/api-evangelist/carsxe/issues/new).
- **A new API, or one that is not in the catalog yet** — [submit it on APIs.io](https://apis.io/add/).
- **Anything else** — [the APIs.io inbox](https://github.com/api-search/inbox/issues/new) or [info@apievangelist.com](mailto:info@apievangelist.com).
