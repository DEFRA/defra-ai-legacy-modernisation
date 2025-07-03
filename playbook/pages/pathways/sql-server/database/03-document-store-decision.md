# Decision Point: Migrate to Document Store?

# Overview

As CDP is the target platform for new projects within Defra, which uses MongoDB as its primary database, we need to consider whether migrating your SQL Server database to a document store like MongoDB is feasible. This decision will depend on the following:
* The complexity of your existing database schema
* The nature of your data and how it is accessed
* The potential benefits of moving to a document store, such as improved scalability and flexibility
* How much current data transformation is required to fit the document model
* How long would data transformation take

In most cases, if your RDBMS database is relatively simple and does not require extensive data transformation, it might be more efficient to migrate to a document store to take advantage of using CDP as your platform. However, if your database is complex or requires significant transformation, it may be more practical to stick with a relational database management system (RDBMS) like PostgreSQL.

CDP does have support for PostgreSQL but only for specific use cases. If you are considering using PostgreSQL, it is recommended to consult with the CDP team to ensure compatibility and support. It might be the case that your application cannot be migrated to CDP at this time, and you will need to continue using your existing SQL Server database.

Regardless, of the decision you make, AI tools can assist in the migration process, whether you choose to migrate to a document store or stick with an RDBMS. The next steps will guide you through either using AI to assist in migrating to a document store like MongoDB or generating an OpenAPI specification for your chosen solution.

---

[← Previous: Changelog Refactoring](02-changelog-refactoring.md)

**Decision Point:** Choose your migration approach:
- [Document Store Path →](04-document-store.md)
- [Relational Database Path →](05-openapi-specification.md)
