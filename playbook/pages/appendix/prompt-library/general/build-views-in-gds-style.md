# Build Views in GDS Style

**Prompt:**

```
# CONTEXT

You have been provided with a screenshot of a screen from the legacy system and its associated user story. Your task is to create a single webpage based on the image and story.

# ANALYSIS PHASE

For each webpage:
- Analyse the screenshot and read the user story to determine the required elements, fields, and structure.
- Generate a checklist of all visible elements.

# IMPLEMENTATION PHASE

- Only implement elements and fields that are explicitly visible in the screenshot.
- Update the elements you add to be in keeping with the GDS (gov.uk) design system and GDS accessibility requirements as shown below.
- Do not create or populate form fields or other content that isn't clearly shown in these materials.
- Adhere to the GDS gov.uk design system: https://design-system.service.gov.uk
- Meet GDS accessibility requirements: https://design-system.service.gov.uk/accessibility/
- Update the routes and index page appropriately to allow navigation to this page.
- If the screenshot has a tabbed interface, generate each tab as its own HTML page and use the tab name as the filename.
- All form fields must have proper semantic HTML with appropriate labels, hints, and error handling structure.
- Forms must be fully navigable via keyboard and screen reader accessible.
- Update the router file to include the new pages.
- Ensure all form fields have hint text that is appropriate to the field and follows GDS guidelines.
```

---

[← Back to Prompt Library](../.)