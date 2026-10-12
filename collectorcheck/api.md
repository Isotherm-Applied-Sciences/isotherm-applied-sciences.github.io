---
title: CollectorCheck API
description: Deterministic API for receipt verification and provenance continuity.
---

# CollectorCheck API

The CollectorCheck API provides deterministic, transparent endpoints for receipt ingestion, verification, and continuity record generation.

---

## v1 API (Current Implementation)

These endpoints are implemented in the public CollectorCheck repository.

### 1. Verify Receipt

```http
POST /verify
```

Uploads a receipt and returns a verification result.

**Returns:**
- authenticity result
- parsed metadata
- verification output

### 2. Health Check

```http
GET /status
```

Returns backend health.

### 3. Version

```http
GET /version
```

Returns the current CollectorCheck version.

---

## v2 API (Planned Deterministic Interface)

The following endpoints define the future Isotherm continuity-stack API.

### Base URL

```text
/api/v1
```

### 1. Upload Receipt

```http
POST /api/v1/receipts/upload
```

Uploads a receipt image or PDF for verification.

### 2. Verify Receipt

```http
POST /api/v1/receipts/verify
```

Runs deterministic verification logic on a previously uploaded receipt.

### 3. Get Continuity Record

```http
GET /api/v1/continuity/{record_id}
```

Retrieves a deterministic continuity record.

### 4. Health Check

```http
GET /api/v1/health
```

Returns system health and deterministic status.

---

## Deterministic Behavior

All endpoints behave deterministically:

- Same input → same output
- No hidden heuristics
- No cloud dependencies
- Fully auditable logic

---

## Status

This API specification defines both the current v1 interface and the planned v2 deterministic interface for CollectorCheck.
