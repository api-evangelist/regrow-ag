---
name: regrow-ag-upload-field-and-retrieve-estimates
description: Upload a field for analysis and retrieve the resulting estimates from the Regrow Ag DNDC scenarios service.
api: openapi/regrow-ag-measure-api-openapi.yml
operations:
- upload_field_v0_explore_api_fields_post
- get_status_v0_explore_api_fields__field_request_id__status_get
- get_raw_input_v0_v0_explore_api_fields__field_request_id__get
- get_estimates_v0_explore_api_fields__field_request_id__results_get
generated: '2026-10-18'
method: generated
generator: extract-docs-artifacts.py skills (deepseek)
source: openapi/regrow-ag-measure-api-openapi.yml ; every operationId checked against the contract
---

# regrow-ag-upload-field-and-retrieve-estimates

Upload a field for analysis and retrieve the resulting estimates from the Regrow Ag DNDC scenarios service.

## Steps

1. 1. Upload field data using `upload_field_v0_explore_api_fields_post` with the required field information in the request body
2. 2. Check processing status using `get_status_v0_explore_api_fields__field_request_id__status_get` with the `field_request_id` from the upload response
3. 3. Retrieve raw input data using `get_raw_input_v0_v0_explore_api_fields__field_request_id__get` with the `field_request_id` to verify uploaded data
4. 4. Get final estimates using `get_estimates_v0_explore_api_fields__field_request_id__results_get` with the `field_request_id` once processing is complete

## Rules

- Authentication header required for all API calls
- Use `field_request_id` from upload response for subsequent operations
- Check status endpoint before retrieving results to ensure processing is complete
