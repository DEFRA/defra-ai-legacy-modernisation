# Build GDS-Compliant Views

## Overview

After documenting forms and creating user stories, the next step is to build modern, accessible user interfaces following the GDS (GOV.UK) Design System. This process transforms legacy MS Access forms into web-based interfaces that maintain functionality while improving usability, accessibility, and design consistency.

<pre class="mermaid">
flowchart TD
    A["📋 Form Documentation"] --> B["🔍 Analyse Requirements"]
    C["📖 User Stories"] --> B
    D["🖼️ Form Images"] --> B
    B --> E["🤖 Generate Code with AI"]
    E --> F["🔍 Code Review & Refinement"]
    F --> G["🧪 Testing & Iteration"]
    G --> H{"Views Complete?"}
    H -->|No| I["🔄 Refine Implementation"]
    H -->|Yes| J["✅ GDS-Compliant Web Interface"]
    I --> E

    classDef input fill:#ffebee,stroke:#c62828,stroke-width:2px
    classDef process fill:#e3f2fd,stroke:#1976d2,stroke-width:2px
    classDef ai fill:#fff3e0,stroke:#f57c00,stroke-width:2px
    classDef review fill:#f3e5f5,stroke:#7b1fa2,stroke-width:2px
    classDef decision fill:#ffeb3b,stroke:#f57f17,stroke-width:2px
    classDef output fill:#e8f5e8,stroke:#2e7d32,stroke-width:2px

    class A,C,D input
    class B,F,G process
    class E,I ai
    class H decision
    class J output
</pre>

## Prerequisites

- Completed form documentation from the previous step
- User stories generated following GDS standards
- Screenshots or detailed descriptions of legacy forms
- AI tool access for code generation
- Development environment set up for your chosen framework
- Understanding of GDS Design System principles

## Building Process

### 1. Prepare Your Materials

Before beginning development, ensure you have:

1. **Form documentation** with complete component inventories
2. **User stories** that detail all required functionality
3. **Visual references** (screenshots) of the original forms
4. **Business logic understanding** for any complex interactions

### 2. Use AI Tools for Code Generation

Leverage AI tools to generate initial code while ensuring quality and compliance:

#### Using the Build Views Prompt
1. **Reference your form documentation** and user stories in your AI tool
2. **Use the Build Views in GDS Style prompt** from our prompt library as guidance
3. **Provide clear context** about the specific form you're implementing
4. **Include screenshots** of the original form for visual reference

The [Build Views in GDS Style prompt](../../../appendix/prompt-library/general/build-views-in-gds-style) ensures that generated code:
- Follows GDS Design System patterns
- Implements proper semantic HTML
- Includes appropriate ARIA labels and accessibility features
- Uses correct validation and error handling structures
- Maintains responsive design principles

#### Key Implementation Guidelines
When using AI tools, ensure the generated code:
- **Only implements visible elements** from your screenshots
- **Uses semantic HTML** with proper form structure
- **Includes appropriate labels and hints** for all form fields
- **Implements GDS validation patterns** for error handling
- **Supports keyboard navigation** throughout the interface
- **Uses GDS CSS classes** and component patterns

### 3. Code Review, Refinement, and Analysis

After generating initial code, review the first iteration of webpages and use your AI tool to refine the implementation based on your vision for GDS compliance and user flow:

#### Developer Analysis and Vision Alignment
- **Review the generated webpage** against your expectations for modern web standards
- **Assess GDS compliance** by comparing against design system patterns and components
- **Evaluate user flow** to ensure logical navigation and task completion
- **Identify gaps** between the AI-generated output and your vision for the modernised interface
- **Document specific refinements** needed to better align with GDS principles

#### AI-Assisted Component Refinement
- **Refine your prompts** based on your analysis of the initial output to request specific improvements
- **Update component specifications** in your prompts to map legacy components to more appropriate GDS Design System equivalents
- **Enhance prompt instructions** for complex interactions that require better handling for modern web standards
- **Improve responsive design prompts** for optimal display across different screen sizes

#### AI-Assisted Accessibility Enhancement
- **Refine accessibility prompts** based on your review of semantic structure to improve screen reader compatibility
- **Update navigation instructions** in prompts to enhance keyboard navigation paths and focus management for better usability
- **Enhance error handling prompts** to refine validation messaging that follows GDS patterns
- **Improve visual accessibility prompts** including high contrast and clear visual hierarchy requirements

#### Technical Review
- **Validate HTML semantics** and accessibility compliance improvements
- **Test keyboard navigation** and screen reader compatibility enhancements
- **Verify GDS Design System** pattern implementation accuracy
- **Check responsive behaviour** across device sizes

#### Functional Review
- **Compare with original form** functionality to ensure feature parity
- **Test all user interactions** documented in user stories
- **Validate business logic** implementation in the refined interface
- **Ensure error handling** meets modernised requirements

### 4. Testing and Iteration

Conduct comprehensive testing:

#### Accessibility Testing
- **Screen reader testing** with tools like NVDA or VoiceOver
- **Keyboard navigation testing** without mouse interaction
- **Colour contrast validation** using accessibility tools
- **Focus management verification** for complex interactions

#### User Acceptance Testing
- **Compare functionality** with legacy system
- **Validate user workflows** end-to-end
- **Test edge cases** and error scenarios
- **Gather feedback** from actual users when possible

## Next Steps

The next step will focus on connecting these frontend views to backend APIs to complete the full application stack.

---

[← Previous: Document Forms](01-create-ui-documentation) | [Next: Connect to Backend API →](03-connect-backend-api)

*This step is part of the DEFRA AI Legacy Modernisation Playbook.*
