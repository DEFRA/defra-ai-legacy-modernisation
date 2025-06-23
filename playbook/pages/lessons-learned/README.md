
# Lessons Learned

This document captures key lessons learned during the DEFRA AI Legacy Modernisation project to help future teams avoid common pitfalls and adopt best practices.

## Working with AI Tools

### GitHub Copilot and Visual References

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

## Future Considerations

- Document other lessons learned as the project progresses
- Share insights with the broader team
- Update this document regularly to capture new discoveries
