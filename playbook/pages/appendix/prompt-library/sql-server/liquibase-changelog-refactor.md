# Liquibase Changelog Refactor

This prompt can be used to generate and refactor Liquibase changelogs that have been automatically generated from a database.

```
I want to refactor #file:db.changelog.xml. Your task is to follow the below steps to analyze it and refactor it according to the specified rules.

# ANALYSIS PHASE
1. Analyze the generated changelog to identify the structure and content.
2. Identify the tables, columns, data types, constraints, and relationships present in the database.
3. Identify any default values, indexes, and foreign keys that need to be included in the changelog.
4. Identify any vendor specific data types / fucntions that need to be converted to common Liquibase types.

# REFACTOR PHASE
1. After the changelog is generated, refactor the change log according to the following rules:
  - The main changelog should only include child changelogs and not directly run migration operations
  - Child changelogs should follow the convention db.changelog-{version}.xml and start at 1-0
  - Ensure data types are converted to common Liquibase data types. For example:
    - `nvarchar(max)` should be converted to `TEXT`
    - `datetime2` should be converted to `TIMESTAMP`
    - `bit` should be converted to `BOOLEAN`
  - Ensure any default values are retained but ensure that they are compatible with the liquibase data type for the column.
  - Use standard SQL functions like `CURRENT_TIMESTAMP` instead of vendor-specific functions.
  - Only use vendor specific data types or functions if they are necessary and cannot be converted to common Liquibase types. These must be documented in the changelog and summary.
3. Ensure that the original changeset IDs are preserved for traceability.
4. Ensure that the author of all changesets is "liquibase (generated)"
5. Ensure only two changelogs files are created for this task:
  - changelog/db.changelog.xml
  - changelog/db.changelog-1.0.xml
```
