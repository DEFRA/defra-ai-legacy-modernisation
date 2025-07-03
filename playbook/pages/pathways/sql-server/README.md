# SQL Server Migration Pathway

This pathway provides comprehensive guidance for migrating SQL Server databases to modern cloud-native solutions using AI-assisted development practices.

## Overview

SQL Server modernisation typically involves database migration and API development that can be approached in phases:

1. **Database Migration**: Transform SQL Server to modern database platforms
2. **API Development**: Create modern APIs from migrated database structures

<pre class="mermaid">
graph TD
    A[SQL Server Database] --> B[Schema Extraction]
    B --> C[Refactor and Deloy Liquibase Changelog]
    C --> E{Decision Point: Migrate to Document Store?}
    E -->|Document Store Possible| F[Consider MongoDB]
    E -->|Stick with RDBMS| H
    F --> H[Generate OpenAPI Specification]
    H --> I[Develop Backend API]
</pre>

## Related Pathways

- [MS Access](../ms-access/) - For migrating from Access to SQL Server

---

*This pathway is part of the DEFRA AI Legacy Modernisation Playbook.*
