---
name: carsxe-bulk-recall-sweep
description: >-
  Sweep a whole fleet or inventory list for open safety recalls with the CarsXE Recalls Batch API —
  submit up to 10,000 VINs, poll or receive a webhook, then retrieve or download the results. The
  only asynchronous workflow CarsXE exposes.
api: openapi/carsxe-recalls-api-openapi.yml
operations:
  - submitRecallsBatch
  - getRecallsBatchStatus
  - getRecallsBatchResults
  - downloadRecallsBatchResults
  - getRecallsByYmm
---

# CarsXE — bulk recall sweep

This is the one CarsXE workflow that creates server-side state and runs asynchronously. It is
**REST-only** — there is no MCP tool for it, so an agent working through the CarsXE MCP server
cannot run a batch.

## Steps

1. **Submit** — `submitRecallsBatch`
   `POST /v1/recalls-batch/submit?key=$KEY` with a JSON body. VINs can be supplied three ways and
   they are merged and deduplicated: a `vins` array, inline `csv` text, or a `csvUrl`.
   - Cap is **10,000 VINs per batch**. Over that: `400 BULK_RECALL_BATCH_TOO_MANY_VINS`.
   - `csvUrl` must be HTTPS, under 5 MB, and hosted on an allowed host (Google Cloud Storage, Google
     Sheets, Google Drive, S3, Dropbox, Azure Blob, DigitalOcean Spaces, Box). Anything else returns
     `400 BULK_RECALL_BATCH_CSV_URL_HOST_NOT_ALLOWED`.
   - Optionally pass `webhookUrl` — a valid HTTPS URL — to be told when the job finishes instead of
     polling. Redirects are not followed and CarsXE gives up after about 30 seconds, so the endpoint
     must answer fast.
   - **Send an `Idempotency-Key` header on any retry.** CarsXE deduplicates wallet deductions only
     when the same key is reused for the same logical request; a retried submit without it is billed
     again. This is the single operation where that matters most.
   - Returns `202` with a `batchId` like `brb_mnablbn7_wvbaqv`.

2. **Wait** — `getRecallsBatchStatus`
   `GET /v1/recalls-batch/status?key=$KEY&batchId=$ID`
   States are `processing`, `uploading`, `completed`, `partial`, `failed`. Poll no more often than
   every 30 seconds. Typical turnaround is 30–60 minutes; a fully cached batch can come back
   `completed` immediately on submit. If you passed `webhookUrl`, wait for
   `bulk_recall_batch_complete` instead of polling.

3. **Retrieve** — `getRecallsBatchResults` or `downloadRecallsBatchResults`
   `GET /v1/recalls-batch/results?key=$KEY&batchId=$ID` for JSON, or
   `GET /v1/recalls-batch/download?key=$KEY&batchId=$ID` for CSV.
   Calling either before the job is terminal returns `409 BULK_RECALL_BATCH_NOT_COMPLETE` — that is a
   "not yet", not a failure. `partial` means some rows returned; take what came back.
   `hitCount` and `hasRecalls` both mean at least one open safety-type recall row for that VIN.

## Things to tell the user

- **A submitted batch cannot be cancelled.** CarsXE publishes no cancel, delete or reverse operation
  for a batch job. It is a read-only lookup, so nothing needs undoing — but do not promise a
  cancellation path that does not exist.
- Billing is **1 unit per VIN**, not per request. A 10,000-VIN batch consumes 10,000 units. Check
  `usage.remaining` on a `429` before resubmitting; if the batch is too large for what is left, the
  message says so and you should shrink it rather than retry.
- The `downloadUrl` in the completion webhook **embeds the account API key in its query string**.
  Treat the webhook endpoint and any logs of it as credential-bearing.
- If you do not have VINs, `getRecallsByYmm` (`GET /v1/recalls-ymm?key=$KEY&year=&make=&model=`)
  answers the same question from a year/make/model with no VIN at all.
