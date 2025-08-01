# Changelog Refactoring

## Overview

As mentioned in the previous section, the generated Liquibase changelog from your SQL Server database may contain SQL Server-specific syntax and be quite verbose. The next step is to refactor this changelog to make it more concise and compatible with PostgreSQL or other target databases. We can use AI tools to assist in this process, but it is also important to have a good understanding of your database structure and the specific requirements of your target database.

For the purposes of this guide, we will focus on refactoring the changelog for PostgreSQL, as this is the standard RDBMS used in new projects across Defra. However, these principles can be applied to other databases as well.

## Prerequisites
- Docker and Docker Compose
- Liquibase CLI - We recommend using the official Liquibase Docker image but you can also install Liquibase directly if preferred.
- Access to the SQL Server database
- Domain knowledge of your database structure and application
- AI tool for changelog refactoring
- Liquibase changelog refactor prompt ([see prompt library](../../../appendix/prompt-library/sql-server/liquibase-changelog-refactor))

## Refactoring Process

### 1. Review the Generated Changelog
Before refactoring, examine the changelog generated in the previous step.

Take note of:
- SQL Server-specific data types that need conversion
- Verbose or redundant constraint definitions
- Default values that may need adjustment
- Any vendor-specific functions used

### 2. Use AI Tools for Refactoring
Open your AI tool of choice and start the refactoring process:

1. **Reference the changelog file** in your AI tool (copy the contents or upload the file)
2. **Use the refactor prompt** from the prompt library to guide the AI in:
   - Converting SQL Server-specific data types to Liquibase generic types
   - Restructuring the changelog for better organization
   - Ensuring cross-database compatibility
3. **Review the AI-generated suggestions** and apply them to create your refactored changelog files
4. **Save the refactored files** in the correct structure:
   - `changelog/db.changelog.xml` (main changelog)
   - `changelog/db.changelog-1.0.xml` (child changelog with actual changes)

### 3. Manual Review and Adjustments
After AI refactoring, manually review the output for:
- Consistency in naming conventions
- Proper data type conversions
- Retained foreign key relationships
- Appropriate default values for the target database

## Validating the Changelog

### 1. Create Docker Compose Configuration

Create a `postgres.compose.yml` file with the following configuration to set up PostgreSQL and Liquibase containers for testing your refactored changelog:

```yaml
services:
  postgres:
    image: postgres:16
    container_name: postgres_container
    environment:
      POSTGRES_DB: tbcms
      POSTGRES_USER: postgres
      POSTGRES_PASSWORD: ppp
    ports:
      - "5432:5432"
    volumes:
      - postgres_data:/var/lib/postgresql/data
    healthcheck:
      test: ["CMD-SHELL", "pg_isready -U postgres -d tbcms"]
      interval: 10s
      timeout: 5s
      retries: 5
    restart: unless-stopped

  liquibase:
    image: liquibase/liquibase:4.24
    container_name: liquibase_container
    depends_on:
      postgres:
        condition: service_healthy
    environment:
      LIQUIBASE_COMMAND_URL: jdbc:postgresql://postgres:5432/tbcms
      LIQUIBASE_COMMAND_USERNAME: postgres
      LIQUIBASE_COMMAND_PASSWORD: ppp
      LIQUIBASE_COMMAND_DRIVER: org.postgresql.Driver
      LIQUIBASE_COMMAND_CHANGELOG_FILE: changelog/db.changelog.xml
    volumes:
      - ./changelog:/liquibase/changelog
    restart: "no"

volumes:
  postgres_data:
    driver: local
```

### 2. Prepare Directory Structure

Ensure you have the necessary directory structure with your refactored changelog:

```bash
mkdir -p changelog
```

### 3. Start the Environment

Start the PostgreSQL container:

```bash
docker-compose -f postgres.compose.yml up -d postgres
```

Wait for PostgreSQL to fully initialize and pass health checks before proceeding with Liquibase operations.

### 4. Test Refactored Changelog

Once your PostgreSQL container is running, test your refactored changelog:

```bash
# Validate the changelog syntax
docker-compose -f postgres.compose.yml run --rm liquibase validate

# Check status against the PostgreSQL database
docker-compose -f postgres.compose.yml run --rm liquibase status

# Apply the changelog to PostgreSQL (if validation passes)
docker-compose -f postgres.compose.yml run --rm liquibase update
```

You should now have a refactored Liquibase changelog that has been deployed to your local PostgreSQL database. This can also be used as context for AI tools to further refine or generate application code based on the database schema.

## Common Issues Found

When migrating from SQL Server to PostgreSQL using Liquibase, several data type and syntax incompatibilities commonly arise. The examples below are based on real migration scenarios but represent typical patterns rather than an exhaustive list. Understanding these patterns will help you identify and resolve similar issues in your specific migration.

### Data Type Conversions

#### Text and Character Fields
- **`nvarchar(MAX)`** → **`TEXT`**
  - SQL Server's unlimited text storage maps to PostgreSQL's TEXT type
  - Removes Unicode prefix requirement (`nvarchar` vs `varchar`)

- **`nvarchar(n)`** → **`VARCHAR(n)`** 
  - Standardizes variable-length character fields
  - PostgreSQL handles Unicode natively, removing need for `nvarchar`

- **`nchar(n)`** → **`CHAR(n)`**
  - Fixed-length character fields conversion
  - Similar Unicode considerations apply

#### Date and Time Fields
- **`datetime2`** → **`TIMESTAMP`**
  - Provides cross-database compatibility
  - Maintains precision while using standard SQL type

- **`datetime`** → **`TIMESTAMP`**
  - Legacy SQL Server datetime to standard timestamp
  - May require precision adjustments

- **`date`** → **`DATE`**
  - Usually compatible, but validate format handling

#### Boolean and Numeric Fields
- **`bit`** → **`BOOLEAN`**
  - SQL Server's bit type to proper boolean
  - Requires updating default values (0/1 → false/true)

- **`tinyint`** → **`SMALLINT`**
  - PostgreSQL doesn't have tinyint, maps to smallest integer type

- **`money`** → **`DECIMAL(19,4)`**
  - SQL Server's money type to standard decimal with appropriate precision

### Constraint and Index Issues
- **Naming Conventions**: SQL Server auto-generated constraint names may need standardization
- **Clustered Indexes**: PostgreSQL doesn't support clustered indexes directly
- **Check Constraints**: Syntax differences in constraint definitions may require updates

**Note**: These examples represent common patterns encountered in real SQL Server to PostgreSQL migrations. Your specific database may have additional or different conversion requirements depending on its schema complexity and SQL Server features used.

## Best Practice: Use Liquibase Data Types

For optimal cross-database compatibility, it's recommended to use Liquibase's generic data types rather than database-specific types. Liquibase automatically converts these generic types to the appropriate native types for your target database.

### Benefits of Liquibase Data Types
- **Cross-Database Compatibility**: Generic types work across all supported database platforms
- **Automatic Conversion**: Liquibase handles the mapping to native types for each database
- **Future-Proof**: Easier to migrate to different database platforms later
- **Standardization**: Consistent type definitions across your entire schema

### Common Liquibase Generic Types
Instead of using SQL Server-specific types, consider these Liquibase alternatives:

- Use **`BOOLEAN`** instead of `bit`
- Use **`BIGINT`** instead of `bigint`
- Use **`VARCHAR(n)`** instead of `nvarchar(n)`
- Use **`CLOB`** instead of `nvarchar(MAX)` or `text`
- Use **`TIMESTAMP`** instead of `datetime2`
- Use **`DECIMAL`** instead of `money`

### Data Type Matrix Reference
For a complete mapping of how Liquibase converts generic types to database-specific types, refer to the official [Liquibase Data Type Handling documentation](https://docs.liquibase.com/concepts/data-type-handling.html). This matrix shows exactly how each generic type maps to SQL Server, PostgreSQL, and other supported databases.

---

[← Previous: Schema Extraction](01-schema-extraction) | [Next: MongoDB Decision Point →](03-mongodb-decision-point)
