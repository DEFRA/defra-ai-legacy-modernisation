# The Four Pillars of Legacy Modernisation

To effectively modernise legacy systems using AI assistance, four pillars must work together as shown in the diagram below.

<img src="./attachments/four-pillars-venn-diagram.svg" alt="Four Pillars Venn Diagram" width="500">

*Image: Venn diagram showing the intersection of elements for consistent AI code generation*

These pillars are essential for ensuring that AI can assist in generating high-quality code, advising on architecture, and helping to build new features.

## The Four Pillars

### 1. Domain Knowledge
**Purpose**: Understanding the business logic, requirements, and constraints of the legacy system is crucial for AI tools to generate contextually relevant code and migration strategies. If you don't know what the system does, AI can't help effectively.

**Where to start**: Ensure you or someone on your team understands the system's users, workflows, and interactions. SMEs (Subject Matter Experts) can provide valuable insights into requirements and constraints.

### 2. Effective System Documentation
**Purpose**: Clear technical documentation of the system's architecture, data structures, and workflows enables AI tools to generate accurate code and migration paths.

**Where to start**: Ensure you have comprehensive documentation of the system's architecture, data models, and workflows. If existing documentation is lacking, consider using AI tools to help generate or improve it.

### 3. Good Prompts

**Purpose**: Create clear, detailed requests for specific tasks. You can refer to IDE rules and requirements, but don't repeat what's already in the rules or requirements in the prompt.

**Where to start**: Create prompts manually at first, then refine them using a chat model like Claude or ChatGPT.

### 4. Capable Code Generation Model

**Purpose**: Use the most capable LLM model for your task to get high-quality results. Not all tasks need advanced models, so select the most cost-effective model that can achieve the outcome you want. The majority of examples in this playbook use Claude Sonnet 3.5.

**Where to start**: AI IDE tools typically let you select which model to use when prompting the LLM.

## Next steps

Read and understand the detailed [Prompting Guidance](../appendix/prompt-library/prompting-guidance.md) before you start.

## [Next -> Mindset](ai-working-mindset.md)
