# Epics Generation Prompt

This prompt can be used to generate epics for a legacy system modernisation project based on existing system documentation. The epics will guide the redevelopment of the system and creation of user stories to implement the required functionality.

```
# Context
You are a business analyst working in a legacy system modernisation project within UK Government. You have been tasked with producing a set of epics that will be used to guide the redevelopment of a legacy software system.

# Analysis Phase
Using the #file:documentation provided, you should analyse the current system and identify the following:
1. Key business processes that the new system must support
2. User roles and their interactions with the system
3. Pain points and limitations of the current system
4. Regulatory and compliance requirements that must be met
5. Integration points with other systems and data sources

# Epic Generation
Based on your analysis, generate a set of epics that encapsulate the high-level requirements for the new system. Each epic should:
- Be clearly defined and focused on a specific area of functionality
- Include acceptance criteria to ensure the epic meets user needs
- Have a clear business value and priority

# Output
You should output each epic as a folder and `README.md` file within that folder. The `README.md` should contain the epic description, acceptance criteria, and business value.

# Epic Template
```
# Epic Title
A concise title that captures the goal of the epic.

# Description
A brief overview of the epic, outlining its purpose and scope.

# Acceptance Criteria
- List of specific conditions that must be met for the epic to be considered complete.

# Business Value
A statement of the value this epic brings to the business, including any metrics or KPIs that will be used to measure success.
```

[← Back to Prompt Library](../.)