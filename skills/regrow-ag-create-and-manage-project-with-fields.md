---
name: regrow-ag-create-and-manage-project-with-fields
description: Create a new agricultural project, upload field data, and manage the project lifecycle through the Regrow API.
api: openapi/regrow-ag-measure-api-openapi.yml
operations:
- create_project_v0_api_projects_post
- upload_field_v0_api_projects__project_name__fields_post
- list_fields_v0_api_projects__project_name__fields_get
- finalize_project_v0_api_projects__project_name__finalize_post
generated: '2026-10-18'
method: generated
generator: extract-docs-artifacts.py skills (deepseek)
source: openapi/regrow-ag-measure-api-openapi.yml ; every operationId checked against the contract
---

# regrow-ag-create-and-manage-project-with-fields

Create a new agricultural project, upload field data, and manage the project lifecycle through the Regrow API.

## Steps

1. 1. Create a new project using `create_project_v0_api_projects_post` with required fields like `project_name` and `protocol_name`
2. 2. Upload field data to the project using `upload_field_v0_api_projects__project_name__fields_post` with the `project_name` path parameter and field data in the request body
3. 3. List all fields in the project using `list_fields_v0_api_projects__project_name__fields_get` with the `project_name` path parameter
4. 4. Finalize the project using `finalize_project_v0_api_projects__project_name__finalize_post` with the `project_name` path parameter

## Rules

- Authentication header required for all API calls
- Use pagination parameters when listing resources
- Handle errors according to HTTP status codes and response bodies
