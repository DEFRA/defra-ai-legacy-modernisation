# User Story Generation

This prompt can be used to create user stories for a legacy system modernisation project based on existing system documentation. An example ticket template has been provided below but you can swap it out for your own if you have a different format.

```
# Context

You are a business analyst working in a legacy system modernisation project. Your task is to create user stories based on the provided system documentation and requirements. Each user story should be focused on a single, testable piece of functionality that can be completed within a sprint.

You should use the following template to structure your user stories and 

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

1. **Link to Epic**: Ensure each user story is linked to a relevant epic
2. **Keep scope small**: Each ticket should have a single clear scope that can be completed within a sprint
3. **Be specific**: Avoid vague requirements - use concrete, testable criteria
4. **Include context**: Reference the legacy system being replaced or modernised
5. **Consider dependencies**: Identify blocking relationships early
6. **Focus on user value**: Every ticket should deliver tangible user benefit

---

[← Back to Prompt Library](../.)