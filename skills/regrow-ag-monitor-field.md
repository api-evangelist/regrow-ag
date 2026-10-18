---
name: regrow-ag-monitor-field
description: Submit a Monitor API job for a field (GeoJSON or boundary ID), poll the job, and fetch crop and practice results.
api: openapi/regrow-ag-monitor-api-openapi.yml
spec: openapi/regrow-ag-monitor-api-openapi.yml
operations:
- health_check_status_get
- Monitor_Field_Geojson_processes_monitor_fields_geojson_execution_post
- Monitor_Field_processes_monitor_fields_boundary_id_execution_post
- get_job_status_jobs__job_id__get
- get_job_results_jobs__job_id__results_get
generated: '2026-10-18'
method: generated
---

# regrow-ag-monitor-field

Submit a Monitor API job for a field (GeoJSON or boundary ID), poll the job, and fetch crop and practice results.

## Steps
1. `GET /status` (health_check_status_get): Health Check
2. `POST /processes/monitor-fields-geojson/execution` (Monitor_Field_Geojson_processes_monitor_fields_geojson_execution_post): Monitor Field Geojson
3. `POST /processes/monitor-fields-boundary-id/execution` (Monitor_Field_processes_monitor_fields_boundary_id_execution_post): Monitor Field
4. `GET /jobs/{job_id}` (get_job_status_jobs__job_id__get): Get Job Status
5. `GET /jobs/{job_id}/results` (get_job_results_jobs__job_id__results_get): Get Job Results

## Rules
- Send the `x-apikey` header on every request. Keys come from Regrow Support (support@regrow.ag).
- Processing is asynchronous: poll the status or job operation until it completes, then read the results.
- The spec documents no idempotency keys, so do not blindly retry a POST that creates a project or uploads a field; list first to check whether it already exists.
- DELETE operations are destructive. Run them only when the user explicitly asks.
- Expect 401 for an invalid key and 422 for a validation error (FastAPI-style detail body).
