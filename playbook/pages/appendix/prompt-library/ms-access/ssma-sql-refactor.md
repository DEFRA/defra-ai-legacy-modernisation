# SSMA SQL Refactor

This prompt can be used to refactor SQL generated from SQL Server Migration Assistant (SSMA).

```
I want to refactor the #file:script.sql SQL script. Your task is to follow the below steps to analyze it and refactor it according to the specified rules.

You are allowed create / run any python scripts or terminal commands to assist in the analysis and refactoring process.

# ANALYSIS PHASE

Identify:
  1. Any warning comments
  2. Relations between tables
  3. Foreign key creation
  4. References to these foreign keys in 'MS_SSMA_SOURCE' metadata

# REFACTOR PHASE

Refactor any SQL matching the following rules:
  - Create a new script file with the same name as the original but with a `.refactored.sql` extension
  - Rename any primary key constraints to follow the format PK_{table_name}_{column_name}
  - Rename any foreign key constraints like [TableName]${GUID} to FK_{child_table}_{parent_table}
  - Rename any indexes like [TableName]${GUID} to IDX_{table_name}_{column_name}
  - Ensure any updated foreign keys are updated elsewhere in the script
  - Identify which warnings flagged by the migration assistant need addressed

# SUMMARISE PHASE
Create a summary file in markdown format with the following sections:
  - Summary of changes made
  - List of warnings addressed
  - List of foreign keys renamed
  - Any other relevant notes
```

---

[← Previous: Prompt Library](../.)
