# CarsXE (carsxe)

CarsXE is a comprehensive vehicle data API platform offering VIN decoding, vehicle specifications, market value estimates, vehicle history, vehicle imagery, license plate recognition, OBD fault-code decoding, international VIN decoding, and recall lookups. Designed for automotive marketplaces, dealerships, insurance, lending, fleet, and claims platforms that need programmatic access to rich, current vehicle data.

**URL:** [Visit APIs.json URL](https://raw.githubusercontent.com/api-evangelist/carsxe/refs/heads/main/apis.yml)

## Scope

- **Type:** Index
- **Position:** Provider
- **Access:** 3rd-Party

## Tags

 - Automotive, Vehicles, VIN, Vehicle Data, License Plate, OCR, Automobiles

## Timestamps

- **Created:** 2025-02-24
- **Modified:** 2026-04-23

## APIs

### CarsXE Vehicle Specifications API

VIN decoding and comprehensive vehicle specification lookup. Returns year, make, model, trim, engine, drivetrain, body style, and detailed feature and option data for a given North American VIN.

**Human URL:** [https://api.carsxe.com/vehicle-specifications](https://api.carsxe.com/vehicle-specifications)

#### Tags

 - VIN Decoder, Specifications, Vehicle Data

### CarsXE Vehicle Market Value API

Returns market value estimates (retail, wholesale, trade-in) for new and used vehicles by VIN, informed by millions of historical vehicle sales.

**Human URL:** [https://api.carsxe.com/vehicle-market-value](https://api.carsxe.com/vehicle-market-value)

#### Tags

 - Market Value, Pricing, Valuation

### CarsXE Vehicle Images API

Retrieves high-quality photos of vehicles by year, make, model (and optional trim / color / background-transparency options) for use in marketplaces, dealer sites, and comparison tools.

**Human URL:** [https://api.carsxe.com/vehicle-images](https://api.carsxe.com/vehicle-images)

#### Tags

 - Images, Media, Vehicle Data

### CarsXE VIN OCR API

OCR endpoint that extracts a VIN string from an image of a VIN plate, windshield, or document, enabling mobile-first vehicle-onboarding and inspection workflows.

**Human URL:** [https://api.carsxe.com/vin-ocr](https://api.carsxe.com/vin-ocr)

#### Tags

 - OCR, VIN, AI

### CarsXE Vehicle Plate Decoder API

Decodes vehicle information from a license plate plus state/province, returning make, model, year, and VIN where available.

**Human URL:** [https://api.carsxe.com/vehicle-plate-decoder](https://api.carsxe.com/vehicle-plate-decoder)

#### Tags

 - License Plate, Lookup, Vehicle Data

### CarsXE Vehicle Plate Recognition API

Image-to-text OCR for license plates. Paired with the Plate Decoder, enables full vehicle lookup starting from a plate image, supporting parking, access-control, law-enforcement, and valet use cases.

**Human URL:** [https://api.carsxe.com/vehicle-plate-recognition](https://api.carsxe.com/vehicle-plate-recognition)

#### Tags

 - License Plate, OCR, AI

### CarsXE Vehicle History API

Raw vehicle-history data endpoint returning title records, accident history, odometer readings, service history, and salvage/lemon flags for a given VIN.

**Human URL:** [https://api.carsxe.com/vehicle-history](https://api.carsxe.com/vehicle-history)

#### Tags

 - History, Title, Accident

### CarsXE Vehicle Recalls API

Returns safety-recall and campaign data for a given VIN, sourced from manufacturer and NHTSA data, for use in inspection, compliance, and pre-purchase workflows.

**Human URL:** [https://api.carsxe.com/vehicle-recalls](https://api.carsxe.com/vehicle-recalls)

#### Tags

 - Recalls, Safety, Compliance

### CarsXE International VIN Decoder API

VIN decoding for non-US vehicles, returning make, model, year, and market-specific trim/spec data for international markets.

**Human URL:** [https://api.carsxe.com/international-vin-decoder](https://api.carsxe.com/international-vin-decoder)

#### Tags

 - VIN Decoder, International, Specifications

### CarsXE OBD Codes Decoder API

Matches an OBD-II diagnostic trouble code (DTC) to a human-readable vehicle fault description for use in service, maintenance, and connected-car applications.

**Human URL:** [https://api.carsxe.com/obd-codes-decoder](https://api.carsxe.com/obd-codes-decoder)

#### Tags

 - OBD, Diagnostics, Maintenance

## Use Cases

- Dealer inventory enrichment — hydrating a VIN-only feed into full year/make/model/trim/photo listings on dealer and marketplace sites.
- Automated vehicle intake — a mobile scanner photographs a VIN plate or license plate; the OCR + Decoder APIs resolve to a full vehicle record without manual data entry.
- Pre-purchase due diligence — combining the Vehicle History and Recalls APIs to surface title brands, accident history, odometer rollback risk, and open safety campaigns before a buyer commits.
- Lending and insurance valuation — pulling market-value estimates by VIN to underwrite loans, set insured values, or price claims.
- Fleet maintenance triage — translating OBD-II DTCs into human-readable diagnostics in connected-car and service-scheduling workflows.
- Parking, access control, and toll — plate-recognition and plate-decoder in combination to identify vehicles entering a facility or crossing a road segment.
- International vehicle data — expanding automotive products beyond North America using the International VIN Decoder.

## Common Properties

- [Documentation](https://api.carsxe.com/docs)
- [Portal](https://api.carsxe.com/)
- [GettingStarted](https://api.carsxe.com/docs/quickstart)
- [Authentication](https://api.carsxe.com/docs/authentication)
- [Errors](https://api.carsxe.com/docs/errors)
- [Pricing](https://api.carsxe.com/pricing)
- [About](https://api.carsxe.com/about)
- [Blog](https://api.carsxe.com/blog)
- [Support](https://api.carsxe.com/support)
- [Contact](https://api.carsxe.com/contact-us)
- [TermsOfService](https://api.carsxe.com/terms-and-conditions)
- [Login](https://api.carsxe.com/login)
- [SignUp](https://api.carsxe.com/register)
- [JSON-LD Context](json-ld/carsxe-context.jsonld)
- [Vocabulary Definition](vocabulary.yml)
- [Spectral Rules](spectral/carsxe.spectral.yml)

## Maintainers

**FN:** Kin Lane

**Email:** info@apievangelist.com
