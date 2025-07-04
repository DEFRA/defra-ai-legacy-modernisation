# Documentation Gathering

Effective documentation is crucial for successful legacy system modernisation. It provides the necessary context and understanding of how the current system works, enabling AI tools to assist in the next phases of requirements building and implementation.

<pre class="mermaid">
flowchart TD
    START["📚 Documentation Gathering"] --> A["🧑‍💻 Find Subject Matter Expert"]
    A --> B["📚 Locate Existing Documentation"]
    B --> C["📋 Assess Documentation Quality"]
    C --> D{"Documentation Adequate?"}
    D -->|No| E["🤖🧑‍💻 Create / Improve Documentation"]
    D -->|Yes| F["🤖 Test AI Understanding"]
    E --> F
    F --> G{"AI Understanding Correct?"}
    G -->|No| H["🔄 Refine Documentation"]
    G -->|Yes| I["✅ Documentation Complete"]
    H --> E

    classDef title fill:#f3e5f5,stroke:#7b1fa2,stroke-width:3px,font-weight:bold
    classDef person fill:#ffeb3b,stroke:#f57f17,stroke-width:2px
    classDef document fill:#e8f5e8,stroke:#2e7d32,stroke-width:2px
    classDef ai fill:#e3f2fd,stroke:#1976d2,stroke-width:2px
    classDef decision fill:#fff3e0,stroke:#f57c00,stroke-width:2px

    class START title
    class A,B,C,E,H,I document
    class F,G ai
    class D,G decision
</pre>

## Key Activities

### 1. Find Subject Matter Experts (SMEs)

Identify people who understand the current system's business processes, technical implementation, and user needs. Start by looking for these key types of stakeholders:
- **System Users**: Current users who interact with the system daily
- **System Administrators**: Technical staff who maintain the system
- **Developers**: Those who built or maintain the system
- **Business Stakeholders**: Individuals who understand the business processes supported by the system

### 2. Locate Existing Documentation

Gather all available documentation about the current system from multiple sources. Search for these common types of documentation:
- **Technical Documentation**: Database schemas, API specifications, architecture diagrams
- **User Documentation**: User manuals, training materials, help guides
- **Business Documentation**: Process flows, business rules, requirements documents

Create an inventory of existing documentation with quality assessment to allow AI to assist in identifying gaps

### 3. Create and Improve Documentation

Fill documentation gaps and improve existing documentation quality to support AI assistance. This typically involves a combination of manual and AI-assisted tasks:
- **Screenshot user interfaces**: Capture all screens, forms, and reports
- **Record business processes**: Document step-by-step workflows
- **Map data flows**: Show how data moves through the system
- **Document business rules**: Capture validation rules and business logic
- **Interview SMEs**: Conduct interviews to gather insights and context
- **Export hard-to-reach code**: For example, extract VBA or SQL queries from databases or spreadsheets
- **Use AI to analyze code**: Generate documentation from source code
- **Create process diagrams**: Convert text descriptions to flowcharts

Focus on business functionality over technical implementation details and use consistent terminology while validating all documentation with SMEs.

### 4. Test AI Understanding

Validate that AI tools correctly understand your documented system before proceeding. Follow this process:
- Submit test prompts to AI tools with your documentation
- Review AI responses with SMEs for accuracy
- Identify areas where AI misunderstood or missed important details
- Refine documentation to address gaps and provide more context
- Break complex concepts into simpler components if needed
- Repeat testing until you are confident AI demonstrates accurate understanding

## Common Challenges and Solutions
The documentation gathering process can be complex and you may encounter several challenges. Here are some common challenges and suggested solutions:
- **SMEs with Limited Time**: Use structured interviews and documentation templates to make the most of limited SME time. Consider scheduling multiple short sessions rather than one long meeting.
- **Complex Legacy System Architecture**: A lot of legacy systems are large and unintuitive. If the AI tools seem to be struggling to understand the context, start with high-level documentation and progressively add detail. Use diagrams to visualize complex relationships and data flows.
- **AI Misunderstanding Documentation**: Use iterative testing and refinement. Break complex concepts into simpler components and provide more context and examples.
- **AI Not Understanding Artifacts**: If AI tools struggle with specific artifacts, such as images or complex diagrams, consider providing additional context or simplifying the artifacts. Use text descriptions to clarify complex visual elements and ensure images are large enough for AI to process effectively.

## Success Criteria
Documentation gathering is complete when:
- ✅ All SMEs have been identified and engaged
- ✅ Existing documentation has been collected and assessed
- ✅ Critical documentation gaps have been filled
- ✅ AI tools demonstrate accurate understanding of the system through testing
- ✅ Documentation is validated by SMEs and stakeholders
- ✅ Business processes, data flows, and technical architecture are clearly documented

## Caveats

It's important to recognise that documentation gathering is an ongoing process throughout the modernisation journey, not a one-time activity. This stage focuses on establishing the foundational understanding needed to begin AI-assisted development.

More in-depth, technology-specific documentation advice using AI tools will be provided in the relevant pathway sections (e.g., MS Access, SQL Server).

The goal of this initial documentation gathering stage is to create sufficient understanding for AI tools to assist in the next phase of requirements building. It is not expected to cover every detail, but rather to provide a solid foundation for high-level user stories and requirements.

## Next Steps

Once documentation gathering is complete, proceed to [Requirements Building](requirements-building) to define what needs to be built in the modernised system.

---

[← Previous: Discovery and Analysis](README) | [Next: Requirements Building →](requirements-building)

*This page is part of the DEFRA AI Legacy Modernisation Playbook.*
