# MS Access Pathway

This pathway outlines the recommended approach for migrating MS Access applications with AI assistance.

## Overview

Microsoft Access applications typically consist of two main components that require different migration strategies:

1. **Frontend Components**: Forms, reports, and user interfaces
2. **Backend Components**: Database schema, data, and business logic

<pre class="mermaid">
graph TD
    A[MS Access] -->|Frontend| B[Document Forms]
    B --> C[Modern UI Implementation]
    A -->|Database| D[SQL Server Migration Assistant SSMA]
    D --> E[Refactor Generated SQL]
    E --> F[Follow SQL Server Pathway]
</pre>

Both sub-paths (frontend and database) have been broken down into detailed guides which can be followed independently or in parallel, depending on the complexity of the Access application.

## Frontend

1. **[Document UI](frontend/01-document-ui)**

## Database

1. **[Schema Migration using SSMA](database/01-ssma-migration)**
2. **[SQL Refactoring](database/02-sql-refactoring)**
3. **[Follow SQL Server Pathway](../sql-server/)**

---

*This pathway is part of the DEFRA AI Legacy Modernisation Playbook. For questions or contributions, please refer to the main documentation.*