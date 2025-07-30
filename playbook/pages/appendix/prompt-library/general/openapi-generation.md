# OpenAPI Generation

This prompt can be used to generate a OpenAPI 3.1.0 specification document based on user stories and system requirements identified during the discovery-analysis phase.

```
# Context

Suggest and add endpoints to a OpenAPI 3.1.0 specification that would allow the implementation of the referenced user story. You have been provided with the following:
- #file:documentation - System documentation to provide domain / business entity context
- #file:user_story - Contains the current user story being implemented
- #file:openapi.yaml - Contains the current OpenAPI specification. Create this if it does not exist.

## Analysis Phase

You should analyse the user story to identify:
- The business entity or domain entity that the user story relates to
- The data fields and attributes that are required to implement the user story
- Any relationships with other entities that need to be considered
- The data access patterns and how this entity would be accessed within business processes

After analysing the user story and understanding the requirements, you should review the documentation and existing OpenAPI specification to identify:
- Any existing endpoints that can be reused or extended
- Any new endpoints that need to be created to support the user story
- Any changes to existing endpoints that are required to support the user story
- Any additional data fields or attributes that need to be added to the OpenAPI specification
- Any changes to the data types, constraints, or business rules that need to be reflected in the OpenAPI specification

At this stage, you should output a summary of the analysis, including:
- The core business entity(s) that the user story relates to
- Your suggested endpoints and their purpose 
  - For each endpoint, include:
    - HTTP method (GET, POST, PUT, DELETE)
    - Endpoint path
    - Description of the endpoint's purpose
    - Input parameters and their types
    - Output response structure and types
- Data schemas that will need to be defined in the OpenAPI specification (including responses and request bodies)
- Any additional notes on indexing, performance considerations, or specific OpenAPI features that should be used

## Implementation Phase
Using the analysis, you should add these endpoints and their schemas to the OpenAPI specification in `openapi.yaml` or create a new OpenAPI specification if it does not exist.

You may fetch the OpenAPI 3.1.0 specification from https://spec.openapis.org/oas/v3.1.0.html.

The specification MUST follow these standards:
- Use OpenAPI 3.1.0 YAML format
- Use camelCase for field names throughout the specification
- Use PascalCase for schema names
- Use kebab-case for folder and file names
- Use plural nouns for resource names (e.g., `users`, `orders`)

To reduce cognitive load, you should split the OpenAPI specification into a structured format that allows for easy navigation and understanding. The structure should follow the conventions of OpenAPI 3.1.0 and be organized by version and resource.

You should split the OpenAPI specification into the following structure:

api/
  ├── v{ersion}/
  │   ├── resources/
  │   │   ├── {resource-name}.yaml
  |   ├── schemas/
  │   │   ├── {schema-name}.yaml
  │   ├── openapi.yaml


The `openapi.yaml` file should contain the main OpenAPI specification, including metadata, versioning, and references to the resource and schema files. See the following example for the structure of the `openapi.yaml` file:
```yaml
openapi: "3.1.0"
info:
  title: Todo Application API
  description: API for managing tasks in a Todo application
  version: 1.0.0

servers:
  - url: https://{host}:{port}
    description: API server
    variables:
      host:
        default: "localhost"
      port:
        default: "3001"

paths:
  /tasks:
    $ref: './resources/tasks.yaml'

components:
  schemas:
    $ref: './schema/_index.yaml'
```

---

[← Previous: Prompt Library](../.)
