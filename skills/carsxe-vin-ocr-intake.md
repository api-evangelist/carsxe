---
name: carsxe-vin-ocr-intake
description: >-
  Onboard a vehicle from a photo of its VIN plate or windshield etching using the CarsXE API — OCR
  the VIN out of the image, decode it (domestically or internationally), and return a listing-ready
  record with imagery. For marketplace, inspection and mobile intake flows.
api: openapi/_original/carsxe-openapi.yml
operations:
  - vinOcr
  - getVehicleSpecs
  - getInternationalVinDecoder
  - getVehicleImages
  - decodeObdCode
---

# CarsXE — VIN OCR intake

## Steps

1. **Extract the VIN** — `vinOcr`
   `POST /v1/vinocr?key=$KEY` with `{"image_url": "https://..."}` (a base64 payload also works).
   Returns the detected VIN with a confidence score, bounding box and candidate list.
   - `400 Missing image data` — no image was supplied.
   - `400 Invalid image data format. Must be a valid URL or base64 encoded string.` — the URL is not
     publicly fetchable, or the base64 is truncated.
   - `404 No valid VIN candidates found in the image` / `No text detected in the image` — ask for a
     higher-resolution shot of the VIN plate or the windshield etching.
   **Do not accept a low-confidence candidate silently.** Show the user the detected VIN and the
   confidence before you spend quota decoding it.

2. **Decode it** — `getVehicleSpecs` for North American vehicles
   `GET /specs?key=$KEY&vin=$VIN`. On `404 No data found for this VIN` retry once with `deepdata=1`.
   If the vehicle is not North American, or specs still miss, use `getInternationalVinDecoder`
   (`GET /v1/international-vin-decoder?key=$KEY&vin=$VIN`) instead — it covers European, Asian and
   other markets. You can also suppress the automatic international fallback on `/specs` with
   `disableIntVINDecoding` when you want a strictly domestic answer.

3. **Add imagery** — `getVehicleImages`
   `GET /images?key=$KEY&make=$MAKE&model=$MODEL&year=$YEAR&color=$COLOR`
   Both `make` and `model` are required; omitting either returns a `500` on this legacy route.
   `transparent=true` returns cut-out images suitable for a listing card.

4. **Optional — decode a fault code from the same intake** — `decodeObdCode`
   `GET /obdcodesdecoder?key=$KEY&code=P0300`
   Useful when the inspection also captured a scanner reading. Accepts SAE J2012 codes (`P`, `B`,
   `C`, `U` prefixes).

## Notes

- Steps 1 and 3 are also available on the EU host `https://eu-api.carsxe.com` for lower latency from
  Europe; `/specs` and `/obdcodesdecoder` are US-only and 404 there.
- VIN OCR, images and OBD decoding are the cheapest products on the price list ($0.15 Starter /
  $0.10 Pro per successful call); a failed 400 validation costs nothing.
- Never fabricate a VIN to fill a gap. If OCR misses, say it missed.
