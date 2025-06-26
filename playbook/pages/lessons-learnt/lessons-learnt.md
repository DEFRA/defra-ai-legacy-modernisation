
# Lessons Learnt

This document captures key lessons learnt during the DEFRA AI Legacy Modernisation project to help future teams avoid common pitfalls and adopt best practices.

## Working with AI Tools

### 1. Issue with Documentation of Legacy Application

**Issue**: GitHub Copilot had difficulty interpreting PowerPoint presentations (.pptx files) when used as reference material for implementing UI components and pages.

**Root Cause**: AI tools like GitHub Copilot work better with image formats that provide clear visual information rather than proprietary document formats.

**Solution**: Export PowerPoint slides as PNG images with the following specifications:
- Minimum resolution: 1080px width
- High quality export settings
- Clear, readable text and UI elements

**Best Practice**: When providing visual references to AI tools:
- Use high-resolution images (PNG, JPEG)
- Ensure text is clearly readable
- Include multiple views/states of components when relevant
- Consider providing both overview and detailed views

**Impact**: This approach significantly improved the accuracy of AI-generated code and reduced the number of revision cycles needed to match the intended design.

### 2. Hallucinating Table IDs

**Issue**: The database schema contained reference tables that intentionally did not have ID columns. However, Copilot inherently applies SQL best practices and automatically generated ID columns for tables that shouldn't have them.

**Root Cause**: Copilot's training prioritises standard database design patterns, which typically include primary key ID columns for all tables.

**Solution**: We resolved this by creating a stricter prompt that explicitly stated: "Tables should be created exactly as specified in the schema. Tables without IDs in the original schema must be created without ID columns."

**Impact**: This ensured the migrated database structure matched the original Access database design exactly.

### 3. Synthetic Data Character Length Overflow

**Issue**: During the Access DB to PostgreSQL migration, we requested Copilot to add 'Fake' prefixes to names and addresses to clearly identify synthetic data and avoid any Personal Identifiable Information (PII) concerns. This caused the generated data to exceed the original schema's character limits.

**Root Cause**: Adding 'Fake' as a prefix increased string lengths beyond the original column constraints (e.g., 'John Smith' became 'Fake John Smith', increasing from 10 to 15 characters).

**Solution**: We used Copilot to truncate the synthetic data to fit within the original schema constraints.

**Best Practice**: For future projects, the ideal solution would be to use shorter prefixes such as 'F_John Smith' instead of 'Fake John Smith', which would minimise character length impact whilst still clearly indicating synthetic data. Consider either:
- Using minimal prefixes (F_, or  X_)
- Increasing column lengths in test environments
- Adding separate boolean flags to indicate synthetic data

### 4. Frontend-Backend Data Mapping Ambiguity

**Issue**: The naming conventions used in database tables did not clearly correspond to frontend element names, creating uncertainty about data relationships. For example, it was unclear whether the `tb-status` dropdown component would map to the `tb_status_t` table.

**Root Cause**: The legacy system lacked clear documentation linking frontend components to their corresponding database tables, and naming conventions differed between frontend (kebab-case) and database (snake_case) implementations.

**Solution**: We used Copilot to systematically map each frontend component to its potential data source tables. The output was then reviewed and verified with subject matter experts familiar with both the database structure and the TB Content Management System (TB-CMS).

**Best Practice**: For future modernisation projects:
- Establish clear naming convention mappings early in the project
- Document component-to-table relationships explicitly
- Involve domain experts in verification processes
- Consider creating automated tools to validate data mappings

**Impact**: This approach helped establish reliable data flow patterns and reduced integration errors between frontend and backend systems.

### 5. Establishing Copilot Development Standards

**Issue**: Without clear guidance, Copilot generated code that was inconsistent with project requirements, government standards, and existing system patterns, leading to additional rework and quality issues.

**Root Cause**: Copilot operates on general programming knowledge but lacks specific context about project requirements, coding standards, accessibility guidelines, and reference materials location.

**Solution**: We created comprehensive Copilot rules that provided explicit instructions for both frontend and backend development, including:
- Location of reference materials (screenshots, documentation, schemas)
- Adherence to GDS GOV.UK design system and accessibility standards
- Project-specific coding conventions and patterns
- Database schema requirements and constraints
- Security and data protection guidelines

**Best Practice**: Establish clear Copilot instructions early in the project that cover:
- **Frontend requirements**: UI/UX standards, accessibility compliance, responsive design patterns
- **Backend requirements**: API conventions, database patterns, security protocols, error handling
- **Reference material locations**: Documentation paths, screenshot directories, schema files
- **Quality standards**: Code formatting, testing requirements, performance considerations
- **Regulatory compliance**: Government digital standards, data protection requirements

**Impact**: This significantly accelerated development velocity whilst ensuring consistent code quality and compliance with all required standards across both frontend and backend components. 


### 6. Output Format Modernisation Strategy

**Issue**: The legacy TB-CMS application exported outputs exclusively to Microsoft Word documents, creating vendor dependency and limiting formatting flexibility.

**Root Cause**: The original system was built around Microsoft services integration, resulting in tight coupling to proprietary document formats.

**Solution**: The modernised application is node based and  produces reports in multiple formats rather than being constrained to a single proprietary format, enabling greater flexibility and reducing vendor lock-in.

**Best Practice**: For legacy modernisation projects:
- Decouple output generation from specific vendor formats
- Implement format-agnostic reporting engines
- Support multiple export formats (PDF, HTML, CSV, etc.)
- Consider user preferences and accessibility requirements

**Impact**: This approach provides greater flexibility in output formatting, reduces dependency on Microsoft services, and enables future format extensibility without system redesign. 


### 7. Database Migration Strategy -WIP

**Issue**: The legacy TB-CMS used Microsoft Access database, which is incompatible with modern development standards and cloud deployment requirements.

**Root Cause**: Microsoft Access is a desktop database system that lacks scalability, cloud compatibility, and modern development tooling support required for contemporary applications.

**Solution**: We migrated from Access to MongoDB using a structured approach:
- Exported the original Access database schema
- Converted the schema to Liquibase format for database-agnostic deployment
- Used Copilot to generate synthetic test data matching the original structure
- Validated the migration with comprehensive testing

**Best Practice**: For database modernisation projects:
- Use schema migration tools (Liquibase, Flyway) for database-agnostic deployments
- Generate comprehensive synthetic data for testing
- Maintain data structure integrity during migration
- Consider NoSQL alternatives when appropriate for scalability
- Implement thorough validation processes

**Impact**: This migration enables cloud deployment, improved scalability, and alignment with modern development standards whilst maintaining data structure integrity.
