# Decision Point: Migrate to MongoDB

As CDP is the target platform for new projects within Defra, which uses MongoDB as its primary database, we need to consider whether migrating a RDBMS to MongoDB is feasible. This decision will depend on the following:
* The complexity of your existing database schema
* The nature of your data and how it is accessed
* The potential benefits of moving to MongoDB, such as improved scalability and flexibility
* How much current data transformation is required to fit the document model
* How long would data migration take

In most cases, if your RDBMS database is relatively simple and does not require extensive data transformation, it probably makes sense migrating to MongoDB to take full advantage of CDP. However, if your database is complex or requires significant transformation, it may be more practical to stick with a RDBMS.

CDP does have support for PostgreSQL but only for specific approved use cases. If you are considering using PostgreSQL, it is recommended to consult with the CDP team to ensure compatibility and support. It might be the case that your application cannot be migrated to CDP at this time, and you will need to provision your service through the traditional CCoE routes.

Regardless, of the decision you make, AI tools can assist in the migration process, whether you choose to migrate to MongoDB or stick with an RDBMS. The next steps will guide you through either using AI to assist in migrating to MongoDB or generating an OpenAPI specification for your chosen solution.

---

[← Previous: Changelog Refactoring](02-changelog-refactoring)

**Decision Point:** Choose your migration approach:
- [MongoDB Migration →](04-mongodb-migration)
- [Relational Database Path →](05-openapi-specification)
