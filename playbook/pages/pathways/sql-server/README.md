# SQL Server Migration Pathway

This pathway provides comprehensive guidance for migrating SQL Server databases to open-source databases like PostgreSQL, and optionally to MongoDB using AI assistance.

## Overview

SQL Server modernisation typically involves database migration and API development that can be approached in phases:

1. **Database Migration**: Transform SQL Server to modern database platforms
3. **Optional: MongoDB Migration**: Migrate to MongoDB if feasible
2. **API Development**: Create modern APIs from migrated database structures

<pre class="mermaid">
graph TD
    A[SQL Server Database] --> B[Schema Extraction]
    B --> C[Refactor and Deploy Liquibase Changelog]
    C --> E{MongoDB?}
    E -->|Migrate| F[Design MongoDB Schema]
    F --> G[SQL to Mongo Data Mapping]
    G --> H[Generate OpenAPI Specification]
    E -->|Stick with RDBMS| H
    H --> I["🪄 Develop Backend API"]

    classDef database fill:#e8f5e8,stroke:#2e7d32,stroke-width:2px
    classDef process fill:#e3f2fd,stroke:#1976d2,stroke-width:2px
    classDef mongodb fill:#f3e5f5,stroke:#7b1fa2,stroke-width:2px
    classDef decision fill:#fff3e0,stroke:#f57c00,stroke-width:2px
    classDef api fill:#e8f5e8,stroke:#2e7d32,stroke-width:2px

    class A database
    class B,C process
    class F,G mongodb
    class E decision
    class H,I api
</pre>

## Related Pathways

- [MS Access](../ms-access/) - For migrating from Access to SQL Server

---

[← Previous: MS Access Pathway](../ms-access/.) | [Next: Schema Extraction →](database/01-schema-extraction)

*This pathway is part of the DEFRA AI Legacy Modernisation Playbook.*
