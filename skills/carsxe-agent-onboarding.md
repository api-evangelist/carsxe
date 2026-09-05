---
name: agent-onboarding
description: |
  CarsXE gives AI agents access to vehicle data APIs: VIN decode, market value,
  history, recalls, plate decoder, lien & theft, international VIN, images,
  year/make/model, plate OCR, VIN OCR, and OBD codes. Option 1 (Shell/HTTP,
  recommended for chat agents): get API key + call endpoints via curl. Option 2
  (@carsxe/cli, recommended for coding agents): install CLI + call endpoints.
---

# CarsXE API — Agent Onboarding

CarsXE provides vehicle data APIs: VIN decode, market value, history, recalls, plate decoder, lien & theft, international VIN decoder, images, year/make/model, plate image recognition, VIN OCR, and OBD codes decoder.

Base API URL: `https://api.carsxe.com`

---

## How to call the API

Choose based on your agent type:

| | Shell / HTTP — recommended for chat agents | `@carsxe/cli` — recommended for coding agents |
| --------------------- | ------------------------- | ---------------------------------------------------- |
| **Requires** | `curl` or HTTP client | Node.js 22+, `npm install -g @carsxe/cli` |
| **Auth** | API key as query param | `CARSXE_API_KEY` env var or `~/.carsxe/config.json` |
| **Output** | Raw JSON | JSON (pretty or raw), optional table |
| **Error handling** | HTTP status codes | Exit codes (0 = success, 1 = error) + stderr |

---

## Option 1 — Shell / HTTP (recommended for chat agents)

Chat agents that cannot run subprocesses can call the REST API directly with any HTTP client tool. In environments where subprocesses are available, you can also use `curl`.

### Authentication

No CLI install needed. Use the interactive browser auth flow to get your API key.

> **GUI guidance:** At each waiting step, use `AskUserQuestion` (or your platform's equivalent interactive prompt tool) to present the user with clickable options instead of plain text. This matches the pattern shown in tools like Claude Code / Firecrawl onboarding — numbered option cards the user can tap rather than type.

#### Step 1 — Generate auth parameters

```bash
SESSION_ID=$(openssl rand -hex 32)
CODE_VERIFIER=$(openssl rand -base64 32 | tr '+/' '-_' | tr -d '=\n' | head -c 43)
CODE_CHALLENGE=$(printf '%s' "$CODE_VERIFIER" | openssl dgst -sha256 -binary | openssl base64 -A | tr '+/' '-_' | tr -d '=')
```

#### Step 2 — Direct the user to authorize

Build the URL from the generated parameters, then present it as a markdown hyperlink — never paste the raw URL:

```
[Click here to authorize with CarsXE](https://carsxe.com/cli-auth?code_challenge=$CODE_CHALLENGE&source=coding-agent#session_id=$SESSION_ID)
```

Then use `AskUserQuestion` to pause and wait — **do not poll yet**. Present clickable options:

```
Have you clicked 'Authorize' on the CarsXE page?

1. Yes, I authorized       — I clicked Authorize in the browser
2. Not yet                 — I still need to open the link
3. Type something else...
[Skip]
```

Only proceed to Step 3 after the user selects option 1.

#### Step 3 — Poll for the API key

POST every 3 seconds until `status` is `complete`:

```bash
curl -s -X POST https://carsxe.com/api/auth/cli/status \
  -H "Content-Type: application/json" \
  -d "{\"session_id\": \"$SESSION_ID\", \"code_verifier\": \"$CODE_VERIFIER\"}"
```

Response when complete:

```json
{ "status": "complete", "apiKey": "your-api-key", "teamName": "Your Team" }
```

Abort after 5 minutes or 5 consecutive errors.

#### Step 4 — Store the key

```bash
echo "CARSXE_API_KEY=your-api-key" >> .env
```

After storing the key, use `AskUserQuestion` to confirm next steps:

```
API key saved! What would you like to do next?

1. Decode a VIN
2. Look up a license plate
3. Get a market value estimate
4. Something else...
```

### Available Endpoints

All GET endpoints accept `key` as a query parameter. POST endpoints accept `key` as a query parameter and send the body as JSON.

#### Vehicle Specifications (VIN Decode)
Decode a VIN — make, model, year, engine, trim, equipment, and more.
```bash
curl -G https://api.carsxe.com/specs -d key=$CARSXE_API_KEY -d vin=WBAFR7C57CC811956
```

#### Market Value
Retail, trade-in, and auction values. Optional: `mileage`, `state`, `condition` (excellent/clean/average/rough).
```bash
curl -G https://api.carsxe.com/v2/marketvalue -d key=$CARSXE_API_KEY -d vin=WBAFR7C57CC811956 -d mileage=50000 -d state=CA -d condition=clean
```

#### Vehicle History
Title records, junk/salvage events, and insurance history by VIN.
```bash
curl -G https://api.carsxe.com/history -d key=$CARSXE_API_KEY -d vin=WBAFR7C57CC811956
```

#### Vehicle Recalls
Open NHTSA safety recalls by VIN.
```bash
curl -G https://api.carsxe.com/v1/recalls -d key=$CARSXE_API_KEY -d vin=WBAFR7C57CC811956
```

#### Lien & Theft Check
Active liens and theft records by VIN.
```bash
curl -G https://api.carsxe.com/v1/lien-theft -d key=$CARSXE_API_KEY -d vin=WBAFR7C57CC811956
```

#### Plate Decoder
Look up a vehicle by license plate. Supports 50+ countries. Required: `plate`, `country`. `state` required for US, AU, CA.
```bash
curl -G https://api.carsxe.com/v2/platedecoder -d key=$CARSXE_API_KEY -d plate=7XER187 -d country=US -d state=CA
```

#### International VIN Decoder
Decode a non-US VIN (Europe, Asia, and other markets).
```bash
curl -G https://api.carsxe.com/v1/international-vin-decoder -d key=$CARSXE_API_KEY -d vin=WF0MXXGBWM8R43240
```

#### Vehicle Images
Photos by make, model, year. Optional: `color`, `angle` (front/side/back), `photoType` (interior/exterior/engine), `size` (Small/Medium/Large/Wallpaper/All).
```bash
curl -G https://api.carsxe.com/images -d key=$CARSXE_API_KEY -d make=BMW -d model=5-Series -d year=2012
```

#### Year / Make / Model
Look up vehicle data without a VIN. Optional: `trim`, `allTrimOptions=1`.
```bash
curl -G https://api.carsxe.com/v1/ymm -d key=$CARSXE_API_KEY -d year=2012 -d make=BMW -d model=5-Series
```

#### Plate Image Recognition (POST)
Extract a license plate number from an image URL.
```bash
curl -X POST "https://api.carsxe.com/platerecognition?key=$CARSXE_API_KEY" \
  -H "Content-Type: application/json" \
  -d '{"image_url": "https://imagedelivery.net/moyiiSImjJPI_EZVxNMBBw/f49aed53-d736-4370-f3f4-97418841c800/public"}'
```

#### VIN OCR (POST)
Extract a VIN from a photo of a VIN plate or dashboard sticker.
```bash
curl -X POST "https://api.carsxe.com/v1/vinocr?key=$CARSXE_API_KEY" \
  -H "Content-Type: application/json" \
  -d '{"image_url": "https://user-images.githubusercontent.com/5663423/30922082-64edb4fa-a3a8-11e7-873e-3fbcdce8ea3a.png"}'
```

#### OBD Codes Decoder
Decode a diagnostic trouble code (DTC) from an OBD-II scanner. 3,000+ codes supported.
```bash
curl -G https://api.carsxe.com/obdcodesdecoder -d key=$CARSXE_API_KEY -d code=P0300
```

---

## Option 2 — `@carsxe/cli` (recommended for coding agents)

Coding agents can call any CarsXE endpoint as a subprocess with structured JSON output and reliable exit codes.

### Setup

```bash
npm install -g @carsxe/cli
carsxe login
```

Use `--raw` for compact single-line JSON pipeable to `jq`, or `--table` for a human-friendly view. Run `carsxe <command> --help` to see all flags for any command.

### Available Endpoints

#### Vehicle Specifications (VIN Decode)
Decode a VIN — make, model, year, engine, trim, equipment, and more.
```bash
carsxe specs --vin 1HGBH41JXMN109186
```

#### Market Value
Retail, trade-in, and auction values. Optional: `--mileage`, `--state`, `--condition` (excellent/clean/average/rough).
```bash
carsxe market-value --vin 1HGBH41JXMN109186 --mileage 45000 --state CA --condition clean
```

#### Vehicle History
Title records, junk/salvage events, and insurance history by VIN.
```bash
carsxe history --vin 1HGBH41JXMN109186
```

#### Vehicle Recalls
Open NHTSA safety recalls by VIN.
```bash
carsxe recalls --vin 1HGBH41JXMN109186
```

#### Lien & Theft Check
Active liens and theft records by VIN.
```bash
carsxe lien-theft --vin 1HGBH41JXMN109186
```

#### Plate Decoder
Look up a vehicle by license plate. Supports 50+ countries. `--state` required for US, AU, CA.
```bash
carsxe plate-decoder --plate 7XER187 --country US --state CA
```

#### International VIN Decoder
Decode a non-US VIN (Europe, Asia, and other markets).
```bash
carsxe international-vin --vin WBAFR7C57CC811956
```

#### Vehicle Images
Photos by make, model, year. Optional: `--color`, `--angle` (front/side/back), `--photo-type` (interior/exterior/engine), `--size` (Small/Medium/Large/Wallpaper/All).
```bash
carsxe images --make BMW --model 5-Series --year 2012
```

#### Year / Make / Model
Look up vehicle data without a VIN. Optional: `--trim`.
```bash
carsxe ymm --year 2012 --make BMW --model 5-Series
```

#### Plate Image Recognition
Extract a license plate number from an image URL.
```bash
carsxe plate-image --image https://example.com/car-photo.jpg
```

#### VIN OCR
Extract a VIN from a photo of a VIN plate or dashboard sticker.
```bash
carsxe vin-ocr --image https://example.com/vin-sticker.jpg
```

#### OBD Codes Decoder
Decode a diagnostic trouble code (DTC) from an OBD-II scanner. 3,000+ codes supported.
```bash
carsxe obd --code P0300
```

---

Full API docs: https://carsxe.com/docs
