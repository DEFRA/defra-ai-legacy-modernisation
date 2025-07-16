# The Four Pillars of Legacy Modernisation

To effectively modernise legacy systems using AI assistance, four pillars must work together as shown in the diagram below:

<img src="./attachments/four-pillars-venn-diagram.svg" alt="Four Pillars Venn Diagram" width="500">

*Image: Venn diagram showing the intersection of elements for consistent AI code generation*

These pillars are essential for ensuring that AI can assist in accelerating legacy transformation, advising on architecture, and helping to build new features.

## The Four Pillars

### 1. Domain Knowledge
**Purpose**: Understanding the business logic, requirements, and constraints of the legacy system is crucial for AI tools to generate contextually relevant code and migration strategies. If you don't know what the system is supposed to do, an AI tool won't either.

**Where to start**: Ensure you or someone on your team understands the system's goals, business processes, and workflows. SMEs (Subject Matter Experts) can provide valuable insights into requirements and constraints. This domain knowledge is essential for guiding AI tools in accurately modernising legacy systems.

### 2. Clear Modernisation Goal
**Purpose**: Define a clear and specific goal for the modernisation effort. This goal shouldn't be just a 'lift and shift' to a newer platform, but rather a transformation that improves the user experience, performance, and maintainability of the system. A well-defined goal helps AI tools focus on delivering relevant solutions.

**Where to start**: Ask users and stakeholders what they want from the modernised system. This could include fixing existing issues / pain points, improving performance, or adding new features. Document these requirements clearly to guide the AI tools.

### 3. Effective AI Usage

**Purpose**: Combine capable AI models with well-crafted prompts to get high-quality results. This involves both selecting the right AI tools for your task and knowing how to communicate effectively with them through clear, detailed requests.

**Where to start**: 
- **Model selection**: Use the most capable LLM model appropriate for your task. Not all tasks need advanced models, so select the most cost-effective model that can achieve your desired outcome. Most AI IDE tools let you select which model to use.
- **Prompt crafting**: Create clear, detailed requests for specific tasks. You can refer to IDE rules and requirements, but don’t repeat what’s already in the rules or requirements in the prompt. Start by creating prompts manually, then refine them using chat models like Claude or ChatGPT.

### 4. Effective Technical Documentation
**Purpose**: Provide a clear and comprehensive technical overview of the system's architecture, data structures, and codebase. This documentation serves as a foundation for AI tools to understand the system and generate accurate code. This is different from domain knowledge, which focuses on business logic and requirements, while the technical documentation should on the technical aspects of the system.

**Where to start**: Ensure you have comprehensive documentation of the system's architecture, data models, and codebase. If existing documentation is lacking, consider using AI tools to help generate or improve it.

[← Previous: Getting Started](.) | [Next: Workflow →](workflow)
