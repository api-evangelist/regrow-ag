---
name: regrow-ag-intervention-project
description: 'Run a Measure API Intervention project: pick a protocol, create the project, upload fields, finalize, then read scope 1 and scope 3 results.'
api: openapi/regrow-ag-measure-api-openapi.yml
spec: openapi/regrow-ag-measure-api-openapi.yml
operations:
- list_protocols_v0_api_protocols_get
- create_project_v0_api_projects_post
- upload_field_v0_api_projects__project_name__fields_post
- list_fields_v0_api_projects__project_name__fields_get
- finalize_project_v0_api_projects__project_name__finalize_post
- scope_1_results_v0_api_project_level_scope_1_get
- scope_3_results_v0_api_project_level_scope_3_get
generated: '2026-10-18'
method: generated
---

# regrow-ag-intervention-project

Run a Measure API Intervention project: pick a protocol, create the project, upload fields, finalize, then read scope 1 and scope 3 results.

## Steps
1. `GET /v0/api/protocols` (list_protocols_v0_api_protocols_get): List Protocols
2. `POST /v0/api/projects` (create_project_v0_api_projects_post): Create Project
3. `POST /v0/api/projects/{project_name}/fields` (upload_field_v0_api_projects__project_name__fields_post): Upload Field
4. `GET /v0/api/projects/{project_name}/fields` (list_fields_v0_api_projects__project_name__fields_get): List Fields
5. `POST /v0/api/projects/{project_name}/finalize` (finalize_project_v0_api_projects__project_name__finalize_post): Finalize Project
6. `GET /v0/api/project_level_scope_1` (scope_1_results_v0_api_project_level_scope_1_get): Scope 1 Results
7. `GET /v0/api/project_level_scope_3` (scope_3_results_v0_api_project_level_scope_3_get): Scope 3 Results

## Rules
- Send the `x-apikey` header on every request. Keys come from Regrow Support (support@regrow.ag).
- Processing is asynchronous: poll the status or job operation until it completes, then read the results.
- The spec documents no idempotency keys, so do not blindly retry a POST that creates a project or uploads a field; list first to check whether it already exists.
- DELETE operations are destructive. Run them only when the user explicitly asks.
- Expect 401 for an invalid key and 422 for a validation error (FastAPI-style detail body).
