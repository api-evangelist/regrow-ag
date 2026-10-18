---
name: regrow-ag-enteric-project-management
description: Create and manage an enteric project with ranchers for measurement calculations.
api: openapi/regrow-ag-measure-api-openapi.yml
operations:
- v1_create_project_v1_enteric_projects_post
- upload_rancher_v1_enteric_projects__project_name__ranchers_post
- list_ranchers_v1_enteric_projects__project_name__ranchers_get
- finalize_project_v1_enteric_projects__project_name__finalize_post
- v1_get_results_v1_enteric_projects__project_name__get
generated: '2026-10-18'
method: generated
generator: extract-docs-artifacts.py skills (deepseek)
source: openapi/regrow-ag-measure-api-openapi.yml ; every operationId checked against the contract
---

# regrow-ag-enteric-project-management

Create and manage an enteric project with ranchers for measurement calculations.

## Steps

1. 1. Create a new project using `v1_create_project_v1_enteric_projects_post` with the required project fields
2. 2. Upload ranchers to the project using `upload_rancher_v1_enteric_projects__project_name__ranchers_post` with rancher data and the project_name path parameter
3. 3. List ranchers in the project using `list_ranchers_v1_enteric_projects__project_name__ranchers_get` with the project_name path parameter
4. 4. Finalize the project using `finalize_project_v1_enteric_projects__project_name__finalize_post` with the project_name path parameter
5. 5. Get project results using `v1_get_results_v1_enteric_projects__project_name__get` with the project_name path parameter

## Rules

- Authentication header required for all API calls
- Use project_name path parameter for project-specific operations
- Follow proper sequence: create project → add ranchers → finalize → get results
