# Ticket Template

This template provides a structured format for creating user stories that can be effectively processed by AI tools during legacy system modernisation. It ensures that generated tickets are manageable in scope and contain all necessary context for development teams.

**When to use this template:**
- Converting legacy system requirements into user stories
- Breaking down large features into manageable development tasks
- Providing AI tools with structured input for ticket generation
- Ensuring consistency across development teams

**Prompt:**

```
# Context

Use this template to create well-structured user stories for legacy system modernisation. Each ticket should be focused on a single, testable piece of functionality that can be completed within a sprint.

## Background
**What/why is this ticket needed?**

[Describe the background and context for this ticket, including any legacy system functionality being replaced or modernised]

## User Need

**As a** [user type/role]  
**I want** [desired functionality/feature]  
**So that** [benefit/value/outcome]

## Acceptance Criteria

**AC1 -** [First acceptance criterion]

**AC2 -** [Second acceptance criterion]

**AC3 -** [Third acceptance criterion]

[Add additional acceptance criteria as needed, but keep the ticket scope manageable]

## Technical Notes

**Are there any technical considerations for this ticket?**

[Add any relevant technical details, architecture decisions, or implementation notes]

**Dependencies**

[List any dependencies on other tickets, external systems, or prerequisite work]

## Definition of Done

- [ ] All acceptance criteria are met
- [ ] Code is peer reviewed
- [ ] Unit tests are written and passing
- [ ] Integration tests are written and passing (where applicable)
- [ ] Documentation is updated
- [ ] Accessibility requirements are met (for UI changes)
- [ ] Security considerations are addressed
```

## Guidelines for AI-Generated Tickets

When using this template with AI tools:

1. **Keep scope small**: Each ticket should represent 1-3 days of development work
2. **Be specific**: Avoid vague requirements - use concrete, testable criteria
3. **Include context**: Reference the legacy system being replaced or modernised
4. **Consider dependencies**: Identify blocking relationships early
5. **Focus on user value**: Every ticket should deliver tangible user benefit

---

[← Back to Prompt Library](../.)