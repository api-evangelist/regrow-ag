---
name: regrow-ag-monitor-field-and-retrieve-results
description: Monitor a field using boundary ID or GeoJSON and retrieve job status and results
api: openapi/regrow-ag-monitor-api-openapi.yml
operations:
- Monitor_Field_processes_monitor_fields_boundary_id_execution_post
- Monitor_Field_Geojson_processes_monitor_fields_geojson_execution_post
- get_job_status_jobs__job_id__get
- get_job_results_jobs__job_id__results_get
generated: '2026-10-18'
method: generated
generator: extract-docs-artifacts.py skills (deepseek)
source: openapi/regrow-ag-monitor-api-openapi.yml ; every operationId checked against the contract
---

# regrow-ag-monitor-field-and-retrieve-results

Monitor a field using boundary ID or GeoJSON and retrieve job status and results

## Steps

1. 1. Submit a field monitoring job using `Monitor_Field_processes_monitor_fields_boundary_id_execution_post` with boundary_id parameter or `Monitor_Field_Geojson_processes_monitor_fields_geojson_execution_post` with GeoJSON data
2. 2. Check job status using `get_job_status_jobs__job_id__get` with the job_id path parameter
3. 3. Retrieve job results using `get_job_results_jobs__job_id__results_get` with the job_id path parameter

## Rules

- Authentication headers are required as indicated by the servers requiring HTTPS
- Job status and results operations are idempotent GET requests
- Error handling for job processing failures should be implemented
