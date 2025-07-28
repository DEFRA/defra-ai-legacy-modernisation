# MongoDB Schema Design

This prompt can be used to suggest how a business entity or domain entity from an existing system could be incorporated into a MongoDB schema.

Replace `<business_entity>` with the name of the entity you want to add to the MongoDB schema.

```
The `<business_entity>` entity from the existing system needs to be added to the MongoDB schema. You have been provided with the following:
- #file:documentation - System documentation to provide domain / business entity context
- #file:db.changelog.xml - Liquibase changelog for SQL context
- #file:mongo-erd.md - Contains the current Mongo schema Mermaid ERD. Create this if it does not exist.
- #file:stories - Contains the user stories that will the system will be built around

# Analysis Phase
1. Analyse the available documentation and changelog to identify the structure, relationships, and business context of the `<business_entity>`.
2. Identify:
  - All relevant data fields and attributes
  - Relationships with other entities
  - Any specific data types, constraints, or business rules
3. Determine how this entity fits into the overall MongoDB schema:
  - Should it be a separate collection?
  - Should it be embedded in another document?
  - Should it be a reference to another collection for lookups or relationships?
  - Explore the benefit of denormalization for performance and business needs
4. Consider the data access patterns and how this entity will be used in the application.

# MongoDB Schema Design
Using the analysis, suggest how the `<business_entity>` should be represented in MongoDB:
- The name of the MongoDB collection that will represent this entity
- List each field in the collection, its type, any constraints, and what it maps to in the original business context
- For fields that are embedded, document the parent collection and how the fields are nested. Nested fields should follow the format `parentField->childField`.
- For fields that are referenced, document the reference collection and how the lookup will be performed.
- Provide any additional notes on indexing, performance considerations, or specific MongoDB features that should be used
- Always use pascal case for collection names and camel case for field names

# ERD Creation
Create or update the Mermaid ERD in `mongo-erd.md` to include the results of your analysis. The ERD should reflect:
- The new collection or embedded document structure
- Any relationships with other collections/entities
- The data types, constraints, and business rules that are relevant for MongoDB
- Ensure the ERD is clear and follows best practices for MongoDB schema design

Each entity in the ERD should have the following layout:
1. **Entity Name**: The name of the MongoDB collection / schema
2. **Fields**: A list of fields in the collection, including:
    - Field Name (in camel case)
    - Data Type (e.g., String, Number, Date, ObjectId)
    - Constraints (e.g. indexed, unique, not null, nullable)
```

---

[← Previous: Liquibase Changelog Refactor](./liquibase-changelog-refactor)
