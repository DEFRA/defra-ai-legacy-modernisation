
# Lessons Learned

This document captures key lessons learnt during the DEFRA AI Legacy Modernisation project to help future teams avoid common pitfalls and adopt best practices.

## Working with AI Tools

### 1. Issue with Documentation of Legacy Application

**Issue**: GitHub Copilot had difficulty interpreting PowerPoint presentations (.pptx files) when used as reference material for implementing UI components and pages.

**Root Cause**: AI tools like GitHub Copilot work better with image formats that provide clear visual information rather than proprietary document formats.

**Solution**: Export PowerPoint slides as PNG images with the following specifications:
- Minimum resolution: 1080px width
- High quality export settings
- Clear, readable text and UI elements

**Best Practice**: When providing visual references to AI tools:
- Use high-resolution images (PNG, JPEG)
- Ensure text is clearly readable
- Include multiple views/states of components when relevant
- Consider providing both overview and detailed views

**Impact**: This approach significantly improved the accuracy of AI-generated code and reduced the number of revision cycles needed to match the intended design.

### 2. Hallucinating Table IDs

**Issue**: The database schema contained reference tables that intentionally did not have ID columns. However, Copilot inherently applies SQL best practices and automatically generated ID columns for tables that shouldn't have them.

**Root Cause**: Copilot's training prioritises standard database design patterns, which typically include primary key ID columns for all tables.

**Solution**: We resolved this by creating a stricter prompt that explicitly stated: "Tables should be created exactly as specified in the schema. Tables without IDs in the original schema must be created without ID columns."

**Impact**: This ensured the migrated database structure matched the original Access database design exactly.

### 3. Synthetic Data Character Length Overflow

**Issue**: During the Access DB to PostgreSQL migration, we requested Copilot to add 'Fake' prefixes to names and addresses to clearly identify synthetic data and avoid any Personal Identifiable Information (PII) concerns. This caused the generated data to exceed the original schema's character limits.

**Root Cause**: Adding 'Fake' as a prefix increased string lengths beyond the original column constraints (e.g., 'John Smith' became 'Fake John Smith', increasing from 10 to 15 characters).

**Solution**: We used Copilot to truncate the synthetic data to fit within the original schema constraints.

**Best Practice**: For future projects, the ideal solution would be to use shorter prefixes such as 'F_John Smith' instead of 'Fake John Smith', which would minimise character length impact whilst still clearly indicating synthetic data. Consider either:
- Using minimal prefixes (F_, X_, TEST_)
- Increasing column lengths in test environments
- Adding separate boolean flags to indicate synthetic data

## Future Considerations

- Document other lessons learnt as the project progresses
- Share insights with the broader team
- Update this document regularly to capture new discoveries
