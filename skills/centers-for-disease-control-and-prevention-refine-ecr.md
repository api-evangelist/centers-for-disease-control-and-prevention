---
name: Build and test an eCR Refiner configuration
description: Create a reportable-condition configuration in the DIBBs eCR Refiner, rehearse it against a sample eCR, then activate it — using only operations declared in CDC's published OpenAPI.
api: openapi/centers-for-disease-control-and-prevention-dibbs-ecr-refiner-openapi.json
operations: [getConditions, createConfiguration, associateConditionWithConfiguration, addCustomCodeToConfiguration, validateCustomCodeFromConfiguration, runInlineConfigurationTest, uploadEcr, discoverConfigurations, activateConfiguration, deactivateConfiguration, acquireConfigurationLock, releaseConfigurationLock]
generated: '2026-09-05'
method: generated
---

# Build and test an eCR Refiner configuration

The DIBBs eCR Refiner reduces eICR and Reportability Response documents to the data a given
reportable condition actually needs. It is a **self-hosted** CDC product (Apache-2.0,
`ghcr.io/cdcgov/dibbs-ecr-refiner`, release 1.0.0 on 2026-09-04) — there is no CDC-operated
endpoint, so the base URL is whatever your jurisdiction deployed. Every operationId below is
verbatim from CDC's own spec.

## 1. Pick the condition

`getConditions` — `GET /api/v1/conditions/`. Then `getCondition` — `GET /api/v1/conditions/{condition_id}`
for its code sets and completeness status.

## 2. Create a configuration

`createConfiguration` — `POST /api/v1/configurations/` with the `condition_id`.

**There is no idempotency key on this API.** A retried POST creates a second configuration. If a
call times out, list with `getConfigurations` before retrying.

## 3. Take the lock before editing

`acquireConfigurationLock` — `POST /api/v1/configurations/{configuration_id}/acquire-lock`.
Release it with `releaseConfigurationLock` when you are done. A configuration carries a
`LockedByUser`, so concurrent edits are a real failure mode here.

## 4. Shape it

- `associateConditionWithConfiguration` — `PUT .../code-sets`; reverse with
  `disassociateConditionWithConfiguration` (`DELETE .../code-sets/{condition_id}`).
- `addCustomCodeToConfiguration` — `POST .../custom-codes`; reverse with
  `deleteCustomCodeFromConfiguration`.
- Bulk: `uploadCustomCodesCsv` then `confirmUploadCustomCodesCsv` — a two-phase upload, so
  inspect the preview before confirming. `deleteCustomCodes` (bulk-delete) has **no** reversal.
- Sections: `addCustomSection`, `updateSection`, `deleteCustomSection`.

## 5. Rehearse before you activate

- `validateCustomCodeFromConfiguration` — `POST .../custom-codes/validate`, checks one code.
- `runInlineConfigurationTest` — `POST /api/v1/configurations/test`, runs the configuration
  without activating it.
- `uploadEcr` — `POST /api/v1/simulator/upload`, and `discoverConfigurations` —
  `POST /api/v1/simulator/discover-configurations`, to see which configurations a real eCR would
  match.

Use CDC's own synthetic corpus for this: https://github.com/CDCgov/dibbs-star-wars-ecr-data.
Never rehearse with live patient documents.

## 6. Activate, and know how to undo

`activateConfiguration` — `PATCH .../activate`. It is reversible with `deactivateConfiguration`
— but **CDC publishes no window** for that reversal, so do not promise the user one.

## 7. Errors

37 of the 44 operations declare a **422** carrying FastAPI's `HTTPValidationError`:
`{"detail":[{"loc":[…],"msg":"…","type":"…"}]}`. Correct the field named in `detail[].loc`.
Nothing on this API is RFC 9457.
