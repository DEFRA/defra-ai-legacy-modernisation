# SQL Refactoring

In the previous step, the SQL Server Migration Assistant (SSMA) has migrated the Access database schema to SQL Server and you have outputted the generated SQL script. Although these scripts are functional, they are often difficult to read and require refactoring.

This step focuses on using AI tools to speed up the refactoring process, allowing it's validity to be verified and optimised for performance and maintainability.

## Prerequisites
- SQL Server Management Studio (SSMS)
- SQL Server Migration Assistant (SSMA) for Access - [Download here](https://docs.microsoft.com/en-us/sql/ssma/access/installing-sql-server-migration-assistant-for-access-accesstosql)
- Access to the SQL Server instance where the database was migrated
- AI tool for code refactoring
- Base SQL refactoring prompt ([see prompt library](../../../appendix/prompt-library))

## Refactoring Process

### 1. Manually Review Generated SQL
- Open the generated SQL script in your preferred code editor.
- Check for any obvious issues such as:
  - Inconsistent constraint naming conventions
  - Redundant or unnecessary constraints
  - Missing indexes or foreign keys
- Make a note of any custom rules or naming conventions that you want to apply during the refactoring process.

### 2. Use AI Tools for Refactoring
Open your AI tool of choice and start the refactoring process:

- Reference the SQL script in your AI tool.
- Use the base SQL refactoring prompt to guide the AI in improving the script.
- Review the AI-generated suggestions and apply them to the SQL script.

### 3. Validate Refactored SQL
Now that we have a refactored SQL script, it is essential to validate it before continuing with the migration process.

- Either delete / recreate the database or create a new one to test the refactored SQL:
- Execute the refactored SQL script in SQL Server Management Studio (SSMS).
- Check for any errors or warnings during execution.
- Verify that the database schema is created as expected.
- If the script fails, review the error messages and go back to step 2. Repeat until the script executes successfully.

### 4. Migrate Data from Access to SQL Server via SSMA
In order to test the schema is suitable for the data, you will need to migrate the data from the Access database to SQL Server. This is done using the SQL Server Migration Assistant (SSMA):

- Open SQL Server Migration Assistant (SSMA).
- Connect to the SQL Server instance and the Access database.
- Start the data migration process by clicking on the "Migrate Data" button.
- Ensure that the data is migrated successfully without any errors.

---

[← Previous: SSMA Migration](01-ssma-migration) | [Next: SQL Server Pathway →](../../sql-server)
