# Schema Extraction

## Overview

The first step in our SQL Server migration pathway is to extract the existing database schema. As Defra and CDP uses Liquibase for database version control, we will use the Liquibase CLI to generate a changelog that captures the current structure of your SQL Server database. This changelog will serve as the foundation for further migration steps and also provide valuable context to AI tools for understanding your database schema.

## Prerequisites
- Docker and Docker Compose
- Liquibase CLI - We recommend using the official Liquibase Docker image but you can also install Liquibase directly if preferred.
- Access to the SQL Server database
- Domain knowledge of your database structure and application

## Docker Environment Setup

### 1. Create Docker Compose Configuration

Create a `docker-compose.yml` file with the following configuration to set up both SQL Server and Liquibase containers.

**NOTE**: Ensure you have read and accept the SQL Server Developer Edition [license terms](https://www.microsoft.com/en-us/sql-server/sql-server-downloads). If you accept the EULA, set `ACCEPT_EULA` to 'Y' in the environment variables.

```yaml
services:
  mssql:
    image: mcr.microsoft.com/mssql/server:2022-latest
    container_name: mssql_container
    environment:
      ACCEPT_EULA: 'N'
    env_file:
      - .env
    ports:
      - "1433:1433"
    volumes:
      - mssql_data:/var/opt/mssql
    restart: unless-stopped

  liquibase:
    image: liquibase/liquibase:4.24
    container_name: liquibase_container
    depends_on:
      - mssql
    env_file:
      - .env
    environment:
      LIQUIBASE_COMMAND_URL: jdbc:sqlserver://mssql:1433;databaseName=tbcms;encrypt=false;trustServerCertificate=true
      LIQUIBASE_COMMAND_USERNAME: sa
      LIQUIBASE_COMMAND_PASSWORD: ${MSSQL_SA_PASSWORD}
      LIQUIBASE_COMMAND_DRIVER: com.microsoft.sqlserver.jdbc.SQLServerDriver
      LIQUIBASE_COMMAND_CHANGELOG_FILE: changelog/db.changelog.xml
    volumes:
      - ./changelog:/liquibase/changelog
    restart: "no"

volumes:
  mssql_data:
    driver: local
```

### 2. Create Environment Configuration

Create a `.env` file in the same directory with your SQL Server password:

```
MSSQL_SA_PASSWORD=YourStrongPasswordHere123!
```

**Note:** Make sure your password meets SQL Server requirements (at least 8 characters, containing uppercase, lowercase, numbers, and special characters).

### 3. Prepare Directory Structure

Create the necessary directory structure for Liquibase:

```bash
mkdir changelog
```

### 4. Start the Environment

Start the SQL Server container:

```bash
docker-compose up -d mssql
```

Wait for SQL Server to fully initialize (check logs with `docker-compose logs mssql`) before proceeding with Liquibase operations.

## Liquibase Generation Process

### 1. Generate Initial Changelog

Once your SQL Server container is running and your database is accessible, generate the initial changelog from your existing database schema:

```bash
docker-compose run --rm liquibase generate-changelog
```

This will create a `changelog/db.changelog.xml` file containing your current database structure.

### 2. Validate the Generated Changelog

Verify that the changelog was generated correctly:

```bash
docker-compose run --rm liquibase validate
```

### 3. Check Changelog Status

Check the current status of your database against the changelog:

```bash
docker-compose run --rm liquibase status
```

### 4. Review Generated Files

Examine the generated changelog file:

```bash
# View the generated changelog
cat changelog/db.changelog.xml

# Or open it in your preferred editor
code changelog/db.changelog.xml
```

The generated changelog will contain all your database objects including tables, constraints, indexes, and other schema elements in Liquibase's XML format.

You may find that the changelog is quite verbose and also contains SQL Server-specific syntax. The next step will be to refactor this changelog for compatibility with PostgreSQL or other target databases.

---

[← Previous: SQL Server Pathway](../README.md) | [Next: Changelog Refactoring →](02-changelog-refactoring.md)
