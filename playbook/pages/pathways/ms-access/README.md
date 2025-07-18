# MS Access Pathway

This pathway outlines the recommended approach for migrating MS Access applications with AI assistance.

## Overview

Microsoft Access applications typically consist of two main components that require different migration strategies:

1. **Frontend Components**: Forms, reports, and user interfaces
2. **Backend Components**: Database schema, data, and business logic

<pre class="mermaid">
graph TD
    A[MS Access] -->|Frontend| B[Document Forms]
    B --> C[Build GDS-Compliant Views]
    C --> G[Connect to Backend API]
    A -->|Database| D[SQL Server Migration Assistant SSMA]
    D --> E[Refactor Generated SQL]
    E --> F[Follow SQL Server Pathway]

    classDef legacy fill:#ffebee,stroke:#c62828,stroke-width:2px
    classDef frontend fill:#f3e5f5,stroke:#7b1fa2,stroke-width:2px
    classDef migration fill:#e3f2fd,stroke:#1976d2,stroke-width:2px
    classDef pathway fill:#e8f5e8,stroke:#2e7d32,stroke-width:2px

    class A legacy
    class B,C,G frontend
    class D,E migration
    class F pathway
</pre>

Both sub-paths (frontend and database) have been broken down into detailed guides which can be followed independently or in parallel, depending on the complexity of the Access application.

## Frontend

1. **[Document Forms](frontend/01-create-ui-documentation)**
2. **[Build GDS-Compliant Views](frontend/02-build-gds-views)**
3. **[Connect to Backend API](frontend/03-connect-backend-api)**

## Database

1. **[Schema Migration using SSMA](database/01-ssma-migration)**
2. **[SQL Refactoring](database/02-sql-refactoring)**
3. **[Follow SQL Server Pathway](../sql-server/)**

---

[← Previous: Requirements Building](../discovery-analysis/requirements-building) | [Next: SQL Server Pathway →](../sql-server/.)

*This pathway is part of the DEFRA AI Legacy Modernisation Playbook. For questions or contributions, please refer to the main documentation.*
