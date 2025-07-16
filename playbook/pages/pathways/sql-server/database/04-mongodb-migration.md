# MongoDB Migration

This step covers the process of migrating from a relational database schema to MongoDB using AI assistance. This involves designing a document-oriented schema and documenting the mapping of relational data to MongoDB documents.

## MongoDB Schema Design Process

MongoDB schemas (like all NoSQL databases) should be designed around how your application accesses data. Designing a MongoDB schema has a significant impact on how your application performs and scales. This is why the system documentation phase is critical before starting the migration, as it helps you and AI tools understand the data access patterns and relationships in your application.

<pre class="mermaid">
flowchart TD
    START["🗄️ MongoDB Migration"] --> A["📋 Identify Core Business Entities"]
    A --> B["🎯🤖 Select Next Table"]
    B --> C["🤖🧑‍💻 Generate MongoDB Schema for Table"]
    C --> D{"🧑‍💻 Schema Appropriate?"}
    D -->|No| E["🔄🤖🧑‍💻 Refine Schema Design"]
    D -->|Yes| F{"🧑‍💻 More Tables?"}
    E --> C
    F -->|Yes| B
    F -->|No| G["📊🤖🧑‍💻 Generate Complete ERD"]

    classDef title fill:#f3e5f5,stroke:#7b1fa2,stroke-width:3px,font-weight:bold
    classDef human fill:#ffeb3b,stroke:#f57f17,stroke-width:2px
    classDef hybrid fill:#e8f5e8,stroke:#2e7d32,stroke-width:2px
    classDef decision fill:#fff3e0,stroke:#f57c00,stroke-width:2px

    class START title
    class A human
    class B,C,E,G hybrid
    class D,F decision
</pre>

### Key Phases

MongoDB migration consists of two key phases that can be covered in the same prompt:

1. **Design MongoDB Schema**: Create a document structure that optimizes for your application's data access patterns
2. **SQL to Mongo Data Mapping**: Document how relational tables, relationships, and data types will translate to MongoDB documents

### Prerequisites

- **Capable model**: We recommend using a large language model (LLM) with a large context window for this step. The Liquibase changelog being used for context will likely be very large.
- **MongoDB ERD Creation Prompt**: Use the [MongoDB ERD Creation Prompt](../../../appendix/prompt-library/sql-server/mongodb-schema-creation.md) to guide the AI in designing the MongoDB schema, table by table, based on the Liquibase changelog and system documentation.

### Step-by-Step Process

1. **Identify Core Business Entities**
   - You should be able to do this without AI assistance using the gathered documentation from the previous phase
   - Make a list of the core business entities
   - You don't need to capture the columns and relations - the Liquibase changelog will provide enough context for the AI tool

2. **Generate Schema for Each Table**
   - Using the [MongoDB ERD Creation Prompt](../../../appendix/prompt-library/sql-server/mongodb-schema-creation.md), edit the prompt to reference the specific table
   - The AI tool will use the changelog for context and suggest whether:
     - A new document/collection type is required
     - An embedded document in an existing collection
     - Separate collection with cache reference (in case of lookups)

3. **Iterate Through All Tables**
   - Repeat the schema generation process for each table until all are covered
   - Validate each schema design before moving to the next table

4. **Generate Complete ERD**
   - Once all tables are processed, generate a comprehensive Entity Relationship Diagram
   - Review the ERD to ensure it meets all requirements and optimizes for your application's data access patterns

## Guidelines

**Keep your prompt focused**: We have found that processing one table at a time gets better results from the AI due to the smaller context load. It also allows for more robust human-in-the loop verification and better suggest tweaks and improvements.

---

[← Previous: MongoDB Decision Point](03-mongodb-decision-point) | [Next: Generate OpenAPI Specification →](../api/openapi-specification)
