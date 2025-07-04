# Requirements Building

Requirements building bridges the gap between understanding what exists and defining what needs to be built. This stage uses the documentation gathered in the previous phase to create a comprehensive picture of the modernised system's requirements.

<pre class="mermaid">
flowchart TD
    A["📋 Documented Legacy System"] --> B["🤖 Generate High-Level Overview"]
    B --> C["🎯 Define System Scope"]
    C --> D["🏗️ Create Epic Structure"]
    D --> E["📝 Generate User Stories"]
    E --> F["✅ Validate with Stakeholders"]
    F --> G{"Requirements Complete?"}
    G -->|No| H["🔄 Refine Requirements"]
    G -->|Yes| I["✅ Requirements Ready for Implementation"]
    H --> E

    classDef documentation fill:#e8f5e8,stroke:#2e7d32,stroke-width:2px
    classDef ai fill:#e3f2fd,stroke:#1976d2,stroke-width:2px
    classDef requirements fill:#fff3e0,stroke:#f57c00,stroke-width:2px
    classDef validation fill:#f3e5f5,stroke:#7b1fa2,stroke-width:2px

    class A documentation
    class B ai
    class C,D,E,H requirements
    class F,G,I validation
    class J requirements
</pre>

## Key Activities

### 1. Generate High-Level System Overview
Use AI to create a comprehensive overview of the modernised system based on the documentation gathered in the previous phase. This overview should capture the system's purpose, key user interactions, core processes, and technical requirements. At this stage, you should focus on:
- **System Goals**: What the modernised system aims to achieve
- **User Needs**: Who the users are and what they need from the system
- **High-Level Architecture**: How the system will be structured, including major components and their interactions
- **Key Functional Areas**: Major features or user journeys that the system will support
- **Non-Functional Requirements**: Performance, security, and usability considerations
- **Technical Constraints**: Any limitations or dependencies that must be considered
- **Data Requirements**: What data the system will need to store, process, and manage
- **Integration Points**: If / How the system will interact with other systems or services
- **Compliance and Regulatory Requirements**: Any legal or policy constraints that must be adhered to
- **Modernisation Opportunities**: Areas where the system can be improved or transformed, rather than simply replicated

### 2. Define System Scope and Boundaries
Clearly define what the modernised system will and will not include, based on the high-level overview and stakeholder input. Avoid doing a 'lift and shift' of legacy functionality; instead, focus on improving, modernising, and transforming the system.

### 3. Create Epic Structure
Break down the system into logical, manageable epics that can guide development. Use AI to assist in identifying and structuring these epics based on scope, goals and user needs. These epics should represent major functional areas or user journeys within the system.

### 4. Generate User Stories
Break down epics into detailed, actionable user stories that can guide implementation. To make the best use of AI assisted implementation, you should ensure each user story has:
- Clear context and background
- Specific user needs and goals
- Testable acceptance criteria
- Technical considerations and dependencies

#### Validate User Stories with Stakeholders
Once user stories are generated, validate them with stakeholders to ensure they accurately reflect user needs and don't regress existing functionality. This validation step is crucial to ensure alignment and buy-in from all involved stakeholders. To validate user stories, you can:
- Review user stories with SMEs and end users
- Conduct workshops or review sessions to gather feedback

## Common Challenges and Solutions
The requirements building process can be complex and you may encounter several challenges. Here are some common challenges and suggested solutions:
- **AI-Generated Requirements Missing Context**: Always validate AI-generated content with SMEs. Use iterative refinement and provide additional context when AI understanding is incomplete.

## Success Criteria

Requirements building is complete when:
- ✅ High-level system overview is validated by stakeholders
- ✅ System scope, goals and boundaries are clearly defined
- ✅ Complete epic structure covers all system functionality
- ✅ User stories are detailed, testable, and have clear acceptance criteria
- ✅ Requirements are validated by SMEs and end users
- ✅ Technical risks and dependencies are identified and planned

## Next Steps

With requirements building complete, you're ready to move into implementation using the appropriate pathway.

---

[← Previous: Documentation Gathering](documentation-gathering) | [Next: Pathways Overview →](../pathways/README)

*This page is part of the DEFRA AI Legacy Modernisation Playbook.*
