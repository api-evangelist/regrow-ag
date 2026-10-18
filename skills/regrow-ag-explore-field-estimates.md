---
name: regrow-ag-explore-field-estimates
description: Upload a field to the Explore API, poll its status, and fetch baseline and modeled GHG estimates.
api: openapi/regrow-ag-measure-api-openapi.yml
spec: openapi/regrow-ag-measure-api-openapi.yml
operations:
- upload_field_v0_explore_api_fields_post
- get_status_v0_explore_api_fields__field_request_id__status_get
- get_estimates_v0_explore_api_fields__field_request_id__results_get
- list_fields_v0_explore_api_fields_get
generated: '2026-10-18'
method: generated
---

# regrow-ag-explore-field-estimates

Upload a field to the Explore API, poll its status, and fetch baseline and modeled GHG estimates.

## Steps
1. `POST /v0/explore_api/fields` (upload_field_v0_explore_api_fields_post): Upload Field
2. `GET /v0/explore_api/fields/{field_request_id}/status` (get_status_v0_explore_api_fields__field_request_id__status_get): Get Status
3. `GET /v0/explore_api/fields/{field_request_id}/results` (get_estimates_v0_explore_api_fields__field_request_id__results_get): Get Estimates
4. `GET /v0/explore_api/fields` (list_fields_v0_explore_api_fields_get): List Fields

## Rules
- Send the `x-apikey` header on every request. Keys come from Regrow Support (support@regrow.ag).
- Processing is asynchronous: poll the status or job operation until it completes, then read the results.
- The spec documents no idempotency keys, so do not blindly retry a POST that creates a project or uploads a field; list first to check whether it already exists.
- DELETE operations are destructive. Run them only when the user explicitly asks.
- Expect 401 for an invalid key and 422 for a validation error (FastAPI-style detail body).
