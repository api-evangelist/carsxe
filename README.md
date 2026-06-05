# CarsXE (carsxe)

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
