# Build GDS-Compliant Views

Building GDS-compliant views transforms refined user stories into modern, accessible web interfaces following the GOV.UK Design System. This process converts legacy MS Access forms into responsive, user-friendly interfaces while maintaining functionality and improving accessibility.

<pre class="mermaid">
flowchart TD
    A["📝 Refined User Stories"] --> B["🔍 Analyse Requirements"]
    A --> C["🤖 Generate Code with AI"]
    B --> C
    C --> D["🔍 Code Review & Refinement"]
    D --> E["🧪 Testing & Iteration"]
    E --> F{"Views Complete?"}
    F -->|No| G["🔄 Refine Implementation"]
    F -->|Yes| H["✅ GDS-Compliant Web Interface"]
    G --> C

    classDef input fill:#e8f5e8,stroke:#2e7d32,stroke-width:2px
    classDef process fill:#e3f2fd,stroke:#1976d2,stroke-width:2px
    classDef ai fill:#fff3e0,stroke:#f57c00,stroke-width:2px
    classDef review fill:#f3e5f5,stroke:#7b1fa2,stroke-width:2px
    classDef decision fill:#ffeb3b,stroke:#f57f17,stroke-width:2px
    classDef output fill:#e8f5e8,stroke:#2e7d32,stroke-width:2px

    class A input
    class B,D,E process
    class C,G ai
    class F decision
    class H output
</pre>

## Prerequisites

- Refined user stories from the previous step with detailed technical specifications
- AI tool access for code generation
- Development environment set up for your chosen framework
- Understanding of GDS Design System principles

## Key Activities

### 1. Generate Initial Code with AI
Use AI tools to create GDS-compliant interfaces from refined user stories:
- **Use the [Build Views in GDS Style prompt](../../../appendix/prompt-library/general/build-views-in-gds-style)**: Ensure consistent implementation
- **Reference user stories**: Use form documentation and requirements as context
- **Avoid using screenshots**: Prevent design limitations by not using direct image input
- **Ensure semantic HTML**: Implement proper form structure and GDS CSS classes

### 2. Review and Refine Implementation
Analyze generated code against GDS standards and modernization goals:
- **Assess GDS compliance**: Compare against design system patterns and components
- **Evaluate user flow**: Check for logical navigation and task completion
- **Identify gaps**: Find differences between AI output and modern web standards
- **Refine prompts**: Request specific improvements based on analysis
- **Update component specifications**: Better map legacy components to GDS equivalents

### 3. Test and Iterate
Conduct comprehensive testing to ensure quality and accessibility:
- **Accessibility testing**: Test screen reader, keyboard navigation, color contrast
- **Functional testing**: Compare with legacy system functionality
- **User acceptance testing**: Validate workflows and gather feedback
- **Technical validation**: Check HTML semantics, responsive behavior, GDS pattern compliance

## Common Challenges and Solutions
- **Generated Code Doesn't Meet GDS Standards**: Use specific GDS Design System references in prompts. Iteratively refine based on component library patterns.
- **Accessibility Issues**: Include detailed accessibility requirements in user stories. Test with screen readers and keyboard navigation.

## Success Criteria

GDS view building is complete when:
- ✅ All interfaces follow GDS Design System patterns and components
- ✅ Code uses semantic HTML and proper accessibility features
- ✅ Views support keyboard navigation and screen reader compatibility
- ✅ Responsive design works across all device sizes
- ✅ Functionality matches legacy system capabilities
- ✅ User workflows are tested and validated

## Next Steps

The next step will focus on connecting these frontend views to backend APIs to complete the full application stack.

---

[← Previous: Document Forms](01-create-ui-documentation) | [Next: Connect to Backend API →](03-connect-backend-api)

*This step is part of the DEFRA AI Legacy Modernisation Playbook.*
