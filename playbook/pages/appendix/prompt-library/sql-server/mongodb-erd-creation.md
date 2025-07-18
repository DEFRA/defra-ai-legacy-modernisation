# MongoDB Schema Design

This prompt can be used to suggest how a table from a RDBMS could be incorporated into a MongoDB schema.

```
I need to include the `business` table from a SQL database in a new MongoDB schema. You can use the following:
- #file:documentation - System documentation to provide domain / business entity context
- #file:db.changelog.xml - Liquibase changelog for SQL table context
- #file:mongo-erd.md - Contains the current Mongo schema Mermaid ERD. Create this if it does not exist.

# ANALYSIS PHASE
1. Analyze the generated changelog to identify the structure and content.
2. Find the `business` table and identify:
  - All data columns
  - Relations with other tables
  - Any specific data types or constraints
3. Determine how this table fits into the overall MongoDB schema:
  - Should it be a separate collection?
  - Should it be embedded in another document?
  - Should it be a reference to another collection for lookups or relationships?
  - Explore the benefit of denormalization for performance
4. Consider the data access patterns and how this table will be used in the application.

# ERD Creation
Create or update the Mermaid ERD in `mongo-erd.md` to include the results of your analysis. The ERD should reflect:
- The new collection or embedded document structure
- Any relationships with other collections
- The data types and constraints that are relevant for MongoDB
- Ensure the ERD is clear and follows best practices for MongoDB schema design

# SQL to MongoDB Mapping
Document how the `business` table maps to the MongoDB schema:
- The name of the MongoDB collection that will represent this table
- List each field in the collection, its type, and any constraints and what it maps to in the original SQL table
- For fields that are embedded, document the parent collection and how the fields are nested. Nested fields should follow the format `parentField->childField`.
- For fields that are referenced, document the reference collection and how the lookup will be performed.
```

---

[← Previous: Liquibase Changelog Refactor](./liquibase-changelog-refactor.md)
