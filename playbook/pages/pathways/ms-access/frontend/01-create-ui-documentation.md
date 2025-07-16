# Document Forms

## Overview

The first step in our MS Access frontend migration pathway is to thoroughly document all forms within the legacy system. This documentation serves as the foundation for creating user stories and eventually modernising the user interface using GDS design standards. Proper documentation ensures that business requirements and user workflows are fully captured before beginning technical implementation.

<pre class="mermaid">
flowchart TD
    A["🏢 MS Access Application"] --> B["📋 Inventory All Forms"]
    B --> C["📝 Document Form Details"]
    C --> D["📸 Capture Visual Documentation"]
    D --> E["📖 Generate User Stories"]
    E --> F{"Documentation Complete?"}
    F -->|No| G["🔄 Refine Documentation"]
    F -->|Yes| H["✅ Complete Documentation Package"]
    G --> C

    classDef legacy fill:#ffebee,stroke:#c62828,stroke-width:2px
    classDef process fill:#e3f2fd,stroke:#1976d2,stroke-width:2px
    classDef documentation fill:#f3e5f5,stroke:#7b1fa2,stroke-width:2px
    classDef decision fill:#fff3e0,stroke:#f57c00,stroke-width:2px
    classDef output fill:#e8f5e8,stroke:#2e7d32,stroke-width:2px

    class A legacy
    class B,C,D process
    class E documentation
    class F,G decision
    class H output
</pre>

## Prerequisites

- Access to the MS Access application and its forms
- Screenshots or detailed descriptions of each form
- Understanding of user roles and business processes
- Domain knowledge of the application workflows

## Documentation Process

### 1. Inventory All Forms

Begin by creating a comprehensive inventory of all forms in your MS Access application:

1. **Navigate through the application** systematically to identify all forms
2. **Create a master list** with form names and their primary purposes
3. **Note the relationships** between forms (how users navigate between them)
4. **Identify user roles** that interact with each form

### 2. Document Form Details

For each form identified, create detailed documentation including:

#### Form Structure
- **Form name and purpose**
- **Primary user role(s)** who interact with the form
- **Business process** the form supports
- **Navigation context** (how users reach this form)

#### Interactive Elements
Document every interactive component:
- **Input fields** (text boxes, dropdowns, checkboxes, radio buttons)
- **Buttons** and their actions
- **Navigation elements** (tabs, menus)
- **Data display areas** (tables, reports, calculated fields)
- **Validation rules** and error handling
- **Contextual tools** (calendar widgets, lookup functions)

#### Business Logic
- **Field dependencies** (conditional showing/hiding of elements)
- **Calculation rules** for computed fields
- **Data validation requirements**
- **Workflow rules** and approval processes

### 3. Capture Visual Documentation

Create visual documentation to supplement textual descriptions:

1. **Take screenshots** of each form in its various states
2. **Document different views** (create, edit, read-only modes)
3. **Capture error states** and validation messages
4. **Record any dynamic behaviours** (fields that appear/disappear based on selections)

#### Best Practices for Visual Documentation

**Important**: When creating visual references for AI tools like GitHub Copilot, follow these specifications based on lessons learned:

**Image Format Requirements:**
- Export screenshots as PNG or JPEG images (avoid PowerPoint .pptx files)
- Minimum resolution: 1080px width
- Use high quality export settings
- Ensure text is clearly readable and UI elements are crisp

**Content Guidelines:**
- Include multiple views/states of components when relevant
- Provide both overview and detailed views of complex forms
- Capture all interactive elements clearly
- Ensure form labels and field names are legible

**Why This Matters:**
AI tools work significantly better with high-resolution image formats that provide clear visual information rather than proprietary document formats. This approach has been proven to improve the accuracy of AI-generated code and reduce revision cycles needed to match the intended design.

## Generating User Stories

Once forms are thoroughly documented, the next step is generating comprehensive user stories following GDS service design standards.

### Using AI Tools for User Story Generation

1. **Prepare your documentation** with screenshots and detailed descriptions
2. **Use the Access Form User Stories prompt** from our prompt library to guide AI tools in creating comprehensive user stories
3. **Review and refine** the generated user stories to ensure they capture all requirements

The [Access Form User Stories prompt](../../../appendix/prompt-library/ms-access/access-form-user-stories.md) provides a structured template that ensures:
- Clear user roles and goals
- Comprehensive component documentation
- Detailed acceptance criteria
- GDS accessibility and design compliance requirements

### Key Elements of Effective User Stories

Each user story should include:
- **Clear user role** and context
- **Specific user goal** and desired outcome
- **Complete component inventory** with interactions
- **Testable acceptance criteria**
- **Accessibility requirements** aligned with GDS standards

## Output and Next Steps

By the end of this phase, you should have:
- Complete inventory of all forms in the legacy system
- Detailed documentation for each form including structure, components, and business logic
- Visual documentation (screenshots) of all form states
- Comprehensive user stories following GDS standards

This documentation will serve as the foundation for the next step: building modern, accessible user interfaces that maintain the functionality of the legacy system while following current design standards.

---

[← Back to MS Access Pathway](../.) | [Next: Build GDS-Compliant Views →](02-build-gds-views)

*This step is part of the DEFRA AI Legacy Modernisation Playbook.*
