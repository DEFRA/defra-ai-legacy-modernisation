# Liquibase Changelog Refactor

This prompt can be used to generate and refactor Liquibase changelogs that have been automatically generated from a database.

```
# Context
I want to refactor #file:db.changelog.xml. Your task is to follow the below steps to analyse it and refactor it according to the specified rules.

You are allowed to create / run any python scripts or terminal commands to assist in the analysis and refactoring process.

# Analysis Phase
1. Analyse the generated changelog to identify the structure and content.
2. Identify the tables, columns, data types, constraints, and relationships present in the database.
3. Identify any default values, indexes, and foreign keys that need to be included in the changelog.
4. Identify any vendor specific data types / fucntions that need to be converted to common Liquibase types.

# Refactor Phase
DO NOT modify the original #file:db.changelog.xml file in any way. Instead, create a new changelog file called `db.changelog-1-0.xml` to store the refactored changesets. The new file should follow the structure and conventions of Liquibase changelogs.

You can fetch https://docs.liquibase.com/concepts/data-type-handling.html to get available Liquibase types and their mappings across RDBMS implementations.

1. Copy the original changesets from the `db.changelog.xml` file into the new file
2. Refactor the changesets according to the following rules:
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

# Validation Phase
1. Validate the new changelog file against the original #file:db.changelog.xml to ensure that all changesets are correctly refactored and that the structure is maintained.
2. Confirm no additional changesets are added that were not present in the original changelog.

# Finalisation Phase
1. Provide a summary of the changes made in the new changelog file.
2. Document any vendor specific data types or functions that were used and why they could not be converted to common Liquibase types.
3. Ensure the main changelog file (`db.changelog.xml`) is updated to include the new child changelog file (`db.changelog-1-0.xml`).
```

---

[← Previous: Prompt Library](../.)
