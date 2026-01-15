---
agent: design-to-code
---
Analyze the selected frame in Sketch and review all layer names for semantic quality and HTML/CSS compatibility.

Extract all layer names from the selected frame and nested layers, then evaluate them against these criteria:

## Naming Best Practices

### Semantic Clarity
- Names should clearly describe the layer's purpose or content
- Avoid generic names like "Group", "Rectangle", "Text", "Shape 1"
- Use descriptive names: "profile-image", "user-name", "action-button", "card-header"

### BEM Compatibility
Evaluate names for BEM (Block, Element, Modifier) methodology:
- **Block**: Standalone component (e.g., "card", "button", "profile")
- **Element**: Part of a block (e.g., "card-header", "button-text", "profile-image")
- **Modifier**: Variant or state (e.g., "button-primary", "card-featured", "text-bold")

Names should work well with BEM separators:
- Elements use `__` (double underscore): `.card__header`
- Modifiers use `--` (double dash): `.button--primary`

### Consistency
- Use consistent naming patterns throughout the frame
- Apply the same naming convention for similar elements
- Maintain clear hierarchy that reflects the component structure
- Use lowercase with hyphens (kebab-case) for multi-word names

### HTML Element Mapping
Consider how names will map to HTML elements:
- "button" → `<button>`
- "image" or "avatar" → `<img>`
- "heading" or "title" → `<h1>`, `<h2>`, etc.
- "text" or "description" → `<p>`
- "list" → `<ul>` or `<ol>`
- "container" or "wrapper" → `<div>`

### Icons
- Name icon layers clearly: "icon-heart", "icon-star", "icon-menu"
- Include the icon purpose if context-specific: "icon-share", "icon-bookmark"

## Analysis Output

For each layer in the selected frame, provide:

1. **Current name**: The layer's name in Sketch
2. **Evaluation**: Whether the name is good, acceptable, or needs improvement
3. **Suggested name** (if improvement needed): A better alternative following best practices
4. **Reasoning**: Brief explanation of why the suggestion improves semantic quality

## Structure

Present findings in a clear, hierarchical format that shows:
- The frame/component hierarchy
- Parent-child relationships between layers
- Groups and their contents

## Summary

After analyzing all layers, provide:
- Count of well-named layers
- Count of layers needing improvement
- General patterns to improve (e.g., "Replace generic 'Group' names with descriptive container names")
- Overall naming consistency score (Good/Fair/Needs Work)

## Next Steps

If improvements are suggested, offer to:
1. Generate a batch rename script for Sketch (using Sketch/run_code)
2. Proceed with code generation using current names
3. Wait for manual renaming before proceeding

The goal is to ensure layer names translate seamlessly into semantic HTML elements and maintainable CSS class names using BEM methodology.