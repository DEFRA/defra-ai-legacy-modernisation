# Legacy System Modernisation Workflow

The diagram below shows the main steps that are covered in this playbook. This workflow is designed to help teams modernise legacy systems using AI tools effectively. It provides a structured approach to understanding the existing system, gathering requirements, and implementing a modernised solution.

### Workflow Key

| Colour | Process Stage | Description |
|-------|---------------|-------------|
| 🔵 **Blue** | 💻 Legacy System | Starting point - the existing system to modernise |
| 🟢 **Green** | 📋 Documentation Gathering | Collecting knowledge about the system and creating documentation |
| 🟠 **Orange** | 📝 Requirements Building | Defining system requirements, epics and user stories |
| 🟣 **Purple** | 🪄⚙️ Implementation | Building, testing and validating the modernised system |
| 🔴 **Pink** | 🏛️ Deployment | Final deployment to production environment |

### Workflow Diagram

<pre class="mermaid">
flowchart TD
    A["💻 Legacy system to modernise"] --> B["🧑‍💻 Find a SME"]
    B --> C["🧑‍💻 Locate system documentation (if possible)"]
    C --> D["🤖🧑‍💻 Create / improve documentation using both manual tweaks and prompts"]
    D --> E["🤖 Prompt to test understanding of documentation"]
    E --> F["🤖 Prompt to create high-level overview of system"]
    F --> G["🤖 Prompt to create epics and user stories"]
    G --> H["🪄🤖 Take user stories and prompt to generate code and tests"]
    H --> K["🧑‍💻 QA / testing with SME and end-users"]
    K --> J["🏛️ Deploy to Defra CDP"]

    classDef legacySystem fill:#e1f5fe,stroke:#01579b,stroke-width:2px
    classDef infoGathering fill:#e8f5e8,stroke:#2e7d32,stroke-width:2px
    classDef requirements fill:#fff3e0,stroke:#f57c00,stroke-width:2px
    classDef implementation fill:#f3e5f5,stroke:#7b1fa2,stroke-width:2px
    classDef deployment fill:#fce4ec,stroke:#880e4f,stroke-width:2px

    class A legacySystem
    class B,C,D,E infoGathering
    class F,G requirements
    class H,K implementation
    class J deployment
</pre>

## Key Stages of the Workflow

* **Legacy System Assessment** - Start by assessing your existing legacy system that needs modernisation. This could be a database application, a legacy web application, or any other system requiring updates.
* **Locate a Subject Matter Expert (SME)** - Find someone who either uses the system or understands how the current system works, its business processes, and its requirements. This person will be crucial for understanding the system's domain knowledge.
* **Find Existing Documentation** - Gather any existing documentation about the system. This may include: technical specifications, user manuals, database schemas, business process documents, and architecture diagrams. Documentation may be sparse, outdated, or even non-existent.
* **Create / Improve Documentation** - Use a combination of manual tweaks and AI prompts to build upon the documentation. Techniques could include documenting business processes, screenshoting user interfaces, and mapping data flows. Working with end-users, SMEs, and current developers is crucial to ensure accuracy.
* **Test AI Understanding** - Use prompts to verify that AI tools correctly understand the documented system.
* **Create High-Level System Overview** - Prompt AI to generate a comprehensive overview of the system, including system architecture, key components and their relationships, data flows, and integration points.
* **Generate Epics and User Stories** - Use AI to break down the modernisation into manageable pieces. This includes creating high-level epics and breaking them into detailed user stories, and prioritising features and functionality.
* **Generate Code and Tests** - Iterate through user stories, using AI to build user journeys, develop frontend components, and corresponding tests. This step may involve multiple iterations to refine the code and ensure it meets requirements.
* **QA/Testing with SME and End-Users** - Conduct comprehensive testing with stakeholders to ensure the modernised system meets requirements.
* **Deploy to Defra CDP** - Deploy the modernised system to Defra's Core Delivery Platform (CDP), following Defra's deployment standards and practices.

## Key Principles

This workflow is built on several core principles that ensure successful legacy system modernisation:

### Documentation-First Strategy
High-quality documentation is essential for effective AI assistance—the more comprehensive it is, the better AI tools can assist you. Without proper documentation, your team will fail to harness the full potential of AI tools and may end up with systems that don't meet user needs or business requirements.

### Stage-Based Progression
The first three stages (Legacy System Assessment, Documentation Gathering, and Requirements Building) are generic and foundational—they set the groundwork for AI assistance in later stages.

The final stages (Implementation and Deployment) are tailored to specific technology pathways covered in the [Pathways section](../pathways/README).

### Iterative and Adaptive Approach
The process is designed to be iterative, allowing for continuous validation and improvement, incremental delivery of value, and flexibility to adapt based on learning or changing requirements.

## Best Practices

1. **Engage SMEs early**: Their domain knowledge is crucial for success
2. **Validate AI understanding**: Always test that AI correctly interprets your documentation
3. **Start small**: Begin with simple user stories before tackling complex features
4. **Test continuously**: Generate tests alongside code to ensure quality
5. **Follow Defra standards**: Ensure compliance with Defra's technical and security requirements

## Related Resources

- [Four Pillars of Legacy Modernisation](./four-pillars)
- [Prompt Library](../appendix/prompt-library/README)
- [Responsible Practices](../responsible-practices/README)

---

[← Previous: Four Pillars](four-pillars) | [Next: Discovery and Analysis →](../discovery-analysis/)