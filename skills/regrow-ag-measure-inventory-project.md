---
name: regrow-ag-measure-inventory-project
description: Create a project, upload fields to it, and finalize the project to get inventory results.
api: openapi/regrow-ag-measure-api-openapi.yml
operations:
- create_project_v0_inventory_projects_post
- upload_field_v0_inventory_projects__project_name__fields_post
- finalize_project_v0_inventory_projects__project_name__finalize_post
- get_results_v0_inventory_projects__project_name__get
generated: '2026-10-18'
method: generated
generator: extract-docs-artifacts.py skills (deepseek)
source: openapi/regrow-ag-measure-api-openapi.yml ; every operationId checked against the contract
---

# regrow-ag-measure-inventory-project

Create a project, upload fields to it, and finalize the project to get inventory results.

## Steps

1. 1. Create a project using `create_project_v0_inventory_projects_post` with the required fields in the request body
2. 2. Upload fields to the project using `upload_field_v0_inventory_projects__project_name__fields_post` with the project_name path parameter and field data in the request body
3. 3. Finalize the project using `finalize_project_v0_inventory_projects__project_name__finalize_post` with the project_name path parameter
4. 4. Get the inventory results using `get_results_v0_inventory_projects__project_name__get` with the project_name path parameter

## Rules

- Authentication header required for all API calls
- Use the project_name path parameter to reference specific projects
- Check for errors in the response before proceeding to next steps
