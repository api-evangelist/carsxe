# CarsXE (carsxe)

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

CarsXE is a comprehensive vehicle data API platform offering VIN decoding, vehicle specifications, market value estimates, vehicle history, vehicle imagery, license plate recognition, OBD fault-code decoding, international VIN decoding, and recall lookups. Designed for automotive marketplaces, dealerships, insurance, lending, fleet, and claims platforms that need programmatic access to rich, current vehicle data.

**APIs.json:** [https://raw.githubusercontent.com/api-evangelist/carsxe/refs/heads/main/apis.yml](https://raw.githubusercontent.com/api-evangelist/carsxe/refs/heads/main/apis.yml)

## Scope

- **Type:** Index
- **Position:** Provider
- **Access:** 3rd-Party

## Tags

- Automotive
- Vehicles
- VIN
- Vehicle Data
- License Plate
- OCR
- Automobiles

## Timestamps

- **Created:** 2025-02-24
- **Modified:** 2026-04-23

## APIs

### CarsXE Vehicle Specifications API

VIN decoding and comprehensive vehicle specification lookup. Returns year, make, model, trim, engine, drivetrain, body style, and detailed feature and option data for a given North American VIN.

- **Human URL:** [https://api.carsxe.com/vehicle-specifications](https://api.carsxe.com/vehicle-specifications)
- **Base URL:** `https://api.carsxe.com`

#### Tags

- VIN Decoder
- Specifications
- Vehicle Data

#### Properties

- [Documentation](https://api.carsxe.com/vehicle-specifications)
- [Postman Collection](collections/carsxe.postman_collection.json) — [Postman Collection 2.1](https://schema.getpostman.com/json/collection/v2.1.0/collection.json)
- [Open Collection](collections/carsxe.opencollection.json) — [Open Collection 1.0](https://schema.opencollection.com/opencollection/v1.0.0.json)

### CarsXE Vehicle Market Value API

Returns market value estimates (retail, wholesale, trade-in) for new and used vehicles by VIN, informed by millions of historical vehicle sales.

- **Human URL:** [https://api.carsxe.com/vehicle-market-value](https://api.carsxe.com/vehicle-market-value)
- **Base URL:** `https://api.carsxe.com`

#### Tags

- Market Value
- Pricing
- Valuation

#### Properties

- [Documentation](https://api.carsxe.com/vehicle-market-value)
- [Postman Collection](collections/carsxe.postman_collection.json) — [Postman Collection 2.1](https://schema.getpostman.com/json/collection/v2.1.0/collection.json)
- [Open Collection](collections/carsxe.opencollection.json) — [Open Collection 1.0](https://schema.opencollection.com/opencollection/v1.0.0.json)

### CarsXE Vehicle Images API

Retrieves high-quality photos of vehicles by year, make, model (and optional trim / color / background-transparency options) for use in marketplaces, dealer sites, and comparison tools.

- **Human URL:** [https://api.carsxe.com/vehicle-images](https://api.carsxe.com/vehicle-images)
- **Base URL:** `https://api.carsxe.com`

#### Tags

- Images
- Media
- Vehicle Data

#### Properties

- [Documentation](https://api.carsxe.com/vehicle-images)
- [Postman Collection](collections/carsxe.postman_collection.json) — [Postman Collection 2.1](https://schema.getpostman.com/json/collection/v2.1.0/collection.json)
- [Open Collection](collections/carsxe.opencollection.json) — [Open Collection 1.0](https://schema.opencollection.com/opencollection/v1.0.0.json)

### CarsXE VIN OCR API

OCR endpoint that extracts a VIN string from an image of a VIN plate, windshield, or document, enabling mobile-first vehicle-onboarding and inspection workflows.

- **Human URL:** [https://api.carsxe.com/vin-ocr](https://api.carsxe.com/vin-ocr)
- **Base URL:** `https://api.carsxe.com`

#### Tags

- OCR
- VIN
- AI

#### Properties

- [Documentation](https://api.carsxe.com/vin-ocr)
- [Postman Collection](collections/carsxe.postman_collection.json) — [Postman Collection 2.1](https://schema.getpostman.com/json/collection/v2.1.0/collection.json)
- [Open Collection](collections/carsxe.opencollection.json) — [Open Collection 1.0](https://schema.opencollection.com/opencollection/v1.0.0.json)

### CarsXE Vehicle Plate Decoder API

Decodes vehicle information from a license plate plus state/province, returning make, model, year, and VIN where available.

- **Human URL:** [https://api.carsxe.com/vehicle-plate-decoder](https://api.carsxe.com/vehicle-plate-decoder)
- **Base URL:** `https://api.carsxe.com`

#### Tags

- License Plate
- Lookup
- Vehicle Data

#### Properties

- [Documentation](https://api.carsxe.com/vehicle-plate-decoder)
- [Postman Collection](collections/carsxe.postman_collection.json) — [Postman Collection 2.1](https://schema.getpostman.com/json/collection/v2.1.0/collection.json)
- [Open Collection](collections/carsxe.opencollection.json) — [Open Collection 1.0](https://schema.opencollection.com/opencollection/v1.0.0.json)

### CarsXE Vehicle Plate Recognition API

Image-to-text OCR for license plates. Paired with the Plate Decoder, enables full vehicle lookup starting from a plate image, supporting parking, access-control, law-enforcement, and valet use cases.

- **Human URL:** [https://api.carsxe.com/vehicle-plate-recognition](https://api.carsxe.com/vehicle-plate-recognition)
- **Base URL:** `https://api.carsxe.com`

#### Tags

- License Plate
- OCR
- AI

#### Properties

- [Documentation](https://api.carsxe.com/vehicle-plate-recognition)
- [Postman Collection](collections/carsxe.postman_collection.json) — [Postman Collection 2.1](https://schema.getpostman.com/json/collection/v2.1.0/collection.json)
- [Open Collection](collections/carsxe.opencollection.json) — [Open Collection 1.0](https://schema.opencollection.com/opencollection/v1.0.0.json)

### CarsXE Vehicle History API

Raw vehicle-history data endpoint returning title records, accident history, odometer readings, service history, and salvage/lemon flags for a given VIN.

- **Human URL:** [https://api.carsxe.com/vehicle-history](https://api.carsxe.com/vehicle-history)
- **Base URL:** `https://api.carsxe.com`

#### Tags

- History
- Title
- Accident

#### Properties

- [Documentation](https://api.carsxe.com/vehicle-history)
- [Postman Collection](collections/carsxe.postman_collection.json) — [Postman Collection 2.1](https://schema.getpostman.com/json/collection/v2.1.0/collection.json)
- [Open Collection](collections/carsxe.opencollection.json) — [Open Collection 1.0](https://schema.opencollection.com/opencollection/v1.0.0.json)

### CarsXE Vehicle Recalls API

Returns safety-recall and campaign data for a given VIN, sourced from manufacturer and NHTSA data, for use in inspection, compliance, and pre-purchase workflows.

- **Human URL:** [https://api.carsxe.com/vehicle-recalls](https://api.carsxe.com/vehicle-recalls)
- **Base URL:** `https://api.carsxe.com`

#### Tags

- Recalls
- Safety
- Compliance

#### Properties

- [Documentation](https://api.carsxe.com/vehicle-recalls)
- [Postman Collection](collections/carsxe.postman_collection.json) — [Postman Collection 2.1](https://schema.getpostman.com/json/collection/v2.1.0/collection.json)
- [Open Collection](collections/carsxe.opencollection.json) — [Open Collection 1.0](https://schema.opencollection.com/opencollection/v1.0.0.json)

### CarsXE International VIN Decoder API

VIN decoding for non-US vehicles, returning make, model, year, and market-specific trim/spec data for international markets.

- **Human URL:** [https://api.carsxe.com/international-vin-decoder](https://api.carsxe.com/international-vin-decoder)
- **Base URL:** `https://api.carsxe.com`

#### Tags

- VIN Decoder
- International
- Specifications

#### Properties

- [Documentation](https://api.carsxe.com/international-vin-decoder)
- [Postman Collection](collections/carsxe.postman_collection.json) — [Postman Collection 2.1](https://schema.getpostman.com/json/collection/v2.1.0/collection.json)
- [Open Collection](collections/carsxe.opencollection.json) — [Open Collection 1.0](https://schema.opencollection.com/opencollection/v1.0.0.json)

### CarsXE OBD Codes Decoder API

Matches an OBD-II diagnostic trouble code (DTC) to a human-readable vehicle fault description for use in service, maintenance, and connected-car applications.

- **Human URL:** [https://api.carsxe.com/obd-codes-decoder](https://api.carsxe.com/obd-codes-decoder)
- **Base URL:** `https://api.carsxe.com`

#### Tags

- OBD
- Diagnostics
- Maintenance

#### Properties

- [Documentation](https://api.carsxe.com/obd-codes-decoder)
- [Postman Collection](collections/carsxe.postman_collection.json) — [Postman Collection 2.1](https://schema.getpostman.com/json/collection/v2.1.0/collection.json)
- [Open Collection](collections/carsxe.opencollection.json) — [Open Collection 1.0](https://schema.opencollection.com/opencollection/v1.0.0.json)

## Common Properties

- [GitHub Organization](https://github.com/carsxe)
- [LinkedIn](https://www.linkedin.com/company/carsxe)
- [Website](https://api.carsxe.com/)
- [Portal](https://api.carsxe.com/)
- [Documentation](https://api.carsxe.com/docs)
- [Getting Started](https://api.carsxe.com/docs/quickstart)
- [Authentication](https://api.carsxe.com/docs/authentication)
- [Errors](https://api.carsxe.com/docs/errors)
- [Pricing](https://api.carsxe.com/pricing)
- [About](https://api.carsxe.com/about)
- [Blog](https://api.carsxe.com/blog)
- [Support](https://api.carsxe.com/support)
- [Contact](https://api.carsxe.com/contact-us)
- [Terms of Service](https://api.carsxe.com/terms-and-conditions)
- [Login](https://api.carsxe.com/login)
- [Sign Up](https://api.carsxe.com/register)

## Maintainers

**FN:** Kin Lane
**Email:** info@apievangelist.com
