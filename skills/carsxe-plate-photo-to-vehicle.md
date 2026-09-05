---
name: carsxe-plate-photo-to-vehicle
description: >-
  Turn a photo of a vehicle's license plate into a full vehicle record with the CarsXE API — read
  the plate from the image, decode it to a VIN and vehicle, then pull specifications. For parking,
  valet, access control and marketplace intake flows.
api: openapi/_original/carsxe-openapi.yml
operations:
  - recognizePlate
  - decodePlateV2
  - getVehicleSpecs
  - getVehicleImages
---

# CarsXE — plate photo to vehicle record

## Before you start

- Base URL `https://api.carsxe.com`, key as the `key` query parameter.
- The two OCR endpoints are **POST with a JSON body** and take an image URL or a base64 payload. The
  URL must be publicly reachable — `400 Invalid image data format` means CarsXE could not fetch it.
- If your caller is in Europe, use `https://eu-api.carsxe.com` for steps 1 and 2: plate recognition,
  the multi-country plate decoder, VIN OCR, the international VIN decoder and images are deployed in
  `europe-west1`. Everything else is US-only and returns `404` on the EU host.

## Steps

1. **Read the plate out of the image** — `recognizePlate`
   `POST /platerecognition?key=$KEY` with `{"image_url": "https://..."}`
   Returns detected plates with confidence scores and bounding boxes. `404 No plates detected in
   image` means the image is too dark, too small or the plate is obscured — ask for a better photo
   rather than retrying the same one. If several plates come back, take the highest-confidence
   detection and say which one you used.

2. **Decode the plate to a vehicle** — `decodePlateV2`
   `GET /v2/platedecoder?key=$KEY&plate=$PLATE&country=$CC&state=$ST`
   `country` is **required** and must be ISO 3166-1 alpha-2. For US, CA and AU also pass `state`;
   Pakistan additionally takes `district`. `404 Invalid state or country code.` means the code is
   not ISO-shaped. The response shape differs per country — do not assume US field names.
   For Spanish plates you can pass `require_vin=true` to guarantee a VIN, but it is **billed twice
   and counts twice** toward usage. Ask before using it.

3. **Expand the vehicle** — `getVehicleSpecs`
   `GET /specs?key=$KEY&vin=$VIN` with the VIN from step 2, when one was returned. Not every country
   returns a VIN; if none came back, report the make/model/year from step 2 and stop there rather
   than guessing a VIN.

4. **Optional — illustrate it** — `getVehicleImages`
   `GET /images?key=$KEY&make=$MAKE&model=$MODEL&year=$YEAR`
   `make` and `model` are both required; omitting either returns a **`500`** on this legacy route,
   which is a validation error, not an outage. If you get `404 No images found`, drop `trim` and
   `color` and try once more.

## Notes

- `decodePlate` (`GET /platedecoder`) is the v1 endpoint and still served; prefer v2 for anything
  outside the US.
- `decodeUsPlate` (`GET /v1/us-platedecoder`) is a US-specific alternative that can decode the
  resolved VIN in the same call via `decodeVIN`.
- Plate lookups are the most expensive per-call product on the Starter tier ($0.50 overage). Do not
  loop over a video feed.
