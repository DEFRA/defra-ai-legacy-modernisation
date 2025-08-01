# Schema Migration using SSMA

## Prerequisites
- Docker and Docker Compose
- Source Access database
- SQL Server Migration Assistant (SSMA) for Access - [Download here](https://docs.microsoft.com/en-us/sql/ssma/access/installing-sql-server-migration-assistant-for-access-accesstosql)
- SQL Server Management Studio (SSMS)

## Docker Environment Setup

### 1. Create Docker Compose Configuration

Create a `sql-server.compose.yml` file with the following configuration to set up a SQL Server container.

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

volumes:
  mssql_data:
    driver: local
```

## Migration Process

### 1. Setup SSMA Project
- Open SSMA and ensure you close the **Migration Wizard** if it appears.
- Hover over **File** and select **New Project** to create a new migration project.
- Enter a project name and select your target SQL Server version (this should match your Docker container version).
- Click **OK** to create the project.

### 2. Add Access Database
- In your SSMA project click on the **Add Databases** button in the toolbar and select your Access database file. SSMA will analyze the database and display its contents.
- You may be prompted to enter the Access database password if it is protected.
- Click **OK** to add the database.
- SSMA will analyze the database and display metadata such as tables, queries, and relationships in the **Access Metadata Explorer** pane.

### 3. Connect to SQL Server
- Click on the **Connect to SQL Server** button in the toolbar.
- You will be prompted to enter your SQL Server connection details:
  - **Server name**: `localhost` (or the IP address of your Docker host)
  - **Server port**: `1433` (or the port you mapped in your Docker Compose file)
  - **Database**: If this does not exist, you will need to create it via SSMS first.
  - **Authentication**: Use SQL Server Authentication
  - **Username**: `sa` (or your configured SQL Server user)
  - **Password**: The password you set in your `.env` file

### 4. Initial Migration
- In the **Access Metadata Explorer**, check the tables you want to migrate or select all.
- Right-click on the selected tables or click the **Convert Schema** button in the toolbar.
- SSMA will convert and create the tables in the connected SQL Server database.
- In the **SQL Server Metadata Explorer**, you will see the suggested schema conversion.

> **IMPORTANT**: Before proceeding with testing data migration, ensure that the data in the Access database is test data and is not classed as **OFFICIAL** or **OFFICIAL-SENSITIVE**.

- Click the **Convert, Load, and Migrate** button in the toolbar.
- Select **Overwrite All** if prompted to overwrite existing tables.
- SSMA will now apply the schema changes and migrate the data from Access to SQL Server.
- Ensure you monitor the output for any errors or warnings during the migration process. This will be used in the next step to refactor the SQL scripts.

### 5. Export SQL Scripts
Although SSMA does a good job of converting the schema, some auto-generated SQL scripts may not be optimal. For example, SSMA will likely:
- Add random GUIDs to any primary keys, foreign keys, and indexes names.
- Use unsupported data types like `ATTACHMENT`

The next step in the pathway is [SQL Refactoring](02-sql-refactoring) which aims to fix these issues and prepare the SQL scripts for production use.

However, before proceeding, the generated SQL scripts will need to be exported from SSMA:
- In the **SQL Server Metadata Explorer**, find the following:
  - Your database in the under **Databases**
  - The **dbo** schema
  - A list of tables that were converted from Access
- Once you have selected the tables, right-click and select **Save as Script**.
- Save the script to your filesystem, ensuring it has a `.sql` extension.

---

[← Previous: MS Access Pathway](../.) | [Next: SQL Refactoring →](02-sql-refactoring)
