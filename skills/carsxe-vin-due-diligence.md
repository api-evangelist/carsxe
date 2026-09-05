---
name: carsxe-vin-due-diligence
description: >-
  Run a full pre-purchase due-diligence pass on a used vehicle from its VIN using the CarsXE API —
  specifications, history, liens and theft, open safety recalls, and a condition-adjusted market
  value — and report the findings in the order a buyer needs them.
api: openapi/_original/carsxe-openapi.yml
operations:
  - getVehicleSpecs
  - getVehicleHistory
  - getLienTheft
  - getVehicleRecalls
  - getMarketValueV2
---

# CarsXE — VIN due diligence

Use this when someone gives you a 17-character VIN and asks whether the vehicle is worth buying.

## Before you start

- Base URL: `https://api.carsxe.com`. Authenticate by appending `key=$CARSXE_API_KEY` as a **query
  parameter** on every request. There is no bearer token on the REST API.
- Validate the VIN yourself first: exactly 17 characters, no `I`, `O` or `Q`. A malformed VIN returns
  `400 Wrong VIN length, must be 17 characters` — and 400 validation failures are **free**, they do
  not consume quota.
- `history`, `marketvalue` and `lien-theft` are **not included** in the Starter or Pro monthly
  quotas — every call is metered overage ($4.99, $1.50 and $1.00 respectively). Say so before you
  run all five steps on someone's account.
- Check `body.success` on every response, not just the status code. Some legacy v1 routes report
  validation failures as `500`.

## Steps

1. **Identify the vehicle** — `getVehicleSpecs`
   `GET /specs?key=$KEY&vin=$VIN`
   If it returns `404 No data found for this VIN. Try a deep search by setting deepdata=1`, retry
   once with `&deepdata=1`. Report year, make, model, trim, engine and drivetrain before going on —
   if this does not match what the seller claims, stop and say so.

2. **Pull the title and event history** — `getVehicleHistory`
   `GET /history?key=$KEY&vin=$VIN`
   Look for salvage or junk brands, odometer inconsistencies and insurance total-loss records. These
   are the findings that end a purchase, so lead with them.

3. **Check encumbrance and theft** — `getLienTheft`
   `GET /v1/lien-theft?key=$KEY&vin=$VIN`
   `404 No lien or theft data found for this VIN` is a **clean result**, not an error. Say "no
   records found", never "lookup failed".

4. **Check open safety recalls** — `getVehicleRecalls`
   `GET /v1/recalls?key=$KEY&vin=$VIN`
   Report each open campaign with its consequence and remedy. An open recall is a bargaining point,
   not usually a deal-breaker.

5. **Value it against condition** — `getMarketValueV2`
   `GET /v2/marketvalue?key=$KEY&vin=$VIN&state=$STATE&mileage=$MILES&condition=$COND`
   `condition` accepts only `excellent`, `clean`, `average`, `rough` — anything else returns
   `400 Invalid condition`. `mileage` must be digits only. Pass both when you have them; v2 adjusts
   for mileage and region and that is the whole accuracy win over v1.

## Error and retry rules

- Retry only `500`, `502`, `503`, `504`, once, with exponential backoff.
- Never retry a `4xx`. A `429` here is a **monthly quota exhaustion**, not a throttle — backoff never
  clears it. Read `usage.remaining` from the body and tell the user to upgrade the tier or enable
  overage billing.
- `403 This API is not available for your current subscription tier` means the plan does not include
  that endpoint. Skip the step and say which one was unavailable rather than silently omitting it.
- A response may carry "The response is from the cache". Not-found VIN results are cached for about
  a day, so hammering the same VIN will not produce a different answer.

## Reporting

Report in risk order: title brands and theft first, then open recalls, then value, then
specifications. Always state which steps you actually ran and which were skipped for plan reasons.
