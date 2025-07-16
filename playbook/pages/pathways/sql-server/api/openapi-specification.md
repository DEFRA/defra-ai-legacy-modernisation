# OpenAPI Specification Generation Process

Creating comprehensive API documentation is a critical step in modernising SQL Server applications. This documentation-first approach ensures that API contracts are well-defined before implementation begins, 

<pre class="mermaid">
flowchart TD
    A["📊 Migrated Database Schema"] --> B["🔍 Identify Business Operations"]
    B --> C["📋 Define API Endpoints"]
    C --> D["🤖 Generate OpenAPI Specification"]
    D --> E["✅ Validate with SMEs"]
    E --> F{"Specification Complete?"}
    F -->|No| G["🔄 Refine Specification"]
    F -->|Yes| H["📚 Generate API Documentation"]
    G --> D
    H --> I["🪄 Begin API Implementation"]

    classDef database fill:#e8f5e8,stroke:#2e7d32,stroke-width:2px
    classDef process fill:#e3f2fd,stroke:#1976d2,stroke-width:2px
    classDef ai fill:#fff3e0,stroke:#f57c00,stroke-width:2px
    classDef decision fill:#ffeb3b,stroke:#f57f17,stroke-width:2px
    classDef documentation fill:#f3e5f5,stroke:#7b1fa2,stroke-width:2px

    class A database
    class B,C,G process
    class D,H ai
    class E,F decision
    class I documentation
</pre>

## Why Documentation-First?

Continuing with the documentation-first approach this playbook takes, the documentation-first approach to API development offers several advantages for any modernisation project, including:

- **Clear Communication**: Provides a shared understanding between stakeholders, developers, and SMEs
- **Early Validation**: Identifies potential issues before implementation begins
- **Parallel Development**: Enables frontend and backend teams to work simultaneously
- **Better Testing**: Facilitates comprehensive test planning and mock implementation
- **Reduced Rework**: Minimises changes required during development phases
- **Better Context for AI**: Provides a clear contract for AI tools to assist in generating code and further documentation

## Key Activities

### 1. Identify Business Operations

Before generating API specifications, ensure you and your AI tool understand the core business operations that the API will need to support.

### 2. Define API Endpoints

Structure your API endpoints around business capabilities rather than database tables. Consider these patterns:

**Resource-Based Endpoints**:
```
GET    /api/customers           # List customers
POST   /api/customers           # Create customer
GET    /api/customers/{id}      # Get specific customer
PUT    /api/customers/{id}      # Update customer
DELETE /api/customers/{id}      # Delete customer
```

**Action-Based Endpoints**:
```
POST   /api/orders/{id}/process    # Process an order
POST   /api/customers/{id}/archive # Archive a customer
GET    /api/reports/sales/monthly  # Generate monthly sales report
```

You can also use AI tools to help process existing documentation and user stories to identify the necessary endpoints.

### 3. Generate OpenAPI Specification with AI

Use AI tools to quickly generate OpenAPI specifications based on your system documentation and business requirements.

For detailed guidance on creating comprehensive OpenAPI specifications with AI, see the [OpenAPI Generation Prompt](../../../appendix/prompt-library/general/openapi-generation) in the prompt library.

### 4. Validate with Subject Matter Experts

Review the generated specification with SMEs to ensure it meets business requirements. This SME will typically be a developer who understands the system's business logic and user needs.

**Validation Checklist**:
- ✅ All critical business operations are represented
- ✅ Data models match business entity relationships
- ✅ API flows support existing user workflows  
- ✅ Security requirements are appropriately addressed
- ✅ Error handling covers expected failure scenarios
- ✅ Performance requirements are considered
- ✅ Response formats are clear and consistent

### 5. Refine and Iterate

Based on SME feedback, refine the specification using AI assistance:

**Common Refinements**:
- **Missing Endpoints**: Add operations identified during SME review
- **Data Relationships**: Adjust schemas to reflect business entity relationships
- **Business Rules**: Incorporate validation rules and constraints
- **Workflow Support**: Ensure API supports complete business processes
- **Error Handling**: Add specific error responses for business exceptions

## Common Challenges

**Challenge**: Including database schema context can lead AI tools to generate APIs too closely tied to the database structure rather than business operations.
**Solution**: When prompting AI tools, focus on business operations and workflows rather than database tables. Use examples of user journeys to guide API design. It is better to only include the database schema context when implementing the API, not when generating the OpenAPI specification.

## Next Steps

Once the OpenAPI specification is complete and validated:

1. **Generate Mock APIs**: Create mock implementations for frontend development
2. **Begin API Implementation**: Start building the actual API using the specification
3. **Setup API Testing**: Implement automated testing based on the specification

---

[← Previous: Database Migration](../,) | [Next: API Implementation →](../api/.)

*This page is part of the DEFRA AI Legacy Modernisation Playbook.*
