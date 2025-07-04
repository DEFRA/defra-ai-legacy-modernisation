# OpenAPI Generation

This prompt can be used to generate a comprehensive OpenAPI 3.1.1 specification document based on user stories and system requirements identified during the discovery-analysis phase.

```
# Context

Create a comprehensive OpenAPI 3.1.1 specification document by analyzing user stories and system requirements. The document should provide complete API documentation that enables developers and API consumers to understand and interact with all available endpoints effectively.

## Analysis Phase

### 1. User Story and Requirement Analysis

- **Scope**: Review all user stories and system requirements identified during the discovery-analysis phase
- **Location**: Analyze documentation and artifacts generated in the discovery-analysis phase, including:
  - Functional requirements
  - Non-functional requirements
  - Any additional user story modules
- **Method Coverage**: Document all HTTP methods (GET, POST, PUT, DELETE, PATCH) for each endpoint
- **Route Parameters**: Capture path parameters, query parameters, and request body schemas

### 2. OpenAPI Specification Compliance

- **Version**: Use OpenAPI Specification v3.1.1 exactly as defined at: https://spec.openapis.org/oas/v3.1.1.html
- **Validation**: Ensure the document validates against the official OpenAPI 3.1.1 JSON Schema
- **Standards Compliance**: Follow all MUST, SHOULD, and RECOMMENDED practices from the specification

### 3. Data Model Analysis

- **Request/Response Schemas**: Extract and document all data structures from user stories and requirements
- **Validation Rules**: Include parameter validation, required fields, data types, and constraints
- **Error Responses**: Document all possible error responses with appropriate HTTP status codes
- **Examples**: Provide realistic example requests and responses for each endpoint

## Implementation Specifications

### 1. Document Structure

```yaml
openapi: 3.1.1
info:
  title: API Specification
  description: |
    Comprehensive REST API documentation based on user stories and system requirements.
    Provides endpoints for managing data and operations as defined in the discovery-analysis phase.
  version: 1.0.0
  contact:
    name: API Support Team
  license:
    name: MIT

servers:
  - url: /api/v1
    description: Version 1 API Base URL
```
### 2. Required Components

- **Security Schemes**: Document authentication/authorization if required by a user story
- **Reusable Schemas**: Create components for common data structures
- **Response Models**: Define standard response formats and error schemas
- **Parameter Objects**: Reusable parameter definitions for common query params

### 3. Endpoint Documentation Standards

- **Operation IDs**: Unique, descriptive operation identifiers for each endpoint
- **Tags**: Logical grouping of endpoints based on user stories and requirements
- **Descriptions**: Clear, comprehensive descriptions for all operations
- **Parameter Documentation**: Complete documentation for all parameters including:
  - Type definitions
  - Validation constraints
  - Default values
  - Examples
- **Response Documentation**: All possible responses with:
  - HTTP status codes
  - Response schemas
  - Example payloads

### 4. Advanced Features
- **Request/Response Examples**: Multiple realistic examples for complex operations
- **Schema Validation**: Proper JSON Schema constraints and validation rules
- **Media Type Support**: Document all supported content types
- **Error Handling**: Comprehensive error response documentation
## Quality Assurance & Evaluation

### 1. Specification Validation
- **Schema Compliance**: Validate against OpenAPI 3.1.1 specification
- **Syntax Validation**: Ensure valid YAML syntax and structure
- **Reference Validation**: Verify all $ref references resolve correctly
- **Example Validation**: Ensure all examples validate against their schemas

### 2. Completeness Verification
- **Endpoint Coverage**: Confirm all endpoints derived from user stories are documented
- **HTTP Method Coverage**: Verify all supported HTTP methods are included
- **Parameter Coverage**: Ensure all parameters are documented with proper types
- **Response Coverage**: Document all possible response scenarios

### 3. Documentation Quality
- **Clarity**: Descriptions should be clear and comprehensive
- **Consistency**: Use consistent naming conventions and patterns
- **Usability**: Documentation should enable easy API consumption
- **Maintainability**: Structure should support easy updates and modifications

### 4. Testing Integration
- **Mock Server Compatibility**: Document should support API mocking tools
- **Code Generation**: Structure should enable client SDK generation
- **API Testing**: Support integration with API testing frameworks

## Implementation Process

### Phase 1: Discovery and Analysis
1. **Requirement Discovery**: Systematically analyze all user stories and requirements
2. **Handler Analysis**: Review all functional and non-functional requirements to understand request/response patterns
3. **Schema Extraction**: Extract data models from requirements and validation schemas
4. **Error Mapping**: Document all error scenarios and HTTP status codes

### Phase 2: OpenAPI Document Creation
1. **Basic Structure**: Create the foundational OpenAPI document structure
2. **Path Documentation**: Document each endpoint with complete operation details
3. **Schema Definition**: Create reusable schema components
4. **Example Generation**: Add comprehensive examples for all operations

### Phase 3: Validation and Refinement
1. **Specification Validation**: Validate against OpenAPI 3.1.1 schema
2. **Completeness Review**: Ensure all endpoints and operations are covered
3. **Quality Check**: Review for clarity, consistency, and usability
```

---

[← Previous: Prompt Library](../README)
